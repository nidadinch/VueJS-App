<template>
  <div class="wrapper" :class="{ 'nav-open': $sidebar.showSidebar }">
    <notifications></notifications>

    <side-bar
      :sidebar-item-color="sidebarBackground"
      :sidebar-background-image="sidebarBackgroundImage"
    >
      <mobile-menu slot="content"></mobile-menu>
      <sidebar-link to="/dashboard">
        <md-icon>home</md-icon>
        <p>Anasayfa</p>
      </sidebar-link>
      <sidebar-link to="/notifications">
        <md-icon>show_chart</md-icon>
        <p>Grafik</p>
      </sidebar-link>
      <sidebar-link to="/maps">
        <md-icon>notifications</md-icon>
        <p>Bildirimler</p>
      </sidebar-link>
      <sidebar-link to="/table">
        <md-icon>content_paste</md-icon>
        <p>Sensörler</p>
      </sidebar-link>
   <!--   <sidebar-link to="/typography">
        <md-icon>settings</md-icon>
        <p>Sistem</p>
      </sidebar-link>
      <sidebar-link to="/icons">
        <md-icon>home_repair_service</md-icon>
        <p>Servisler</p>
      </sidebar-link>
      <sidebar-link to="/maps">
        <md-icon>public</md-icon>
        <p>Ağ</p>
      </sidebar-link> -->
      <sidebar-link to="/user">
        <md-icon>person</md-icon>
        <p>Profil</p>
      </sidebar-link>
    </side-bar>

    <div class="main-panel">
      <top-navbar></top-navbar>

      <fixed-plugin
        :color.sync="sidebarBackground"
        :image.sync="sidebarBackgroundImage"
      >
      </fixed-plugin>

      <dashboard-content> </dashboard-content>

      <content-footer v-if="!$route.meta.hideFooter"></content-footer>
    </div>
  </div>
</template>

<script>
import TopNavbar from "./TopNavbar.vue";
import ContentFooter from "./ContentFooter.vue";
import DashboardContent from "./Content.vue";
import MobileMenu from "@/pages/Layout/MobileMenu.vue";
import FixedPlugin from "./Extra/FixedPlugin.vue";

export default {
  components: {
    TopNavbar,
    DashboardContent,
    ContentFooter,
    MobileMenu,
    FixedPlugin
  },
  data() {
    return {
      sidebarBackground: "green",
      sidebarBackgroundImage: require("@/assets/img/sidebar-2.jpg")
    };
  }
};
</script>
