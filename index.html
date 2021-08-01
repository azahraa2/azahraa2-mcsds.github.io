<!DOCTYPE html>
<html style="background-color:Ivory;">
<head>
<style>
select {
  position: absolute;
  left: 50px;
  top: 100px;
}
h3 {
  position: absolute;
  left: 120px;
  top: 80px;
  color: #660000;
}

h4 {
  position: absolute;
  left: 120px;
  top: 120px;
}
.toolTip {
  position: absolute;
  display: none;
  min-width: 80px;
  height: auto;
  width: auto;
  background: rgba(0,0,0,0.6);
  visibility: hidden
  border-radius: 4px;
  padding: 10px;
  text-align: center;
  color: #fff;
  z-index: 10;
}
</style>
</head>
<body>
<meta charset="utf-8">

<!-- Load d3.js -->
<script src="https://d3js.org/d3.v4.js"></script>

<div class="header">
  <h1 style="text-align:center">CO2 Emissions per year (Top 20 countries)</h1>
</div>


<!-- Initialize a select button -->
<select id="selectButton"></select>

<div class="header">
  <h3 style="text-align:center">Make a selection from the dropdown list to view data for the selected year.</h3>
</div>

<div class="header">
  <h4 style="text-align:center">The bar chart below shows the top 20 countries and their total CO2 emissions for the selected year. <br> 
  Hover over the bars for more information related to the country's CO2 data.</h4>
</div>


<!-- Color Scale -->
<script src="https://d3js.org/d3-scale-chromatic.v1.min.js"></script>





<!-- Create a div where the graph will take place -->
<div id="my_dataviz"></div>

<script>

// set the dimensions and margins of the graph
var margin = {top: 160, right: 200, bottom: 100, left: 200},
    width = 1200 - margin.left - margin.right,
    height = 600 - margin.top - margin.bottom;

// append the svg object to the body of the page
var svg = d3.select("#my_dataviz")
  .append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
  .append("g")
    .attr("transform",
          "translate(" + margin.left + "," + margin.top + ")");

var tooltip = d3.select("body").append("div").attr("class", "toolTip");

