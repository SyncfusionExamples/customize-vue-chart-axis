<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle"
    :primaryYAxis="chartPrimaryYAxis">
      <e-series-collection>
        <e-series type="Column" :dataSource="chartData" xName="days" yName="temperature"></e-series>
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, ColumnSeries, Category } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {chart : [ColumnSeries, Category ]},
  data() {
    return {
      chartPrimaryYAxis : { 
        isInversed : true,
        opposedPosition : true,
        majorTickLines : {
          color : 'red',
          width : 5
        },
        majorGridLines : {
          color : 'blue',
          width : 1
       },
       title : 'Temperature',
	   labelFormat : " {value} F", 
      },
      chartTitle : 'Weather Statistics',
      chartPrimaryXAxis : {
        valueType : 'Category',
        majorTickLines : {
          color : 'red',
          width : 5
        },
        majorGridLines : {
          color : 'blue',
          width : 1
       },
       title : 'Days of the Week'
      },
      chartData : [
        { days : "Sunday", temperature : 35  },
        { days : "Monday" , temperature : 40 },
        { days : "Tuesday",  temperature : 80 },
        { days : "Wednesday" , temperature : 70 },
        { days : "Thursday", temperature : 65 },
        { days : "Friday", temperature : 55 },
        { days : "Saturday", temperature : 50 }
      ]
    };
  }
}
</script>




<!-- <template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle"
    :primaryYAxis="chartPrimaryYAxis" :axes="chartAxes">
      <e-series-collection>
        <e-series type="Column" :dataSource="chartData" xName="days" yName="temperature"></e-series>
        <e-series type="Line" :dataSource="chartData" xName="days" yName="temperature1"
        :marker="chartMarker" yAxisName="yAxis1" ></e-series>
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, ColumnSeries, Category, LineSeries } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {chart : [ColumnSeries, Category, LineSeries ]},
  data() {
    return {
      chartAxes : [
        {
          title: 'Temperature (Celsius)',
          name : 'yAxis1',
          minimum: -18, maximum: 38, interval: 10,
          opposedPosition : true,
          labelFormat: '{value} °C'
        }
      ],
      chartMarker : { visible: true, height: 10, width: 10, border: { width: 2, color: '#F8AB1D' }},
      chartPrimaryYAxis : { 
       title : 'Temperature',
       labelFormat : " {value} F", 
       minimum: 0, maximum: 100, interval: 20,
       crossesAt : 2
      },
      chartTitle : 'Weather Statistics',
      chartPrimaryXAxis : {
        valueType : 'Category',
        title : 'Days of the Week',
        crossesAt : 30
      },
      chartData : [
        { days : "Sunday", temperature : 35, temperature1 : 2 },
        { days : "Monday" , temperature : 40, temperature1 : 4 },
        { days : "Tuesday",  temperature : 80, temperature1 : 27 },
        { days : "Wednesday" , temperature : 70, temperature1 : 21 },
        { days : "Thursday", temperature : 65, temperature1 : 18 },
        { days : "Friday", temperature : 55, temperature1 : 13 },
        { days : "Saturday", temperature : 50, temperature1 : 10 }
      ]
    };
  }
}
</script>




 -->
