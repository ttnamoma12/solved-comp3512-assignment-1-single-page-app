Download Link: https://assignmentchef.com/product/solved-comp3512-assignment-1-single-page-app
<br>
This assignment provides an opportunity for you to demonstrate your ability to generate a dynamically updateable single page web application using JavaScript. <strong>You can work in pairs or by yourself.</strong>

<h1>Beginning</h1>

I feel foolish saying this in a third-year university course, but it is your responsibility to read all the assignment instructions thoroughly and carefully. If you are unclear about something, ask me. But before you do, read the material in question again!

Starting files will be found (eventually) at:

https://github.com/mru-comp3512-archive/w2021-assign1.git

The grade for this assignment will be broken down as follows:

<strong><em>Data Files </em></strong>

Images for the logos have been provided. Data is from one of my APIs.

<h1>Requirements</h1>

This assignment consists of a single HTML page (hence single-page application or SPA) with the following functionality:

<ol>

 <li>Your assignment should have just a single HTML page which <strong>must</strong> be named html.</li>

 <li>I expect your page will have significantly more additional CSS styling compared to html. (Every year students receive minimal design marks due to minimal effort in CSS styling). If you make use of CSS recipes you found online, you must provide references (i.e., specify the URL where you found it) via comments within your CSS file. <strong>Failure to properly credit other people’s work in your CSS will likely result in a zero grade. </strong>You can make use of a third-party CSS library; if you do, be sure to indicate this in the header. Attractive styling with your own CSS will result in a higher style mark than if you use a third-party library; poor styling with your own CSS will likely result in a lower style mark than if you use a third-party library.</li>

 <li>You must write your own JavaScript. That is, no jQuery, no Bootstrap, no other third-party</li>

</ol>

JavaScript libraries. You have all the knowledge you need from the lectures and the three JavaScript labs to complete this assignment. If you do find yourself, however, making use of some small snippet of code you found online (and I do mean small), then you <strong>must</strong> provide references (i.e., specify the URL where you found it) via comments within your .js file. <strong>Failure to properly credit other people’s work in your JavaScript will result in a zero grade.</strong> <strong>Using ancient JavaScript found online will result in lower marks.</strong> There is no need to credit code you found in the labs or lectures.

<ol start="6">

 <li>Most of the functionality in the app can be found in the two sketches shown on the next few pages. Each of these is described in more details below. The first shown below is the <strong>Default View</strong>.</li>

 <li><strong>Header</strong>. The page title should be COMP 3512 Assign1. Add an icon or label named Credits. When the user mouses over this icon/label, please display your name(s), the course, any thirdparty technology used (include 3<sup>rd</sup> party CSS if using, Google Maps, charting package, etc). This message should be formatted uniquely and should disappear after 5 seconds (use setTimeout).</li>

 <li><strong>List of Companies</strong>. This must display a list of companies (name field). This assignment uses two discrete APIs: one for retrieving the company list, the other for retrieving company information, quotes, and month’s stock data. The URL for the company list API will be:</li>

</ol>

https://www.randyconnolly.com/funwebdev/3rd/api/stocks/companies.php

This service returns just the most basic information about a few hundred companies.

The API will take some time to retrieve this data. Display a loading animation (there are many free animated GIF or CSS available) until the data is retrieved. For this and the other API, they are also available via HTTP.




<strong>To improve the performance of your assignment, you must store the company data in local storage after you fetch it.</strong> Your page should thus check if this company list data is already saved in local storage: if it is then use local data, otherwise fetch it and store it in local storage. This approach improves initial performance by eliminating this first fetch in future uses of the application. Be sure to test that your application works when local storage is empty before submitting (you can empty local storage in Chrome via the Application tab in DevTools).

In the list simply display the company names, sorted alphabetically. Each list item must be clickable (be sure to change mouse cursor to indicate they are clickable). To make this application more readable, add scrollbars to the fixed-height container using the overflow-y property.

When the user clicks on a company name, then populate the Company Info, Map, and Stock Data sections with the data for the clicked stock/company.

Finally, above the list, provide a filter textbox. When the user types into the textbox (change event), filter the list so it only shows companies whose symbol begins with the same letters typed into the box. Provide some mechanism for clearing the filter (i.e., seeing all the companies).

