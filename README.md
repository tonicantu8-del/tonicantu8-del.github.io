<!DOCTYPE html>
<html lang="es">

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Dashboard CONEVAL - Pobreza en México</title>

<script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>

<style>

body{
    font-family: Arial, sans-serif;
    background:#f4f6f9;
    margin:20px;
}

h1{
    text-align:center;
    color:#2c3e50;
}

.dashboard{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:20px;
}

.chart{
    background:white;
    padding:10px;
    border-radius:10px;
    box-shadow:0px 2px 5px rgba(0,0,0,0.2);
}

.chart-full{
    grid-column:1/3;
}

</style>

<script>

google.charts.load('current', {'packages':['corechart','bar']});
google.charts.setOnLoadCallback(drawCharts);

function drawCharts(){

// --------------------
// GRAFICO 1
// --------------------

var data1 = google.visualization.arrayToDataTable([
['Año','Pobreza (%)'],
['2008',44.4],
['2010',46.1],
['2012',45.5],
['2014',46.2],
['2016',43.6],
['2018',41.9]
]);

var options1 = {
title:'Evolución de la pobreza en México',
curveType:'function',
legend:{position:'bottom'}
};

var chart1 = new google.visualization.LineChart(
document.getElementById('graf1'));

chart1.draw(data1,options1);


// --------------------
// GRAFICO 2
// --------------------

var data2 = google.visualization.arrayToDataTable([
['Año','Pobreza extrema (%)'],
['2008',11.0],
['2010',11.3],
['2012',9.8],
['2014',9.5],
['2016',7.6],
['2018',7.4]
]);

var options2 = {
title:'Pobreza extrema',
legend:{position:'none'}
};

var chart2 = new google.visualization.ColumnChart(
document.getElementById('graf2'));

chart2.draw(data2,options2);


// --------------------
// GRAFICO 3
// --------------------

var data3 = google.visualization.arrayToDataTable([
['Periodo','Porcentaje'],
['2008',65.0],
['2018',57.3]
]);

var options3 = {
title:'Carencia de acceso a seguridad social'
};

var chart3 = new google.visualization.PieChart(
document.getElementById('graf3'));

chart3.draw(data3,options3);


// --------------------
// GRAFICO 4
// --------------------

var data4 = google.visualization.arrayToDataTable([
['Periodo','Porcentaje'],
['2008',21.7],
['2018',20.4]
]);

var options4 = {
title:'Carencia por acceso a alimentación'
};

var chart4 = new google.visualization.BarChart(
document.getElementById('graf4'));

chart4.draw(data4,options4);


// --------------------
// GRAFICO 5
// --------------------

var data5 = google.visualization.arrayToDataTable([
['Año','Millones de personas'],
['2008',49.5],
['2010',52.8],
['2012',53.3],
['2014',55.3],
['2016',53.4],
['2018',52.4]
]);

var options5 = {
title:'Personas en situación de pobreza (millones)',
legend:{position:'bottom'}
};

var chart5 = new google.visualization.AreaChart(
document.getElementById('graf5'));

chart5.draw(data5,options5);

}

</script>

</head>

<body>

<h1>Dashboard CONEVAL - Pobreza en México 2008-2018</h1>

<div class="dashboard">

<div class="chart">
<div id="graf1" style="width:100%; height:400px;"></div>
</div>

<div class="chart">
<div id="graf2" style="width:100%; height:400px;"></div>
</div>

<div class="chart">
<div id="graf3" style="width:100%; height:400px;"></div>
</div>

<div class="chart">
<div id="graf4" style="width:100%; height:400px;"></div>
</div>

<div class="chart chart-full">
<div id="graf5" style="width:100%; height:450px;"></div>
</div>

</div>

</body>
</html>