//Read the data
var data = d3.csv("https://raw.githubusercontent.com/owid/co2-data/master/owid-co2-data.csv", function(data) {

  var data = data.filter(function(d){ return d.iso_code != "" && d.iso_code != "OWID_WRL"})

  // var data =  // sort data
  // data.sort(function(b, a) {
  //   return a.co2 - b.co2;
  // }).slice(0,780);

// List of groups (here I have one group per column)
    // var allGroup = d3.map(data, function(d){return(d.year)}).keys()
    var allGroup = [];
    for (var i = 2019; i >= 1720; i--) {
        allGroup.push(i);
}

    // add the options to the button
    d3.select("#selectButton")
      .selectAll('myOptions')
      .data(allGroup)
      .enter()
      .append('option')
      .text(function (d) { return d; }) // text showed in the menu
      .attr("value", function (d) { return d; }) // corresponding value returned by the button

    // A color scale: one color for each group
    var myColor = d3.scaleOrdinal()
      .domain(allGroup)
      .range(d3.schemeSet2);

  var currData = data.filter(function(d){return d.year==allGroup[0]})
  .sort(function(b, a) {
    return a.co2 - b.co2;
  }).slice(0,20);

// Add X axis
  var x = d3.scaleLinear()
    .domain([0, 13000])
    .range([ 0, width]);
  svg.append("g")
    .attr("transform", "translate(0," + height + ")")
    .call(d3.axisBottom(x))
    .selectAll("text")
      .attr("transform", "translate(-10,0)rotate(-45)")
      .style("text-anchor", "end");

  svg.append("text")
    .attr("class", "x label")
    .attr("text-anchor", "end")
    .attr("x", 0.6*width)
    .attr("y", height + 50)
    .text("Total CO2 emissions");
  svg.append("text")
    .attr("class", "y label")
    .attr("text-anchor", "end")
    .attr("x", -0.5*height)
    .attr("y", -100)
    .attr("dy", ".75em")
    .attr("transform", "rotate(-90)")
    .text("Country");

  // Y axis
  var y = d3.scaleBand()
    .range([ 0, height ])
    .domain(currData.map(function(d) { return d.country; }))
    .padding(.1);
  svg.append("g")
    .call(d3.axisLeft(y))

  

  //Bars
  // var bars = svg.selectAll("myRect")
  //   .data(currData)
  //   .enter()
  //   .append("rect")
  //   .attr("x", x(0) )
  //   .attr("y", function(d) { return y(d.country); })
  //   .attr("width", function(d) { return x(d.co2); })
  //   .attr("height", y.bandwidth() )
  //   .attr("fill", "#69b3a2")
    var bars = svg.selectAll("myRect")
    .data(currData)
    .enter()
    .append("rect")
    .attr("class", "bar")
    .on("mouseover", onMouseOver)
    .on("mousemove", function(d){
            tooltip
              .style("left", d3.event.pageX - 50 + "px")
              .style("top", d3.event.pageY - 70 + "px")
              .style("display", "inline-block")
              .html("Emission: " + (parseInt(d.co2).toLocaleString("en")) + " | " + "Consumption: " + (parseInt(d.consumption_co2).toLocaleString("en")) + "<br>" + "Population: " + (parseInt(d.population).toLocaleString("en")) + " | " + "Emission per capita: " + (parseInt(d.co2_per_capita).toLocaleString("en")));
        })
    .on("mouseout", function(d){ tooltip.style("display", "none");
                                  d3.select(this).attr('class', 'bar');
                                        d3.select(this)
                                          .transition()
                                          .duration(400)
                                          .attr("opacity", 0.6);})
    .attr("x", x(0) )
    .attr("y", function(d) { return y(d.country); })
    .attr("width", function(d) { return x(0); })
    .attr("height", y.bandwidth() )
    .attr("fill", "#e68a19")
    .attr("opacity", 0.6)

    svg.selectAll("rect")
  .transition()
  .duration(600)
  .attr("x", function(d) { return x(0); })
  .attr("width", function(d) { return x(d.co2); })
  .delay(function(d,i){console.log(i) ; return(i*100)})

  svg.append("text")
     .attr('class', 'val') // add class to text label
     .attr('x', function() {
         return 100;
     })
     .attr('y', function() {
         return y(currData[0].country) - 20;
     })
     .text(function() {
         return [currData[0].country] + " is the country with most CO2 emissions in the year " + [currData[0].year] + "!";  // Value of the text
     });
    

    // A function that update the chart
    function update(selectedGroup) {

      // Create new data with the selection?
      // var dataFilter = data.filter(function(d){return d.year==selectedGroup})
  svg.selectAll('rect').remove();
  svg.selectAll('g').remove();
  svg.selectAll('text').remove();
  svg.selectAll('myRect').remove();
  svg.selectAll('svg').remove();
  

  var currData = data.filter(function(d){return d.year==selectedGroup})
  .sort(function(b, a) {
    return a.co2 - b.co2;
  }).slice(0,20);

// Add X axis
  var x = d3.scaleLinear()
    .domain([0, 13000])
    .range([ 0, width]);
  svg.append("g")
    .attr("transform", "translate(0," + height + ")")
    .call(d3.axisBottom(x))
    .selectAll("text")
      .attr("transform", "translate(-10,0)rotate(-45)")
      .style("text-anchor", "end");


  // Y axis
  var y = d3.scaleBand()
    .range([ 0, height ])
    .domain(currData.map(function(d) { return d.country; }))
    .padding(.1);
  svg.append("g")
    .call(d3.axisLeft(y))

  svg.append("text")
    .attr("class", "x label")
    .attr("text-anchor", "end")
    .attr("x", 0.6*width)
    .attr("y", height + 50)
    .text("Total CO2 emissions");
  svg.append("text")
    .attr("class", "y label")
    .attr("text-anchor", "end")
    .attr("x", -0.5*height)
    .attr("y", -100)
    .attr("dy", ".75em")
    .attr("transform", "rotate(-90)")
    .text("Country");

  //Bars
  var bars = svg.selectAll("myRect")
    .data(currData)
    .enter()
    .append("rect")
    .attr("class", "bar")
    .on("mouseover", onMouseOver)
    .on("mousemove", function(d){
            tooltip
              .style("left", d3.event.pageX - 50 + "px")
              .style("top", d3.event.pageY - 70 + "px")
              .style("display", "inline-block")
              .html("Emission: " + (parseInt(d.co2).toLocaleString("en")) + " | " + "Consumption: " + (parseInt(d.consumption_co2).toLocaleString("en")) + "<br>" + "Population: " + (parseInt(d.population).toLocaleString("en")) + " | " + "Emission per capita: " + (parseInt(d.co2_per_capita).toLocaleString("en")));
        })
    .on("mouseout", function(d){ tooltip.style("display", "none");
                                  d3.select(this).attr('class', 'bar');
                                        d3.select(this)
                                          .transition()
                                          .duration(400)
                                          .attr("opacity", 0.6);})
    .attr("x", x(0) )
    .attr("y", function(d) { return y(d.country); })
    .attr("width", function(d) { return x(0); })
    .attr("height", y.bandwidth() )
    .attr("fill", "#e68a19")
    .attr("opacity", 0.6)

    svg.selectAll("rect")
  .transition()
  .duration(600)
  .attr("x", function(d) { return x(0); })
  .attr("width", function(d) { return x(d.co2); })
  .delay(function(d,i){console.log(i) ; return(i*100)})

    svg.append("text")
     .attr('class', 'val') // add class to text label
     .attr('x', function() {
         return 100;
     })
     .attr('y', function() {
         return y(currData[0].country) - 20;
     })
     .text(function() {
         return [currData[0].country] + " is the country with most CO2 emissions in the year " + [currData[0].year] + "!";  // Value of the text
     });

    //   // Give these new data to update line
    //   line
    //       .datum(dataFilter)
    //       .transition()
    //       .duration(1000)
    //       .attr("d", d3.line()
    //         .x(function(d) { return x(d.year) })
    //         .y(function(d) { return y(+d.co2) })
    //       )
    //       .attr("stroke", function(d){ return myColor(selectedGroup) })
    }


    // When the button is changed, run the updateChart function
    d3.select("#selectButton").on("change", function(d) {
        // recover the option that has been chosen
        var selectedOption = d3.select(this).property("value")
        // run the updateChart function with this selected option
        update(selectedOption)
    })

function onMouseOver(d, i) {
    
    d3.select(this).attr('class', 'highlight');
    d3.select(this)
      .transition()
      .duration(400)
      .attr("opacity", 1);

    // svg.append("text")
    //  .attr('class', 'val') // add class to text label
    //  .attr('x', function() {
    //      return x(d.co2) + 10;
    //  })
    //  .attr('y', function() {
    //      return y(d.country) + 19;
    //  })
    //  .text(function() {
    //      return [d.co2];  // Value of the text
    //  });
}

function onMouseOut(d, i) {
        d3.select(this).attr('class', 'bar');
        d3.select(this)
          .transition()
          .duration(400)
          .attr("opacity", 0.6);

        // d3.selectAll('.val')
        //   .remove()
    }

})



</script>
</html>