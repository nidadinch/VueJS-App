<template>


  <div>
    <table>
      <tr>
        <th>Sensor No</th>
        <th>Sıcaklık</th>
        <th>Nem</th>
        <th>CO2</th>
        <th>Basınç</th>
      </tr>
    </table>


    <table v-for="(value,sensor) in sensors" v-bind:key="sensor">
      <tr>
        <td> {{sensor}} </td>
        <td> {{value.t}}</td>
        <td> {{value.h}}</td>
        <td> {{value.co2}}</td>
        <td> {{value.p}}</td>
      </tr>
    </table>

<div><ul>
  <!-- <li v-for="(value,key) in list" v-bind:key="key">{{ value }} : {{value.t}}  {{value.h}}%  {{value.co2}} </li>
  <li v-for="value in sensor1" v-bind:key="value">{{ key }} : {{value}}</li> -->

</ul></div>

    <!--
    <md-table v-for="item in list" v-bind:key="item" :table-header-color="tableHeaderColor">
      <md-table-row >
        <md-table-cell style="white-space: nowrap;" md-label="Sensör" >{{ item.time }}</md-table-cell>
        <md-table-cell  md-label="Ölçüm">{{ item.t }}</md-table-cell>
        <md-table-cell style="white-space: nowrap;" md-label="Ölçüm Aralığı">{{ item.h }}</md-table-cell>
        <md-table-cell style="white-space: nowrap;" md-label="Alarm - Sıcaklık">{{item.co2}}</md-table-cell>
        <md-table-cell style="white-space: nowrap;" md-label="Alarm - Nem">{{ item.alarm2 }}</md-table-cell>
        <md-table-cell style="white-space: nowrap;" md-label="Batarya">{{ item.battery }}</md-table-cell>
        <md-table-cell style="white-space: nowrap;" md-label="Çekim Gücü">{{ item.cekim }}</md-table-cell>
        <md-table-cell style="white-space: nowrap;" md-label="Grafik">{{ item.graph }}</md-table-cell>
      </md-table-row>
    </md-table>-->


  </div>
</template>
<style>
.content table td, .content table th{
  width:120px;
  text-align: center !important;
}
</style>
<script>
import {SimpleTable} from "@/components";
import vue from "vue";

var axios = require("axios");

/* var sensor1 = [];


var config = {
    method: 'post',
    url: 'http://localhost:3000/acs/updatedData',
    data: "{\"currData\":1,\"alarms\":1}",
  };
  axios(config)
      .then((response)=>
      {
        var theKey = 'currData';
        var secondKey = '1053397';
        sensor1 = (response.data[theKey][secondKey]);
        console.warn(sensor1)
      })

const index = indexWhere(sensor1, item => item.value === '1053397')
function  indexWhere(array, conditionFn) {
  const item = array.find(conditionFn)
  return array.indexOf(item)
}
//console.warn(index)
*/
export default {
  name: "sensors",
  data() {
    return {
      sensors:[],
    }

  },
  methods: {
    pressures : function () {
      return this.sensors[0];
      console.warn(this.sensors[0])
    }
  },



  mounted() {
    var config = {
      method: 'post',
      url: 'http://localhost:3000/acs/updatedData',
      data: "{\"currData\":1,\"alarms\":1}",
    };
    axios(config)
      .then((response)=>
      {
        var theKey = 'currData';
        var secondKey = '1053397';
        this.sensors = JSON.parse(JSON.stringify(response.data[theKey]));

        var firstKey = Object.keys(this.sensors)[1];
        console.warn(this.sensors[firstKey]);
        delete(this.sensors['missing']);
        delete(this.sensors['paired']);
        delete(this.sensors['lastRx']);


        console.log(this.sensors);
        this.pressures();
        console.warn(this.sensors);
      })
  },


  /* methods: {
    firstThree(object){
      var object = object.substr(0,3);
    }
  }*/
}

</script>
