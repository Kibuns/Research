# What should a novice software developer know before their first contribution to an open source project?
This research will give information to beginning software developers or engineers who are interested in making their first contribution to an open source project. 

## Research Method
Below are all the methods I used for this research. the methods will be from the [DOT Framework](https://ictresearchmethods.nl/Methods)
The methods used are:
- Literature Study
- Expert Interview


## What is open source software?
According to [opensource.com](https://opensource.com/resources/what-open-source):
> The term open source refers to something people can modify and share because its design is publicly accessible.

And OSS(Open Source Software) is
> software with source code that anyone can inspect, modify, and enhance.
"Source code" is the part of software that most computer users don't ever see; it's the code computer programmers can manipulate to change how a piece of software—a "program" or "application"—works. Programmers who have access to a computer program's source code can improve that program by adding features to it or fixing parts that don't always work correctly.

Some examples of popular open source projects are:
- Linux operating system
- Android by Google
- Open office
- Firefox browser
- VCL media player
- Moodle
- ClamWinantivirus
- WordPress content management system

## Why do people work on OSP's?
There are multiple reasons why someone might want to work on an open source project. The most notable ones are described below

### Learning how to code
The best ways to learn how to code are to A, code something and B, see how someone else codes. You will be doing a lot of both of these when you work on OSS. All code in OSS is available to the public, so everybody can read, change and learn from eachother.

### Helping the community
When you work on OSS you are adding value to it. Which can be extremely rewarding, especially if it's software that a lot of people use or software that you use yourself.

### Building a portfolio
Your github might be the most important thing in your resume. So it can be really helpfull to work on OSS to show your motivation, skills and interests. Consistently working on OSS shows your employer that you are involved.

(expert interview)
(I still need to find someone)
- How often do you contribute to an OSP(open source project)?
- What motivated you to do your first contribution to an OSP?
- What do you like about working on OSP's?
- How do you choose an open source project to work on?
- Are there any notable mistakes you made or misunderstanding you had when you first started contributing?
- What tip(s) would you give to a beginning developer who's interested in contributing to an open source project for the first time?


## How do you make a contribution?
A lot of OSP's have a Contributing.md, but what are things like forking? and making pull requests? There are a lot of great sources to learn these things. But https://firstcontributions.github.io/ is what I used.


## What are the most important work etiquettes when working on an open-source project?

### Have a reason to be working on an OSP
Before you make a contribution, think about what you want to get out of it. It's fine to just think "I'm bored and I want to do something productive" because of the "do something productive" part. You most likely want to improve your skills, show of your skills or just help others. Definitely **don't** start working on an OSP if you just want to show of how amazing you are, troll / boss people around, or just want someone to talk to.

### Be kind
Working on an OSP requires you to communicate a lot. Be sure to be polite and avoid offensive language during these conversations. Being kind to other contributers will result in a happier an more productive atmosphere. some ways to achieve this are:
- Thanking the people who help you
- Congratulating people when appropriate
- Always respond respectfully, even if i.e. someone obviously didn't read the documentation and you need to correct them.
- Help people in a supportive way. When you correct someone, don't say "this is wrong" or "here is the answer", say something along the lines of "this is OK, but I feel like it would be better is it was more in this way..., here are some links that could help you". 

### If there's documentation, read it.
Often, contributers on an OSP spend a lot of time documenting the project for people like you to read and get all the info you need. It would be a shame if those people or people that are familiar with the documentation constantly have to correct you on everything. Ofcourse you can ask questions, but first make sure your answer isn't already in the documentation. Most projects have a CONTRIBUTING.md and/or a CODE_OF_CONDUCT.md. Here you can find all of the guidelines, be sure to read and follow these.

### Avoid duplicate issues
Github has a feature that allows you to search for issues. When you have a question or discover a bug, look if your queestion / bug doesn't already exist. If it does, see if you can add to the discussion in a helpfull way.

### Provide sufficient information when making a bug report
[gomakethings](https://gomakethings.com/open-source-etiquette/) describes the following:
> I often get bug reports that say something like, “This isn’t working on my site. What am I doing wrong?”
That’s it. No link. No code. No additional information.

It can be really frustrating when someone finds a bug but doesn't give enough information on how they found it. try to provide sceenshots, code, or anything that could be of use to another developer who wants to fix your bug. If the project is something like a plugin. Try to make a [reduced test case], which is basically a test application with as many things stripped away as possible, which still produces the bug. This can make debugging way easier.

### Make progress, not noise

as the [Mozilla Development Network](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Open_source_etiquette#make_progress_not_noise) puts it:
> Think carefully about the way you handle communication in the project — make sure it is useful, and that it doesn't make other contributor's jobs harder. Submitting pull requests to fix bugs is great, but are they truly useful, and easy to review? Filing issues and joining in other conversations is fine, but are your issues and comments on topic, or are they just adding noise?

As a rule, do:

- Discuss one topic per issue — it is easy to keep issues focused and productive.
- Fix one issue per PR — it may be slightly more work for you, but it is much easier to review a single clear fix.
- Contribute to other threads if you have a useful point to make or can answer someone else's question.
- Ask questions using other mechanisms like chat rooms or forums if you are not sure whether something is useful or have a simple question.
- Read the manual first to try to answer the question yourself before asking it.
Don't:

- Complicate issues by trying to discuss multiple topics at once, or making off-topic comments.
- Try to cram multiple fixes into a single pull request. It makes it a lot harder to review, and raises suspicions (some people might think you are trying to hide some malicious - code in between the valid changes).
- Open lots of issues asking vague questions.
- Ask questions without trying to solve the problem yourself first.

_(Cited do's and don't from [Mozilla Development Network](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Open_source_etiquette#make_progress_not_noise))_


## How can you find your first open source project to work on?

There are a bunch of ways for developers to find open source projects. Github has a search issue function which lets you search by certain criteria. You could for example search for "good first issue" label. This is a label people add to issues that are fit for people who are doing their first issue. A movement called [First Timers Only](https://www.firsttimersonly.com/) are pushing a label with the same name. Issues with this label should be reserved for people who have never done a pull request before. According to first timers only, developers putting this label on an issue also means:
> I’m willing to hold your hand so you can make your first PR. This issue is a bit easier than normal. And anyone who’s already contributed to open source isn’t allowed to touch this one!

[CodeTriage](https://www.codetriage.com/) allows you to pick your favorite repos to receive a different open issue in your inbox every day. This is also a great way to search for projects by language. 

### Sources

- What is open source? (z.d.). Opensource.Com. Geraadpleegd op 10 januari 2022, van https://opensource.com/resources/what-open-source
- W. (2019, 29 november). Open Source: What is it, Examples and Advantages | Workana. Glossary - Workana | El Glosario Workana Explica Terminología Del Mundo Freelance, Conceptos Fundamentales Del Marketing y Los Negocios. Geraadpleegd op 10 januari 2022, van https://i.workana.com/glossary/what-is-open-source/
- Synopsys. (z.d.). What Is Open Source Software and How Does It Work? | Synopsys. Geraadpleegd op 10 januari 2022, van https://www.synopsys.com/glossary/what-is-open-source-software.html
- Wachal, M. (2021, 10 december). Why contribute to open source? - SoftwareMill Tech Blog. Medium. Geraadpleegd op 10 januari 2022, van https://blog.softwaremill.com/why-contribute-to-open-source-cc0b95aa82a7
- Open Source Etiquette. (2016, 26 september). Go Make Things. Geraadpleegd op 10 januari 2022, van https://gomakethings.com/open-source-etiquette/
- Mozilla. (2021, 15 oktober). Basic etiquette for open source projects - The MDN project | MDN. MDN Web Docs. Geraadpleegd op 10 januari 2022, van https://developer.mozilla.org/en-US/docs/MDN/Contribute/Open_source_etiquette
