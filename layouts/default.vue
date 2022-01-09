<template>
  <v-app dark>
    <v-app-bar
      flat
      fixed
      app
      color="#F2F2F2"
      height="95px"
      width="100%"
      class="header"
    >
      <img src="~/static/logo-shop.svg" alt="لوگو" />

      <div
        class="header-btn full-height d-flex flex-row align-center justify-space-between"
      >
        <div v-for="(item, index) in headerBtn" :key="index">
          <div
            class="font-18 pointer"
            @click="changeColor(index)"
            :class="selectedbtn == index ? 'selected-btn' : ''"
          >
            {{ item.name }}
          </div>
        </div>
      </div>

      <div class="d-flex flex-row">
        <div>
          <v-btn class="px-0" text
            ><v-badge class="ml-1 mb-6" color="primary" dot /><v-icon
              class="pl-3"
              >mdi-cart-outline</v-icon
            >کارت ها</v-btn
          >
        </div>

        <div class="mr-9">
          <v-btn class="px-0" text
            ><v-icon class="pl-3">mdi-account-circle-outline</v-icon>صفحه
            کاربری</v-btn
          >
        </div>
      </div>
    </v-app-bar>

    <v-main>
      <Nuxt />
    </v-main>

    <v-footer class="d-flex justify-center" height="274px" absolute app>
      <div class="d-flex flex-row justify-space-around" style="width:70%">
        <div class="d-flex flex-column">
          <img
            src="~/static/logo-shop.svg"
            alt="لوگو"
            width="138px"
            height="43px"
            class="mr-13"
          />
          <p class="font-12" style="width: 257px">
            متن درباره ما این قسمت قرار میگیردمتن درباره ما این قسمت قرار
            میگیردمتن درباره ما این قسمت قرار میگیردمتن درباره ما این قسمت قرار
            میگیردمتن درباره ما این قسمت قرار میگیردمتن درباره ما این قسمت قرار
            میگیردمتن درباره ما این قسمت قرار میگیردمتن درباره ما این قسمت قرار
            میگیردمتن درباره ما این قسمت قرار میگیردمتن درباره ما این قسمت قرار
            میگیردمتن درباره ما این قسمت قرار میگیرد
          </p>
        </div>

        <div class="d-flex flex-row full-width justify-space-around">
          <div class="d-flex flex-column">
            <a v-for="n in 5" :key="n">لینک سریع</a>
          </div>

          <div class="d-flex flex-column">
            <a v-for="n in 5" :key="n">لینک سریع</a>
          </div>

          <div class="d-flex flex-column">
            <a v-for="n in 5" :key="n">لینک سریع</a>
          </div>
        </div>

        <div>
          <p class="primary-text font-12 pr-3">شبکه های اجتماعی</p>
          <div class="d-flex flex-row">
            <v-icon color="primary" x-large>mdi-twitter</v-icon>
            <v-icon color="primary" x-large>mdi-whatsapp</v-icon>
            <v-icon color="primary" x-large>mdi-instagram</v-icon>
          </div>
        </div>
      </div>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

@Component({
  components: {},
  filters: {},
})
export default class Default extends Vue {
  [x: string]: any;
  private selectedbtn: number = 0;

  private changeColor(index: number) {
    this.selectedbtn = index;
  }

  private headerBtn = [
    { name: "صفحه اصلی" },
    { name: "اطراف من" },
    { name: "همگردی" },
    { name: "همبودشو" },
    { name: "ژورنال" },
    { name: "کسب و کار ها" },
  ];
}
</script>

<style lang="scss">
.header {
  .v-toolbar__content {
    width: 100% !important;
    justify-content: center;
    .header-btn {
      width: 34%;
      margin: 0 162px 0 65px;
      .selected-btn {
        color: #e47e7a;
      }
    }
  }
}
</style>
