# d3.simple.chart

### About
Very small and easy library for quick creation of simple line charts on d3.js.

### How to use
#### Step 1. Load and prepare data
```js
    d3.tsv("sample.tsv", function(error, data) {
      if (error) throw error;
      // parse date and numeric data before build chart
      d3sPreParceDann("Date","%d.%m.%Y",["Metal month","Mined %"],data);
      ...
    }
```
#### Step 2. Init param
```js
      //initialize params of the chart
      var param = {
        parentSelector: "#chart1",
        width: 600,  // if 0 then get parent width
        height: 300, // if 0 then get parent height
        title: "Iron mine work",
        xColumn: "Date",
        xColumnDate: true,
        xAxisName: "Date work",
        yLeftAxisName: "Tonnes",
        yRightAxisName: "%",
        categories: [
          {name: "plan", width: "1px"},
          {name: "fact", width: "2px"}
        ],
        series: [
          {yColumn: "Metal month", title: "Metal in moth", color: "#ff6600", yAxis: "left"},
          {yColumn: "Mined %", title: "Mined proc.", color: "#0080ff", yAxis: "right"}
        ]
      };
```
#### Step 3. Create chart
```js
      // build chart
      d3sChart(param,data,dataGroup);
```
### Example of chart
![Example of chart](https://cloud.githubusercontent.com/assets/20028214/16200289/8118c198-372e-11e6-89b5-da5072c648da.png)

### Licence
BSD.
