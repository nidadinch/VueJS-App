<template>
  <div class="content">
    <div class="md-layout">
      <div
        class="md-layout-item md-medium-size-100 md-xsmall-size-100 md-size-100"
      >
       <md-card>
          <md-card-header data-background-color="green">
            <h3 class="title">Sensörler </h3>
            <p class="category"></p>
          </md-card-header>
          <md-card-content>
            <simple-table table-header-color="green"></simple-table>
          </md-card-content>
        </md-card>
      </div>

        <div
            class="md-layout-item md-medium-size-100 md-xsmall-size-100 md-size-100"
        >
        <a class="weatherwidget-io" href="https://forecast7.com/tr/36d9030d71/antalya/" data-label_1="ANTALYA" data-label_2="Hava Durumu" data-font="Roboto" data-icons="Climacons Animated" data-days="5" data-theme="pillows" data-textcolor="#43a047" data-cloudcolor="#43a047" >ANTALYA Hava Durumu - Lütfen Sayfayı Yenileyin</a>

       <md-card>
          <div class="alert alert-danger">
            <button type="button" aria-hidden="true" class="close">
              ×
            </button>
            <span><b> TARIMSAL UYARILAR !  -  </b> Şu anda herhangi bir tarımsal uyarı bulunmamaktadır.
            </span>
          </div>
        </md-card>
      <!--  <sensor-datas></sensor-datas> -->

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
import SensorDatas from "@/pages/SensorDatas";
import {
SimpleTable
} from "@/components";

export default {

  components: {
    /*SensorDatas,*/
     SimpleTable
  },
  name: 'RegularToolbar',
}
!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0];if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src='https://weatherwidget.io/js/widget.min.js';fjs.parentNode.insertBefore(js,fjs);}}(document,'script','weatherwidget-io-js');</script>
