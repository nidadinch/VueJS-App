<template>
  <div class="content">
    <div class="md-layout">
      <div
        class="md-layout-item md-medium-size-100 md-xsmall-size-100 md-size-100"
      >
        <md-card>
          <md-card-header data-background-color="green">
            <h4 class="title" style="font-weight:400;">Sensörler</h4>
            <p class="category"></p>
          </md-card-header>
          <md-card-content>
            <simple-table table-header-color="green"></simple-table>
          </md-card-content>
        </md-card>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .md-toolbar + .md-toolbar {
    margin-top: 16px;
  }
</style>
<script>
import axios from "axios";
import {
SimpleTable
} from "@/components";

export default {
/*
  data(){
    return {
      postList : []
    }
  },
  created(){
    customAxios.get("/sensor-datas.json")
      .then(response => {
        let data = response.data;
        for(let key in data){
          this.postList.push({ ...data[key], id : key })
        }
      })
      .catch(e => console.log(e))
  }, */
  components: {
    SimpleTable
  },
  name: 'RegularToolbar',
}
</script>
