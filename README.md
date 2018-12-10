# NiceChart.js
NiceChart.js is a charting library written in pure JavaScript, offering an easy way of adding interactive charts to your web application.<br />
NiceChart.js currently supports below types of charts:<br />
1. Line<br /> 
2. Bar<br />
3. MultiLine<br />
4. TrendLine <br />
5. Gauge. <br />

NiceChart is based on SVG.

# Advantages of using NiceChart.js
1. Reusable <br />
2. Scalable <br />
3. Provides easy configuration options to customize charts <br /> 
4. Creates dynamic charts <br />
5. Available in plug-in based version <br />
6. All modern browser support <br />
7. Lightweight in size – few KB after compression.

# How to use NiceChart in web page ? It's easy..

1. Include ```nicechart.master.1.1.js``` file in your page.<br />
2. Add SVG tag in HTML page for Chart <br />
```
<svg id="myChart">
</svg>
```
3. Create instance of NiceChart and pass chart type, DOM Id & Input data as shown below:
```
var Data = ["Jan,2000", "Feb,1100" ,"Mar,1500", "Apr,1700" ,"May,2200", "Jun,2300",
"July,1500" ,"Aug,1950" ,"Sep,1970" ,"Oct,2500" ,"Nov,1860" ,"Dec,1920"];

var chart = new NiceChart('Bar', {
    renderHere : 'myChart',
    input : Data
}).render();
```
# Screenshot of NiceChart Examples

![Alt text](/niceChart.jpg?raw=true "Optional Title")

# Plugins
If you like to use only specific chart in your application, you can use plugins availbale on top of base library: 

Add ``` nicechart.1.1.js [Base library]``` in your html page - It supports Line ans Bar Charts.<br />

You can can include plugins ```gauge.plugin.nicechart.1.1.js, multiline.plugin.nicechart.1.1.js, trendline.plugin.nicechart.1.1.js ``` in your html file based on your requirement.<br /><br />
Note: Plugins can be useful if you have memory/size contarins, and have no requirement of using all charts.

<h1 class="center-align">NiceChart Documentation</h1>
<h4 class="center-align">Version 1.1</h4>
<hr class="hr-dash" />
<h3>Configurations Options for charts:</h3>
<h4>Example:</h4>

```
var customChart = new NiceChart('Line', {
	renderHere : 'svgboxB',
	input : tmpData,
	axisStyle : {
	    axisColor : '#515256',
	    axisWidth : '1px',
	    axisYLabelCount : 8,
	    axisXTitle : 'Time in days',
	    axisYTitle : 'Energy (mwh)',
	    axisXLabelColor : 'green'
	},
	chartStyle : {
	    chartPlotColor:'red',
	    lineStrokeWidth:'5px',
	    chartPlotMargin : 20,
	    showToolTip : true,
	    toolTipSuffix : 'Kwh'              

	},
	animation : {
	    highLight : true,
	    animateLoad : false,
	animateReload : false
	}
});
customChart.render();
```
<h3>Input Format:</h3>

Line/Bar:[Array]
 ```
["Jan,2000", "Feb,1100" ,"Mar,1500", "Apr,1700" ,"May,2200", "Jun,2300" ,"July,1500" ,"Aug,1950" ,"Sep,1970" ,"Oct,2500" ,"Nov,1860" ,"Dec,1920"];
```
MultiLine:[Object]
```
{
label : ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
series : [
	{
	  name : 'Device1',
	  color  : 'red',
	  data : [100, 550, 400, 700, 500, 900, 1000]
	},
	{
	  name : 'Device2',
	  color  : '#F97D10',
	  data : [200, 450, 500, 800, 600, 1000, 1100]
	},
	{
	  name : 'Device3',
	  color  : '#950aa8',
	  data : [300, 700, 550, 850, 650, 1100, 1200]
	},{
	  name : 'Device6',
	  color  : 'green',
	  data : [500, 800, 650, 1000, 750, 750, 750]
	}
	]
}
```
TrendLine: [Object]
```
{
      data : ["Jan,2000", "Feb,1100" ,"Mar,1500", "Apr,1700" ,"May,2200", "Jun,2300" ,"July,1500" ,"Aug,1950" ,"Sep,1970" ,"Oct,2500"                  ,"Nov,1860" ,"Dec,1920"],          
      type : 'Line',  //Either 'Line' or 'Bar'
      trendline : [
        {
          label : 'High',
          color  : '#FDA915',
          value : 1700
        },
        {
          label : 'V High',
          color  : 'red',
          value : 2100
        }
      ]
    }
```
Gauge : [Object]
```
{
    gaugeVal : 70,
    minGaugeVal : 0,
    maxGaugeVal : 100
}
```
<h3>Configuration Object/Properties:</h3>
<h4>I] axisStyle - [Optional] - customizable style for chart axis.</h4>
<h4>Properties:</h4>

