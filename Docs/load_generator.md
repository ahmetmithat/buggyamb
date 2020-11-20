<h1>Experimental "Load Generator"</h1>

"Load Generator" is nothing but some jQuery scripts that can send multiple requests. You can use this tool to send multiple requests to different pages of BuggyAmb:

![BuggyAmb Load Generator](Images/load_generator.png)

The most important limitation with this tool is the number of the concurrent requests you can make to the BuggyAmb application. Since the tool is based on jQuery Ajax calls, we easily hit the 6 concurrent Ajax call browser limit.


However this tool is still quite useful for reproducing the scenarios because most of the times the problems are easy to reproduce for BuggyAmb application. If, for some reason, you need more requests to test a scenario then there are workarounds: you can open an inPrivate browsing session and can have 6 more concurrent requests. Similarly, you can open one another vendor's browser to have another 6 concurrent request power.

