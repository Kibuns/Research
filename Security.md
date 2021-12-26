# How a severe vulnerability like Log4Shell came to be?


## What is Log4J?
Log4J is a widely used java logging library originally written by Ceki Gülcü. It is used in most moderately sized Java projects. It can be used to track thing like error messages or debug messages, which are then stored or *logged*. Apache describes Log4J as follows:
> log4j is a tool to help the programmer output log statements to a variety of output targets.In case of problems with an application, it is helpful to enable logging so that the problem can be located. With log4j it is possible to enable logging at runtime without modifying the application binary. The log4j package is designed so that log statements can remain in shipped code without incurring a high performance cost. It follows that the speed of logging (or rather not logging) is capital.

> log4j is designed with three goals in mind: reliability, speed and flexibility. There is a tight balance between these requirements. We believe that log4j strikes the right balance.




## Why is Log4Shell a big deal?
Log4Shell (CVE-2021-44228) is a nickname for an severe vulnerability in Log4J. The vulnerability has existed since 2013, and was only "discovered" and privately disclosed to the [Apache Software Foundation](https://en.wikipedia.org/wiki/The_Apache_Software_Foundation) on 24 November 2021. According to the Common Vulnerability Scoring System ([CVSS](https://nvd.nist.gov/vuln-metrics/cvss)) this vulnerability scores a 10/10 for it's severity. This is because this vulnerability enables Remote Code Execution (RCE). Which allows hackers to be able to run any code on your machine. This is also why it is called Log4Shell, because it's almost like anyone can open a [Shell](https://datacarpentry.org/shell-genomics/01-introduction/) on any server that uses Log4J.

According to Snyk, an open source security platform, 60.8% of java projects that use Log4J use it indirectly. Which means that the project has libraries that in turn use Log4J. So even developers that can't directly see that they are using Log4J aren't safe from the vulnerability.
![image](https://user-images.githubusercontent.com/77112006/147350753-63dac8cd-8d3b-4244-ade5-ea239dde1b3c.png)
source: https://snyk.io/blog/log4j-vulnerability-software-supply-chain-security-log4shell/

## How does Log4Shell work?


## How did Log4Shell get discovered?
## What are the potential fixes for severe vulnerabilities like Log4Shell?
![image](https://user-images.githubusercontent.com/77112006/147350117-701b817a-cda4-412c-b85e-89865f4fa72d.png)

## How did affected developers deal with it?

Sources:
- [Log4J Vulnerability (Log4Shell) Explained - for Java developers. (2021, 16 december). [Video]. YouTube.](https://www.youtube.com/watch?v=uyq8yxWO1ls&t=1037s&ab_channel=JavaBrains)
- [Tal, L. (2021, 20 december). The Log4j vulnerability and its impact on software supply chain security. Snyk. Geraadpleegd op 24 december 2021](https://snyk.io/blog/log4j-vulnerability-software-supply-chain-security-log4shell/)
- [Apache log4j 1.2 - Frequently Asked Technical Questions. (z.d.). Apache. Geraadpleegd op 24 december 2021]( https://logging.apache.org/log4j/1.2/faq.html)
-  [Yan, Tao; Deng, Qi; Zhang, Haozhe; Fu, Yu; Grunzweig, Josh (10 December 2021). "Another Apache Log4j Vulnerability Is Actively Exploited in the Wild (CVE-2021-44228)".](https://unit42.paloaltonetworks.com/apache-log4j-vulnerability-cve-2021-44228/)
-  [NVD - Vulnerability Metrics. (z.d.). NVD. Geraadpleegd op 24 december 2021](https://nvd.nist.gov/vuln-metrics/cvss)
