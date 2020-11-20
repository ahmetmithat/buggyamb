<h1>Experimental "Load Generator"</h1>

"Load Generator" is nothing but some jQuery scripts that can send multiple requests. You can use this tool to send multiple requests to different pages of BuggyAmb:

![BuggyAmb Load Generator](Images/load_generator.png)

Just select the page from list and tell how many requests you want to send there and click Request Page. Load Generator will add those requests in the list and show you if those are running or ended up sucessfully or gave an error. Elapsed time will tell how long it took to get the response:

![BuggyAmb Load Generator](Images/load_generator_in_action.png)

>Important: Elapsed Time is the server time + client time. Remember the 6 concurrent Ajax request limit, if you have more than 6 requests still running in the list then the rest will be waiting on the browser's queue for making the actual call. Elapsed Time also counts those seconds / minutes spent in the browser queue while waiting for an available Ajax connection.

>If, for some reason, you need more requests to test a scenario then there are workarounds: you can open an inPrivate browsing session and can have 6 more concurrent requests. Similarly, you can open one another vendor's browser to have another 6 concurrent request power.

<h2>Sample Usage Scenarios</h2>

