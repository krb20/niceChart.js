# NiceChart.js
NiceChart.js is a charting library written in pure JavaScript, offering an easy way of adding interactive charts to your web application.<br />
NiceChart currently supports below types of charts:<br />
1. Line<br /> 
2. Bar<br />
3. MultiLine<br />
4. TrendLine and Gauge.<br />

NiceChart is based on SVG.

# advantages of using NiceChart.js
1. Reusable <br />
2. Scalable <br />
3. Provides easy configuration options to customize charts <br /> 
4. Creates dynamic charts <br />
5. Available in plug-in based version <br />
6. All modern browser support <br />
7. Lightweight in size – few KB after compression.

# How to use NiceChart in web page ? It's easy..

Include ```nicechart.master.1.1.js``` file in your page.<br />
Add SVG tag in HTML page for Chart <br />
```
<svg id="myChart">
</svg>
```
Create instance of NiceChart and pass chart type, DOM Id & Input data as shown below:
```
var Data = ["Jan,2000", "Feb,1100" ,"Mar,1500", "Apr,1700" ,"May,2200", "Jun,2300",
"July,1500" ,"Aug,1950" ,"Sep,1970" ,"Oct,2500" ,"Nov,1860" ,"Dec,1920"];

var chart = new NiceChart('Bar', {
    renderHere : 'myChart',
    input : Data
}).render();
```
