<template>
  <div class="main full-width full-height mt-5 pb-8 d-flex flex-column align-center">
    <div class="text-center font-32">دسته بندی محصولات</div>
    <div class="d-flex flex-row justify-space-around mt-6 mb-10 half-width">
      <v-card
        class="category-card rounded-24 pointer"
        width="194px"
        height="160px"
        v-for="(item, index) in categoryCard"
        :key="index"
      >
        <div
          class="d-flex flex-column full-width full-height justify-center align-center"
        >
          <img :src="getImgUrl(item.image)" :alt="item.alt" />
          <div class="category-title font-24 pt-4">{{ item.title }}</div>
        </div>
      </v-card>
    </div>

    <div class="d-flex justify-center full-width full-height mt-10">
      <v-card
        class="rounded-24 select-category d-flex align-center"
        color="#E5E5E5"
        width="66%"
        height="60px"
      >
        <div class="font-24 pr-5">انتخاب دسته بندی</div>
        <div class="d-flex justify-space-between" style="width: 84%">
          <div class="input-width">
            <v-select
              label="انتخاب دسته‌بندی"
              class="rounded-24 mr-4"
              append-icon="mdi-chevron-down"
              :items="categoriesItem"
              item-text="title"
              hide-details
              solo
              dense
              flat
            ></v-select>
          </div>
          <div class="input-width">
            <v-text-field
              label="جستجو"
              class="rounded-24"
              append-icon="mdi-magnify"
              hide-details
              solo
              dense
              flat
            ></v-text-field>
          </div>
        </div>
      </v-card>
    </div>

    <div class="text-center font-32">خرید محصولات پرفروش</div>

    <div
      class="d-flex flex-row justify-space-around mt-6 mb-10"
      style="width: 67%"
    >
      <v-card
        class="category-card rounded-24 relative-position"
        width="280px"
        height="280px"
        v-for="(item, index) in 4"
        :key="index"
      >
        <div
          v-if="index == 1"
          class="absolute-position offer-badge white-text pr-2 font-14"
        >
          20% تخفیف
        </div>
        <div
          class="d-flex flex-column full-width full-height justify-center align-center"
        >
          <img src="~/static/best-sale.svg" alt="کیک" />

          <div class="d-flex flex-row pt-3">
            <div class="font-18">کیک شکلاتی -</div>
            <div class="font-18 primary-text">#65342</div>
          </div>

          <div class="text-center font-12 secondary-text">دسته‌بندی کیک</div>

          <v-card
            class="rounded-24 d-flex flex-row justify-space-between absolute-position"
            width="238px"
            height="35px"
            color="#E47E7A"
            style="bottom: -18px"
          >
            <v-btn
              text
              style="
                border-radius: 0px 24px 24px 0px;
                background-color: #b66562;
              "
              dark
              class="pb-1"
            >
              <v-icon color="#ffffff">mdi-plus</v-icon>
              خرید</v-btn
            >
            <div class="white-text pt-1 pl-5 font-18">25.000.000</div>
          </v-card>
        </div>
      </v-card>
    </div>

    <div class="d-flex justify-center">
      <div class="relative-position">
        <div
          class="absolute-position white-text font-32"
          style="width: 405px; right: 89px; top: 195px"
        >
          بهترین محصولات کیک و شیرینی را در فروشگاه ما تهیه کنید
        </div>
        <div class="absolute-position" style="right: 89px; top: 304px">
          <v-btn class="rounded-24 input-width" color="#e47e7a" dark>همین حالا خرید کنید</v-btn>
        </div>
        <img src="~/static/last-cake.svg" alt="blue-cake" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

@Component({
  components: {},
})
export default class Default extends Vue {
  private categoryCard = [
    {
      title: "شیرینی",
      image: "burger.svg",
      alt: "برگر",
    },
    {
      title: "ساندویچ",
      image: "cookies.svg",
      alt: "کوکی",
    },
    {
      title: "نان",
      image: "bread.svg",
      alt: "نان",
    },
    {
      title: "کیک",
      image: "cake.svg",
      alt: "کیک",
    },
  ];

  private categoriesItem = [
    {
      title: "شیرینی",
    },
    {
      title: "ساندویج",
    },
    {
      title: "نان",
    },
    {
      title: "کیک",
    },
  ];

  private getImgUrl(image: string) {
    return require("~/static/" + image);
  }
}
</script>

<style lang="scss">
.main {
  .category-card {
    box-shadow: 0px 24px 50px rgba(0, 0, 0, 0.1) !important;
    .category-title {
      color: #313039;
      letter-spacing: 0 !important;
    }
    .offer-badge {
      border-radius: 50%;
      top: -15px;
      left: -15px;
      width: 50px;
      height: 50px;
      background-color: #e47e7a;
    }
  }
  .select-category {
    box-shadow: 0px 24px 50px rgba(0, 0, 0, 0.1) !important;
  }
  .input-width {
    width: 228px;
  }
}
</style>
