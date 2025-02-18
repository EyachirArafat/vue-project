<script setup lang="ts">
import Dolphin from "./components/IconDolphin.vue";
import TradeCard from "./components/TradeCard.vue";
</script>

<template>
  <div class="flex justify-center items-center min-h-screen bg-gray-900">
    <TradeCard
      :logo-icon="Dolphin"
      username="frostyjayys"
      :badgeCount="1"
      action="Sell Partial"
      amount="$4.85K"
      tokenName="Bitcoin"
      price="$0.02338"
      marketCap="$2M"
      time="0s"
    />
  </div>
</template>

<!-- <HelloWorld msg="You did it!" :custom-component="TheWelcome" /> -->
