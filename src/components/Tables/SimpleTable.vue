<template>
  <div>
    <md-table v-model="users" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="Sensör">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Sıcaklık">{{ item.temperature }}</md-table-cell>
        <md-table-cell md-label="Nem">{{ item.humidity }}</md-table-cell>
        <md-table-cell md-label="Batarya">{{ item.battery }}</md-table-cell>
        <md-table-cell md-label="Çekim Gücü">{{ item.cekim }}</md-table-cell>
        <md-table-cell md-label="Ölçüm">{{ item.interval }}</md-table-cell>
        <md-table-cell md-label="Alarm - Sıcaklık">{{ item.alarm1 }}</md-table-cell>
        <md-table-cell md-label="Alarm - Nem">{{ item.alarm2 }}</md-table-cell>
        <md-table-cell md-label="Grafik">{{ item.graph }}</md-table-cell>



      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: "simple-table",
  props: {
    tableHeaderColor: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      selected: [],
      users: [
        {
          name: "Ipv64",
          temperature: "17.9 C",
          humidity: "%49",
          battery: "%96",
          cekim: "2/4",
          interval: "10 dk",
          alarm1: "16 - 40 C",
          alarm2: "%16 - %70 ",
          graph: "Oud-Turnhout"
        },
        {
          name: "Ipv64",
          temperature: "17.9 C",
          humidity: "%49",
          battery: "%96",
          cekim: "2/4",
          interval: "10 dk",
          alarm1: "16 - 40 C",
          alarm2: "%16 - %70 ",
          graph: "Oud-Turnhout"
        },
        {
          name: "Ipv64",
          temperature: "17.9 C",
          humidity: "%49",
          battery: "%96",
          cekim: "2/4",
          interval: "10 dk",
          alarm1: "16 - 40 C",
          alarm2: "%16 - %70 ",
          graph: "Oud-Turnhout"
        },
        {
          name: "Ipv64",
          temperature: "17.9 C",
          humidity: "%49",
          battery: "%96",
          cekim: "2/4",
          interval: "10 dk",
          alarm1: "16 - 40 C",
          alarm2: "%16 - %70 ",
          graph: "Oud-Turnhout"
        },
        {
          name: "Ipv64",
          temperature: "17.9 C",
          humidity: "%49",
          battery: "%96",
          cekim: "2/4",
          interval: "10 dk",
          alarm1: "16 - 40 C",
          alarm2: "%16 - %70 ",
          graph: "Oud-Turnhout"
        },
        {
          name: "Ipv64",
          temperature: "17.9 C",
          humidity: "%49",
          battery: "%96",
          cekim: "2/4",
          interval: "10 dk",
          alarm1: "16 - 40 C",
          alarm2: "%16 - %70 ",
          graph: "Oud-Turnhout"
        }
      ]
    };
  }
};
</script>
