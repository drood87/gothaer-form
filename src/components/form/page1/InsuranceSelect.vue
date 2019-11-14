<template>
  <div class="grid">
    <div
      v-for="insurance in insurances"
      :key="insurance.name"
      :class="'grid__item--'+(insurance.product.name).toLowerCase()"
    >
      <InsuranceBox :product="insurance.product" v-on:selected="insuranceSelect" />
      <h1>{{ checked }}</h1>
      <PriceBox />
    </div>
  </div>
</template>

<script>
import InsuranceBox from "./InsuranceBox";
import PriceBox from "./PriceBox";

export default {
  name: "InsuranceSelect",
  components: {
    InsuranceBox,
    PriceBox
  },
  data() {
    return {
      checked: [],
      insurances: [
        {
          product: {
            name: "Ambulant",
            desc: "Lorem Ipsum Lorem Hipsum",
            price: {
              productA: {
                name: "A",
                price: 9.5
              }
            }
          }
        },
        {
          product: {
            name: "Zahn",
            desc: "Lorem Zahnum Zahnum Ipsum Lorem",
            price: {
              zDuo: {
                name: "zDuo",
                price: 0
              }
            }
          }
        },
        {
          product: {
            name: "Vorsorge",
            desc: "vosogsumIpsum Lorem Insurance",
            price: {
              basis: {
                name: "Basis",
                price: 0
              },
              premium: {
                name: "Premium",
                price: 0
              }
            }
          }
        },
        {
          product: {
            name: "Stationaer",
            desc: "Lorem Bla bla ipsum bla",
            price: {
              s1: {
                name: "S1",
                price: 0
              },
              s2: {
                name: "S2",
                price: 0
              },
              s3: {
                name: "S3",
                price: 0
              }
            }
          }
        }
      ],
      insurancesSelected: []
    };
  },
  methods: {
    insuranceSelect(e) {
      // eslint-disable-next-line no-console
      console.log(e);
    }
  }
};
</script>

<style lang="scss" scoped>
@import "./../../../styles/layout/_select-grid.scss";
</style>