<h1>What is BuggyAmb?</h1>

BuggyAmb is just a very buggy ASP.NET Core Razor Pages based application. This application was intentionally created as a buggy application so it can be used as a learning resource to practice troubleshooting some sample problem scenarios:

* High CPU or low CPU performance problems, deadlocks.
* High memory issues.
* Crash issues and unexpected exceptions.

Each release of BuggyAmb may have a different look and may include different scenarios to troubleshoot. Please check the release information for more details.

All releases will be here: https://github.com/ahmetmithat/buggyamb/releases/

* <a href="Docs/windows_installation_instructions.md">Windows Installation Instructions</a>
* <a href="Docs/linux_installation_instructions.md">Linux Installation Instructions</a>

<h2>Very speacial thanks to Tess Ferrandez</h2>

Tess Ferrandez is a software engineer at Microsoft and when I started my support engineer career at Microsoft, I practiced her famous "BuggyBits" application and I took those great debugging labs to learn ASP.NET debugging on WinDbg.

Some scenarios on the initial release of BuggyAmb is based on what Tess did with BuggyBits. I "borrowed" at least two scenarios and implemented it in BuggyAmb (also borrowed the name as well).

You can follow Tess at https://github.com/TessFerrandez.

<h1>Why? What is the goal of BuggyAmb?</h1>

The goal of this application is NOT teaching you the best practices when writing ASP.NET Core applications, instead the goal is to help you get better at defining a problem, collecting data and performing some data analysis in debuggers.

As a support engineer, I can confidently say that if you know how to collect the required data when you encounter a problem, you have the most important knowledge on the way to a solution. Collecting the right data at the right time is one of the most important steps to take to address a problem and solve it.

<h2>A successfull troubleshooting session has the following characteristics:</h2>

<h3>Identifying the issue</h3>

If you cannot define the problem then you cannot know where to look. If you don't know where to look you cannot collect good data and as a result, you cannot solve the problem easily. Some problems seem complex but if you define it correctly you may narrow down it to a specific component.

If you know how your application works then you can understand what is different when the problem happens and you can start defining the problem.

<b>A bad definition:</b> it was running fast and now it is slow.
<br/>
<b>Good definition:</b> it was responding to this page under 1 seconds and when the problem happens it takes up to 60 seconds. At the same time CPU and memory usage also increases until the application is restarted.

<h3>Collecting data</h3>

Once you identify the issue you need to collect the data. Most of the data collection may require to be done when the problem happens. 

If you can reproduce a problem then you are lucky and you can collect data at any time you want but if you cannot reproduce the problem easily and if you miss the data collection then you may need to wait for the next occurence which may be a problem.

So you need to know what kind of tools you have, how to use those tools in which scenario, etc...

<h3>Data analysis</h3>

Just like collecting data, there are great tools that you can use to analyse data and you need to know what kind of tools there are to analyze data.

Note that some data analysis can be done while capturing the data on the server, for example you may want to look at a network trace while you capture it on the server but some data needs to be analyzed seperately on another machine.

So you need to prepare your machine so you can use those tools when needed.

<h3>Fix the problem and avoid it to happen again</h3>

A good data analysis will give you the power to fix the problem and avoid it to happen. Root cause of some of the problems may be related with some external components that you cannot control but you can at least take some pre-cautions to handle the situation when that external component fails.

I also want to highlight the importance of documentation at this stage although the documentation should be done from the first step to last step if possible. I know that the documentation could be a bit difficult under pressure when the business impact is high, but I encourage you to take some notes during each step and document them while you have a cup of tea after the problem is resolved.

If you document it, most likely you are going to avoid the same problem because you will consolidate what you learn while you document it. You can also share your knowledge with the others if you document it and sharing is good.

<h3>Measure and Monitor</h3>

This is last but not least and actually this should be done always, and I mean "always".

* You should always monitor your application and get alerted when a problem happens so you can act on time. There are great tools, such as SCOM, to monitor your applications.
* You should measure your application to understand how your application behaves while everything is working fine.

To measure your application I recommend you to capture some metrics, such as performance counters and use those as a baseline data. Your baseline data should be up to date: don't forget to capture new baseline data if anything is changed in your application or in the environment (e.g.: added new server, installed new patches, upgraded the .NET version, etc...).

Once you have a baseline data, you can compare it with the same metrics captured at a problem time which will help you to answer the following questions:

* What is changed, when is the problem started?
* What were the expected response times and what are the actual response times, how slow is that?
* Are all of the application is affected, or is some part of the application affected?
* Is the load increased? Are the requests queued?
* Are the CPU and memory usages unexpected compared with the baseline data?
* What about exceptions, contentions or context switching, are they increasing?
* etc...

As you can see if you measure and monitor your application then you can easily start identifying the problem. In some scenarios you may need to take action quickly before comparing these data but if you know how your application works then you can at least make some meaningful comments about the questions above which will give you a quick and good start to your troubleshooting session.