<script setup lang="ts">
import Bitcoin from "./components/Bitcoin.vue";
import Dolphin from "./components/DolphinIcon.vue";
import SnowFlakeIcon from "./components/SnowFlakeIcon.vue";
import TradeCard from "./components/TradeCard.vue";
</script>

<template>
  <div class="flex justify-center items-center min-h-screen bg-gray-900">
    <TradeCard
      :IconOne="SnowFlakeIcon"
      :IconTwo="Dolphin"
      username="Salman vai"
      :badgeCount="1"
      action="Sell Partial"
      amount="$4.85K"
      :tokenIcon="Bitcoin"
      tokenName="Bitcoin"
      price="$0.02338"
      marketCap="$2M"
      time="0s"
    />
  </div>
</template>
