<h1>Experimental "Load Generator"</h1>

"Load Generator" is nothing but some jQuery scripts that can send multiple requests to  different scenarios explained in the <a href="quick_tour.md">quick tour</a>:

![BuggyAmb Load Generator](Images/load_generator.png)

It is not a rocket science, just select the page/scenario from list and tell how many requests you want to send there and click Request Page. Load Generator will add those requests in the list and show you if those are running or ended up sucessfully or gave an error. Elapsed time will tell how long it took to get the response:

![BuggyAmb Load Generator](Images/load_generator_in_action.png)

Screenshot above tells me that there are two requests for <code>/Problem/NotFound</code> page, one is ended up with HTTP 200 and the other one is ended up with HTTP 404. There are two requests for <code>/Problem/Slow</code> and <code>/Problem/Expected</code> pages and both are ended up with HTTP 200 and the slow one took 8 seconds while the expected one took under 1 second. The request for <code>/Problem/Slow3</code> is still not responded. 

>Important: Elapsed Time is the server time + client time. Remember the 6 concurrent Ajax request limit, if you have more than 6 requests still running in the list then the rest will be waiting on the browser's queue for making the actual call. Elapsed Time also counts those seconds / minutes spent in the browser queue while waiting for an available Ajax connection.

>>If, for some reason, you need more requests to test a scenario then there are workarounds: you can open an inPrivate browsing session and can have 6 more concurrent requests. Similarly, you can open one another vendor's browser to have another 6 concurrent request power.

<h2>Sample Usage Scenarios</h2>

