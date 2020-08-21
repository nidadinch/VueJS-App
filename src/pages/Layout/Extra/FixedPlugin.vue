<template>
  <div class="fixed-plugin" v-click-outside="closeDropDown">
    <div class="dropdown show-dropdown" :class="{ show: isOpen }">
      <a data-toggle="dropdown">
        <i class="fa fa-cog fa-2x" @click="toggleDropDown"> </i>
      </a>
      <ul class="dropdown-menu" :class="{ show: isOpen }">
        <li class="header-title">Menü Rengi</li>
        <li class="adjustments-line text-center">
          <span
            v-for="item in sidebarColors"
            :key="item.color"
            class="badge filter"
            :class="[`badge-${item.color}`, { active: item.active }]"
            :data-color="item.color"
            @click="changeSidebarBackground(item)"
          >
          </span>
        </li>
        <li class="header-title">Arkaplan</li>
        <li
          v-for="item in sidebarImages"
          :key="item.image"
          :class="{ active: item.active }"
          @click="changeSidebarImage(item)"
        >
          <a class="img-holder switch-trigger">
            <img :src="item.image" alt="" />
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import Vue from "vue";
import SocialSharing from "vue-social-sharing";
import VueGitHubButtons from "vue-github-buttons";
import "vue-github-buttons/dist/vue-github-buttons.css";

Vue.use(SocialSharing);
Vue.use(VueGitHubButtons, { useCache: true });
export default {
  data() {
    return {
      documentationLink:
        "https://creativetimofficial.github.io/vue-material-dashboard/documentation",
      shareUrl: "https://www.creative-tim.com/product/vue-material-dashboard",
      buyUrl: "",
      freeUrl: "https://www.creative-tim.com/product/vue-material-dashboard",
      isOpen: false,
      sidebarColors: [
        { color: "purple", active: false },
        { color: "blue", active: false },
        { color: "green", active: true },
        { color: "orange", active: false },
        { color: "red", active: false }
      ],
      sidebarImages: [
        { image: require("@/assets/img/sidebar-1.jpg"), active: false },
        { image: require("@/assets/img/sidebar-2.jpg"), active: true },
        { image: require("@/assets/img/sidebar-3.jpg"), active: false },
        { image: require("@/assets/img/sidebar-4.jpg"), active: false }
      ]
    };
  },
  methods: {
    toggleDropDown() {
      this.isOpen = !this.isOpen;
    },
    closeDropDown() {
      this.isOpen = false;
    },
    toggleList(list, itemToActivate) {
      list.forEach(listItem => {
        listItem.active = false;
      });
      itemToActivate.active = true;
    },


    changeSidebarBackground(item) {
      this.$emit("update:color", item.color);
      this.toggleList(this.sidebarColors, item);
    },
    changeSidebarImage(item) {
      this.$emit("update:image", item.image);
      this.toggleList(this.sidebarImages, item);
    }
  }
};
</script>
