<template>
  <div class="container">
    <currency-rate :currency="currency" @currency-change="updateCurrency" />
  </div>
</template>

<script>
import CurrencyRate from "@/components/CurrencyRate.vue";

export default {
  data() {
    return {
      currency: "",
      currencies: [],
    };
  },
  components: {
    CurrencyRate,
  },
  methods: {
    updateCurrency(currency) {
      this.currency = currency;
    },
  },
  created() {
    this.currency = this.$route.params.currency ?? "USD";
  },
};
</script>
