<script setup lang="ts">
import { type Component, type PropType } from "vue";
import ElectricIcon from "./ElectricIcon.vue";

defineProps({
  // logoIcon: {
  //   type: Object as PropType<Component>,
  //   required: false,
  // },
  IconOne: {
    type: Object as PropType<Component>,
    required: false,
  },
  IconTwo: {
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
        <component
          v-if="IconOne"
          :is="IconOne"
          width="20"
          height="20"
          class="text-blue-500"
        />
        <component v-if="IconTwo" :is="IconTwo" width="20" height="20" />

        <span class="text-yellow-500 font-semibold">{{ username }}</span>
        <span
          class="bg-gray-800 text-slate-300 px-2.5 py-0.5 rounded text-sm font-bold"
        >
          {{ badgeCount }}
        </span>
      </div>
      <button
        class="bg-gray-800 px-4 py-2 rounded-full hover:bg-gray-700 cursor-pointer"
      >
        <ElectricIcon class="text-yellow-500" />
      </button>
    </div>

    <div class="flex items-center justify-start gap-2 text-sm font-bold">
      <span class="font-bold">{{ action }}</span>
      <span :class="action === 'Buy' ? 'text-green-500/80' : 'text-red-500'">
        {{ amount }}
      </span>

      <component
        v-if="tokenIcon"
        :is="tokenIcon"
        width="28"
        height="28"
        class="text-amber-500"
      />

      <span class="text-lg font-bold text-slate-300/80">{{ tokenName }}</span>
    </div>

    <div class="flex justify-between items-center text-sm font-bold">
      <div>
        Price: <span class="">{{ price }}</span> MC:
        <span
          :class="action === 'Buy' ? 'text-slate-300/80' : 'text-yellow-400/80'"
        >
          {{ marketCap }}
        </span>
      </div>

      <div
        :class="action === 'Buy' ? 'text-green-500/80' : 'text-red-500/80'"
        class="text-xs text-right"
      >
        {{ time }}
      </div>
    </div>
  </div>
</template>