```
1. axisColor - [Optional] - color of axis. Default value- '#D8D8D8'. e.g.- 'green', '#fff000'.

2. axisWidth - [Optional] - width of axis. Default value- '1px'.

3. axisYLabelCount - [Optional] - Number of labels on Y-axis. Default value- auto calculating w.r.t. chart height. e.g.-10, 20.

4. axisXTitle - [Optional] - x-axis title. Default value- "". e.g. 'Years', 'Months'.

5. axisYTitle - [Optional] - y-axis title. Default value- "". e.g. 'KWh', 'Temperaure'.

6. axisXTitleColor - [Optional] - x-axis title color. Default value- "#000".

7. axisYTitleColor - [Optional] - y-axis title color. Default value- "#000".

8. axisXLabelColor - [Optional] - x-axis label color. Default value- "#000".

9. axisYLabelColor - [Optional] - y-axis label color. Default value- "#000".

10.axisXLabelTb - [Optional] - to place x-axis labels vertically aligned. Default value- false. Possible values- true/false.

11.axisXLabelSkipIndex - [Optional] - to skip lables on x axis. Default value- 1. To skip alernative lables, use 2. e.g.-2,3.

12.axisYTitleTb - [Optional] - to place y-axis tilte vertical/horizantal. Default value- true[vertical].

13.axisXTitleLMargin - [Optional] - to add left margin for x-axis title. Default value- 0.

```
<h4>II]  chartStyle - [Optional] - customizable style for chart.</h4>
<h4>Properties:</h4>	 

```
1.  chartWidth - [Optional] - width for chart. Default value- 450.

2.  chartHeight - [Optional] - width for chart. Default value- 300.

3.  chartMargin  - [Optional] - margin for chart. Default value- 30.

4.  chartPlotColor - [Optional] - color of chart. Default value- '#000'. e.g. - 'green', '#fff000'.

5.  lineStrokeWidth - [Optional] - Applicable to 'Line' chart only. width of line for chart. e.g.- '1px'.

6.  chartPlotMargin - [Optional] - Margin/Gap between bars/lines. Default value- 10.

7.  showToolTip - [Optional] - to show tooltip/title for chart against value. Default value- false. Possible values- true/false.

8.  toolTipPrefix - [Optional] - to configure tooltip prefix. Default value - ''.

9.  toolTipSuffix - [Optional] - to configure tooltip suffix. Default value - ''.

10. circleRadius - [Optional] - Applicable to 'Line' chart only. To configure radius of circle for Line chart. Default value -3.

11. chartBgColor - [Optional] - background color for chart. Default value - '#fff'.

12. chartBgLines - [Optional] - to add lines on chart background. Default value - false. Possible values- true/false.

13. chartBgLineColor - [Optional] - Chart background line color. Default value - '#D8D8D8'.

14. chartBgLineDotted- [Optional] - to make chart background line dotted. Default value - false.

15. toolTipColor  - [Optional] - tootip color. Default value - '#fff'.

16. toolTipBgColor  - [Optional] - tootip background color. Default value - '#000'.

17. showLegend - [Optional] - Applicable to 'MultiLine' chart only. To display legend for chart. Default value - false.

18. legendTitleColor- [Optional] - Applicable to 'MultiLine' chart only. color for legend title. Default value - '#000'.
```
<h4>Specific to Gauge Chart:</h4>

```
19. gaugeBgColor : [Optional] - Background color for gauge. Default value - '#fff'.

20. gaugeColor : [Optional] - Color for gauge curve. Default value - '#000'.

21. gaugeTitle : [Optional] - Title for gauge chart. Default value - ''.

22. gaugeTitleColor : [Optional] - Color title text. Default value - '#000'.

23. gaugeTitleFontSize : [Optional] - Font size for title text. Default value - '12px'.

24. gaugeTitleMargin : [Optional] - Margin(left-margin) for title . Default value - 30.

25. gaugeWidth : [Optional] - Width for gauge curve. Default value - 30.
```

<h4>III]   animation - [Optional] - customizable animation for chart.</h4>
<h4>Properties:</h4>

```
1. highLight - [Optional] - Applicable to 'Bar' chart only. To highlight chart on mouse over. Default value- false. Possible values- true/false.

2. animateLoad - [Optional] - animate charts[line/bar] when it loads. Default value- false. Possible values- true/false.

3. animateReload - [Optional] - opacity effects for charts[line/bar] when it loads. Could be usefull for dynamic charts. 
   Default value - false. Possible values- true/false.
```
<h3>Methods:</h3>

```
1. render()

	 render charts with configuration provided.

2. toggleChart()

	 Applicable to only 'Bar' and 'Line'. function to toggle charts between Line and Bar.

3. getChartType()

	 returns the current type of chart. e.g: "Bar" or "Line".

4. refreshChartData(input)

	 arguments-input, values- input array. format- ["1, 2000", "2, 1500", "3, 2500"]
	 refresh the chart with new values.

5. changeAxisTitles(titleX, titleY)

	 arguments-titleX, titleY.
	 dynamically modifies x, y axis titles.

6. resizeChart(w, h)

	 arguments-w, h.
	 dynamically renders chart with new width and height.
```
