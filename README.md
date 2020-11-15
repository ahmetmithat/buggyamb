<h1>What is BuggyAmb?</h1>

BuggyAmb is just a very buggy ASP.NET Core Razor Pages based application. This application was intentionally created as a buggy application so it can be used as a learning resource to practice troubleshooting some sample problem scenarios:

* High CPU or low CPU performance problems, deadlocks.
* High memory issues.
* Crash issues and unexpected exceptions.

Each release of BuggyAmb may have a different look and may include different scenarios to troubleshoot. Please check the release information for more details.

<h2>Very speacial thanks to Tess Ferrandez</h2>

Tess Ferrandez is a software engineer at Microsoft and when I start my support engineer career, I practiced her debugging labs with that famous BuggyBits application she developed. It was one of my greatest learning adventure when I worked with the BuggyBits to practice debugging ASP.NET applications in WinDbg.

Some scenarios on the initial release of BuggyAmb is based on what Tess did with BuggyBits and I "borrowed" at least two scenarios and implemented it in BuggyAmb.

You can follow Tess at https://github.com/TessFerrandez.

<h1>Why? What is the goal of BuggyAmb?</h1>

The goal of this application is NOT teaching you the best practices when writing ASP.NET Core applications, instead the goal is to help you get better at defining a problem, collecting data and performing some data analysis in debuggers.

As a support engineer, I can confidently say that if you know how to collect the required data when you encounter a problem, you have the most important knowledge on the way to a solution. Collecting the right data at the right time is one of the most important steps to take to address a problem and solve it.

<h1>A successfull troubleshooting session has the following characteristics:</h1>

* Identifying the issue: if you cannot define the problem then you cannot know where to look. If you don't know where to look you cannot collect good data and as a result, you cannot solve the problem easily. Some problems seem complex but if you define it correctly you may narrow down it to a specific component.
* Collecting data: once you identify the issue you need to collect the data at the correct time: most of the times you will need to collect the data when a problem happens. If you can reproduce the same problem then it is OK but if you cannot reproduce the problem easily and if you miss the data collection then you may need to wait for the next occurence which may be a problem. So you need to know what kind of tools you have, how to use those tools in which scenario, etc...
* Data analysis: Just like collecting data, there are great tools that you can use to analyse data and you need to know what kind of tools there are. Note that some data analysis can be done while capturing the data on the server, for example you can look at a network trace while you capture data but some data will be analysed seperately on another machine. So you need to prepare your client machine to make analysis on the data collected on another machine - most probbably from a server.
* Fix the problem and avoid it to happen again: a good data analysis will give you the power to fix the problem and avoid it to happen.
* Measure and monitor: this is last but not least and actually this should be done always, meaning that, you should always measure your application to understand how your application behaves while it works. You should capture some metrics, such as performance counters, to use as a baseline. With that baseline data you understand how your application look and how the metrics look like at normal times. Then once you face with a problem you can compare the same metrics to understand the big picture. For example you can check what changed, are the exceptions increasing, are the CPU and/or memory usages unexpected, are there any contention or context switching?, etc...As you can see if you measure and monitor then you can easily identify the problem.
