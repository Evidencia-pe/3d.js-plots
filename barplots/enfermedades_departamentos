<!-- Load d3.js -->
<script src="https://d3js.org/d3.v4.js"></script>

<!-- Add 2 buttons -->
<button onclick="update(data1)">Malaria</button>
<button onclick="update(data2)">Dengue</button>
<button onclick="update(data3)">Tuberculosis</button>

<!-- Create a div where the graph will take place -->
<div id="my_dataviz"></div>

<script>

// create 2 data_set
var data1 = [
	{group: "Amazonas", value: 9.8},
	{group: "Arequipa", value: 0},
	{group: "Cajamarca", value: 0},
	{group: "Callao", value: 0},
	{group: "Cuzco", value: 0.5},
	{group: "Ica", value: 0},
	{group: "Junín", value: 3.3},
	{group: "La Libertad", value: 0},
	{group: "Lima", value: 0},
	{group: "Loreto", value: 84.7},
	{group: "Piura", value: 0},
	{group: "San Martín", value: 0.9},
	{group: "Ucayali", value: 0}
];

var data2 = [
	{group: "Amazonas", value: 0},
	{group: "Arequipa", value: 0},
	{group: "Cajamarca", value: 0},
	{group: "Callao", value: 0},
	{group: "Cuzco", value: 0},
	{group: "Ica", value: 14.9},
	{group: "Junín", value: 7.8},
	{group: "La Libertad", value: 0},
	{group: "Lima", value: 0},
	{group: "Loreto", value: 16.3},
	{group: "Piura", value: 0},
	{group: "San Martín", value: 10.3},
	{group: "Ucayali", value: 20.4}
];

var data3 = [
	{group: "Amazonas", value: 0},
	{group: "Arequipa", value: 0},
	{group: "Cajamarca", value: 0},
	{group: "Callao", value: 5.2},
	{group: "Cuzco", value: 0},
	{group: "Ica", value: 0},
	{group: "Junín", value: 0},
	{group: "La Libertad", value: 4.10},
	{group: "Lima", value: 52.5},
	{group: "Loreto", value: 6.20},
	{group: "Piura", value: 0},
	{group: "San Martín", value: 0},
	{group: "Ucayali", value: 4.10}
];

// set the dimensions and margins of the graph
var margin = {top: 30, right: 30, bottom: 70, left: 60},
    width = 700 - margin.left - margin.right,
    height = 400 - margin.top - margin.bottom;

// append the svg object to the body of the page
var svg = d3.select("#my_dataviz")
  .append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
  .append("g")
    .attr("transform",
          "translate(" + margin.left + "," + margin.top + ")");

// X axis
var x = d3.scaleBand()
  .range([ 0, width ])
  .domain(data1.map(function(d) { return d.group; }))
  .padding(0.2);
svg.append("g")
  .attr("transform", "translate(0," + height + ")")
  .call(d3.axisBottom(x))

// Add Y axis
var y = d3.scaleLinear()
  .domain([0, 100])
  .range([ height, 0]);
svg.append("g")
  .attr("class", "myYaxis")
  .call(d3.axisLeft(y));

// A function that create / update the plot for a given variable:
function update(data) {

  var u = svg.selectAll("rect")
    .data(data)

  u
    .enter()
    .append("rect")
    .merge(u)
    .transition()
    .duration(1000)
      .attr("x", function(d) { return x(d.group); })
      .attr("y", function(d) { return y(d.value); })
      .attr("width", x.bandwidth())
      .attr("height", function(d) { return height - y(d.value); })
      .attr("fill", "#b53838")
}

// Initialize the plot with the first dataset
update(data1)

</script>