<ol start="7">

 <li><strong>Company Info</strong>. When the user clicks on a company in the list, then your program will display the rest of the company information already fetched from the API.</li>

</ol>




In this section, display the following information from the JSON: logo, symbol, name, sector, subindustry, address, website, exchange, description. The website

should be an actual working link. Also display the logo (provided). I expect this info to be nicely formatted and laid out sensibly.

<ol start="8">

 <li><strong>Map</strong>. Display a Google Map using the company latitude and longitude properties at the same zoom level as in the lab10 mapping exercise. You will need to make use of the Google Cloud Platform (GCP) credits provided for you.</li>

</ol>




Sometimes students have difficulty getting their Google Map to display correctly; in such a case, check for an error message in the console. The usual problem is that you haven’t yet enabled the API for this service. From the hamburger menu of the Google Cloud Platform dashboard, select the APIs &amp; Services option and then the Library option. Look for Maps JavaScript API from the API Library. Select it then click on the appropriate options to enable your API.

<strong>                 </strong>

<ol start="9">

 <li><strong>Stock Data</strong>. Display stock data for the current company/stock from the following API:</li>

</ol>




https://www.randyconnolly.com/funwebdev/3rd/api/stocks/history.php?symbol=xxx




where xxx is the Symbol property value for the clicked-on company/stock. The API will take some time to retrieve this data. Display a loading animation until the data is retrieved.




This API returns three months of real historical stock data from January 2, 2019 to March 29, 2019. This works out to 61 rows of data. To make this data more readable, add scrollbars to the fixed-height container using the overflow-y property.




Your program will display the date, open, close, high, low, and volume fields.




The headings at the top of each column should be clickable (be sure to change mouse cursor to indicate they are clickable). When the user clicks on a column heading, the data will be redisplayed so that it is sorted on the value just clicked. When first displayed, sort by date. There should only be one initial fetch; the sorting should operate on the already fetched data.




You will also need to calculate and display the following information from the stock data: average, minimum, and maximum values for open, close, low, high, and volume. I expect this information to be nicely formatted (e.g., currency as currency) and laid out sensibly.




When the user clicks on the View Charts button, then sections 6,7,8, and 9 on the page will be hidden and replaced with the Chart View, described next.

<strong>                 </strong>

<ol start="10">

 <li><strong>Chart View</strong>. When the user clicks on the View Charts button, sections 2, 3, 4, 5 will be hidden and replaced with just the chart view for the stock:</li>

</ol>




For the Chart View, display the following fields: symbol, name, and description.

For the Financials area, display the 2017,2018, 2019 revenue, earnings, assets, and liabilities values in a table (this data is in the company data). I expect this information to be nicely formatted (e.g., currency as currency with commas for the big numbers) and laid out sensibly. <strong>NOTE: only about 20% of the stocks have associated financial data, so you must be able to handle this elegantly: i.e., don’t crash and display message in the page (not an alert).</strong>




The Speak buttons will use the speech synthesizer to speak the description field content.




The Close button will hide this view and show instead the <strong>Default View</strong>.

For the charts, I would recommend using either echarts (https://echarts.apache.org/) or chart.js (https://www.chartjs.org/); you can use another package if you wish. These are analogous to Google Maps in that they are an external library with an API you will need to learn and discover. Both of these require either an empty &lt;div&gt; or an empty &lt;canvas&gt; element which will end up being the container for the chart generated by the JavaScript charting library.




You will need the following charts:

<ul>

 <li>a bar or column chart which displays the 2017,2018, 2019 revenue, earnings, assets, and liabilities,</li>

 <li>a candlestick chart which displays the min, max, and average values for open, close, low, and high.</li>

 <li>a line chart which plots the close value and volume for each day in our data set. This will require different y-axis ranges for the close and volume lines. As well, since there are 61 data points, your x-axis labelling will need to be sensible.</li>

</ul>

Using these charting libraries will typically require examining the online documentation for the library and transforming your data into a form needed by the charting function.




<h1>Testing</h1>

Every year students lose many easy marks because they didn’t read the requirements carefully enough. When your assignment is getting close to done, I would recommend going through each requirement step and carefully evaluate whether your assignment satisfies each specified requirement.