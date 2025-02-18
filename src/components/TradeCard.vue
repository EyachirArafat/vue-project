<script setup lang="ts">
import { type Component, type PropType } from "vue";

defineProps({
  logoIcon: {
    type: Object as PropType<Component>,
    required: false,
  },
  IconOne: {
    type: Object as PropType<Component>,
    required: false,
  },
  username: String,
  badgeCount: Number,
  action: String,
  amount: String,
  tokenIcon: {
    type: Object as PropType<Component>,
    required: false,
  },
  tokenName: String,
  price: String,
  marketCap: String,
  time: String,
});
</script>

<template>
  <div
    class="bg-gray-900 text-gray-600 p-4 rounded-lg shadow-lg w-90 flex flex-col space-y-2 border border-gray-800"
  >
    <div class="flex items-center justify-between">
      <div class="flex items-center space-x-2">
        <!-- tst -->
        <!-- Use component if provided -->
        <component v-if="logoIcon" :is="logoIcon" class="logo-icon" />

        <span class="text-yellow-500 font-semibold">{{ username }}</span>
        <span class="bg-gray-800 text-slate-200 px-2.5 py-0.5 rounded text-sm">
          {{ badgeCount }}
        </span>
      </div>
      <button
        class="bg-gray-800 px-4 py-2 rounded-full hover:bg-gray-700 cursor-pointer"
      >
        ⚡
      </button>
    </div>

    <div class="flex items-center justify-start gap-2 text-sm font-bold">
      <span class="font-bold">{{ action }}</span>
      <span :class="action === 'Buy' ? 'text-green-500' : 'text-red-500'">
        {{ amount }}
      </span>

      <span>{{ tokenIcon }}</span>

      <span class="text-lg font-bold text-white">{{ tokenName }}</span>
    </div>

    <div class="flex justify-between items-center text-sm font-bold">
      <div>
        Price: <span class="text-white">{{ price }}</span> MC:
        <span :class="action === 'Buy' ? 'text-white' : 'text-yellow-400'">
          {{ marketCap }}
        </span>
      </div>

      <div
        :class="action === 'Buy' ? 'text-green-500' : 'text-red-500'"
        class="text-xs text-right"
      >
        {{ time }}
      </div>
    </div>
  </div>
</template>
