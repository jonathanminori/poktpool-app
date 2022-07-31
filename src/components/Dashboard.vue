<script>
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { LineChart } from "echarts/charts";

import {
  MarkLineComponent,
  TitleComponent,
  TooltipComponent,
  LegendComponent,
  MarkPointComponent,
} from "echarts/components";
import VChart from "vue-echarts";

import { ref, defineComponent } from "vue";

use([
  CanvasRenderer,
  LineChart,
  MarkLineComponent,
  TitleComponent,
  TooltipComponent,
  LegendComponent,
  MarkPointComponent,
]);

export default defineComponent({
  name: "Dashboard",
  data() {
    return {
      wallet_address: "A5DBFF4E8BD2C9B131558A408FB3946AEA14869A",
      records: [
        {
          tranche: 46,
          date: "June 8, 2022",
          total_staked: 12106.76,
          gross_rewards: 121.07,
          fees: 6.05,
          net_rewards: 115.01,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 47,
          date: "June 12, 2022",
          total_staked: 12222.87,
          gross_rewards: 122.23,
          fees: 6.11,
          net_rewards: 116.12,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 48,
          date: "June 15, 2022",
          total_staked: 12340.11,
          gross_rewards: 123.4,
          fees: 6.17,
          net_rewards: 117.23,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 49,
          date: "June 19, 2022",
          total_staked: 14477.64,
          gross_rewards: 144.78,
          fees: 7.24,
          net_rewards: 137.54,
          injection: 0,
          unstake: 2000.0,
          sweeps: 0,
        },
        {
          tranche: 50,
          date: "June 22, 2022",
          total_staked: 14616.5,
          gross_rewards: 146.16,
          fees: 7.31,
          net_rewards: 138.86,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 51,
          date: "June 26, 2022",
          total_staked: 14756.69,
          gross_rewards: 147.57,
          fees: 7.38,
          net_rewards: 140.19,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 52,
          date: "June 29, 2022",
          total_staked: 14898.22,
          gross_rewards: 148.98,
          fees: 7.45,
          net_rewards: 141.53,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 53,
          date: "July 3, 2022",
          total_staked: 15041.11,
          gross_rewards: 150.41,
          fees: 7.52,
          net_rewards: 142.89,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 54,
          date: "July 6, 2022",
          total_staked: 15185.37,
          gross_rewards: 151.85,
          fees: 7.59,
          net_rewards: 144.26,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 55,
          date: "July 10, 2022",
          total_staked: 15331.02,
          gross_rewards: 153.31,
          fees: 7.67,
          net_rewards: 145.64,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 56,
          date: "July 13, 2022",
          total_staked: 15478.06,
          gross_rewards: 154.78,
          fees: 7.74,
          net_rewards: 147.04,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 57,
          date: "July 16, 2022",
          total_staked: 15626.51,
          gross_rewards: 156.27,
          fees: 7.81,
          net_rewards: 148.45,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 58,
          date: "July 19, 2022",
          total_staked: 15776.39,
          gross_rewards: 157.76,
          fees: 7.89,
          net_rewards: 149.88,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 59,
          date: "July 22, 2022",
          total_staked: 14918.11,
          gross_rewards: 149.18,
          fees: 7.46,
          net_rewards: 141.72,
          injection: 1000.0,
          unstake: 0,
          sweeps: 0,
        },
        {
          tranche: 60,
          date: "July 25, 2022",
          total_staked: 15061.19,
          gross_rewards: 150.61,
          fees: 7.53,
          net_rewards: 143.08,
          injection: 0,
          unstake: 0,
          sweeps: 0,
        },
      ],
    };
  },
  methods: {
    copy_address() {
      this.$refs.clone.focus();
      document.execCommand("copy");
    },
  },
  components: {
    VChart,
  },
  setup() {
    const option = ref({
      grid: [
        {
          left: 0,
          top: 15,
          width: "100%",
          height: 480,
          containLabel: true,
        },
        {
          left: 0,
          top: 495,
          width: "100%",
          height: 140,
          containLabel: true,
        },
      ],
      tooltip: {
        trigger: "axis",
        axisPointer: {
          type: "shadow",
        },
        formatter:
          '<div class="p-2 w-56"><p class="text-black font-semibold">Tranche {b0}</p><div class="flex items-baseline justify-between mt-4 p-1.5 bg-slate-50"><div>{a0}:</div><div class="font-semibold">{c0}</div></div><div class="flex items-baseline justify-between p-1.5"><div>{a1}:</div><div class="font-semibold">{c1}</div></div><div class="flex items-baseline justify-between p-1.5 bg-slate-50"><div>{a2}:</div><div class="font-semibold">{c2}</div></div></div>',
      },
      axisPointer: { link: [{ xAxisIndex: "all" }] },
      xAxis: [
        {
          gridIndex: 0,
          type: "category",
          data: [46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60],
          boundaryGap: true,
          axisLine: {
            show: false,
          },
          axisTick: {
            show: false,
          },
          axisLabel: {
            show: false,
          },
          splitLine: {
            show: true,
            lineStyle: {
              type: "solid",
            },
          },
        },
        {
          gridIndex: 1,
          type: "category",
          data: [46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60],
          boundaryGap: true,
          axisTick: {
            alignWithLabel: true,
          },
          splitLine: {
            show: true,
            lineStyle: {
              type: "solid",
            },
          },
        },
      ],
      yAxis: [
        {
          gridIndex: 0,
          type: "value",
          data: [
            12106.76, 12222.87, 12340.11, 14477.64, 14616.5, 14756.69, 14898.22,
            15041.11, 15185.37, 15331.02, 15478.06, 15626.51, 15776.39,
            14918.11, 15061.19,
          ],
          scale: true,
          axisLabel: {
            inside: false,
            verticalAlign: "middle",
          },
          splitLine: {
            show: true,
            lineStyle: {
              type: "dashed",
            },
          },
        },
        {
          gridIndex: 1,
          splitNumber: 2,
          type: "value",
          data: [
            121.07, 122.23, 123.4, 144.78, 146.16, 147.57, 148.98, 150.41,
            151.85, 153.31, 154.78, 156.27, 157.76, 149.18, 150.61,
          ],
          scale: true,
          splitAreaColor: ["rgba(250,250,250,0.2)", "rgba(210,219,238,0.2)"],
          axisLabel: { show: false },
          axisLine: { show: false },
          axisTick: { show: false },
          splitLine: { show: false },
        },
      ],
      series: [
        {
          name: "Total Staked",
          type: "line",
          seriesLayoutBy: "row",
          encode: {
            x: "tranche",
            y: "total_staked",
          },
          data: [
            12106.76, 12222.87, 12340.11, 14477.64, 14616.5, 14756.69, 14898.22,
            15041.11, 15185.37, 15331.02, 15478.06, 15626.51, 15776.39,
            14918.11, 15061.19,
          ],
          step: "middle",
          lineStyle: {
            color: "#0284c7",
            width: 0,
          },
          symbol: "none",
          symbolSize: 6,
          areaStyle: {
            color: "#0284c7",
            opacity: 0.75,
          },
          markPoint: {
            data: [
              {
                name: "Injection",
                x: "288",
                y: "31%",
                itemStyle: {
                  color: "#6366f1",
                  borderType: "solid",
                  borderWidth: 2,
                  borderColor: "rgba(255, 255, 255, 1)",
                },
                symbolRotate: 0,
              },
              {
                name: "Unstake",
                x: "984",
                y: "23%",
                itemStyle: {
                  color: "#ea580c",
                  borderType: "solid",
                  borderWidth: 2,
                  borderColor: "rgba(255, 255, 255, 1)",
                },
                symbolRotate: 180,
              },
            ],
            symbolSize: 20,
            symbol: "triangle",
            label: {
              show: false,
            },
          },
        },
        {
          name: "Rewards",
          type: "bar",
          stack: "Rewards",
          color: "#10b981",
          emphasis: {
            disabled: true,
            focus: "series",
          },
          xAxisIndex: 1,
          yAxisIndex: 1,
          data: [
            115.01, 116.12, 117.23, 137.54, 138.86, 140.19, 141.53, 142.89,
            144.26, 145.64, 147.04, 148.45, 149.88, 141.72, 143.08,
          ],
        },
        {
          name: "Fees",
          type: "bar",
          stack: "Rewards",
          color: "#bbf7d0",
          emphasis: {
            disabled: true,
            focus: "series",
          },
          xAxisIndex: 1,
          yAxisIndex: 1,
          data: [
            6.05, 6.11, 6.17, 7.24, 7.31, 7.38, 7.45, 7.52, 7.59, 7.67, 7.74,
            7.81, 7.89, 7.46, 7.53,
          ],
        },
      ],
    });

    return { option };
  },
});
</script>

<template>
  <nav class="bg-white border-b border-slate-100">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <div class="flex">
          <div class="flex-shrink-0 flex items-center">
            <h1 class="sr-only text-xl font-bold">poktpool</h1>
            <img
              src="../assets/poktpool.webp"
              class="h-7 mt-1"
              alt="poktpool"
            />
          </div>
        </div>
        <div class="flex items-center">
          <div class="hidden md:mr-10 md:flex md:space-x-8 h-16">
            <a
              href="#"
              class="
                border-sky-500
                inline-flex
                items-center
                px-1
                pt-1
                border-b-2
                text-sm
                font-medium
              "
            >
              Dashboard
            </a>
            <a
              href="#"
              class="
                border-transparent
                text-slate-500
                hover:border-slate-300 hover:text-slate-700
                inline-flex
                items-center
                px-1
                pt-1
                border-b-2
                text-sm
                font-medium
              "
            >
              Manage
            </a>
            <a
              href="#"
              class="
                border-transparent
                text-slate-500
                hover:border-slate-300 hover:text-slate-700
                inline-flex
                items-center
                px-1
                pt-1
                border-b-2
                text-sm
                font-medium
              "
            >
              Account
            </a>
          </div>
          <div class="flex-shrink-0">
            <button
              type="button"
              class="
                relative
                inline-flex
                items-center
                px-4
                py-2
                border border-transparent
                text-sm
                font-medium
                rounded-md
                text-white
                bg-sky-600
                shadow-sm
                hover:bg-sky-700
                focus:outline-none
                focus:ring-2
                focus:ring-offset-2
                focus:ring-sky-500
              "
            >
              <!-- Heroicon name: solid/plus-sm -->
              <svg
                class="-ml-2 mr-1 h-5 w-5"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                aria-hidden="true"
              >
                <path
                  fill-rule="evenodd"
                  d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z"
                  clip-rule="evenodd"
                />
              </svg>
              <span>Stake</span>
            </button>
          </div>
          <div class="ml-6 flex items-center md:hidden">
            <!-- Mobile menu button -->
            <button
              type="button"
              class="
                inline-flex
                items-center
                justify-center
                p-2
                rounded-md
                text-slate-400
                hover:text-slate-500 hover:bg-slate-100
                focus:outline-none
                focus:ring-2
                focus:ring-inset
                focus:ring-sky-500
              "
              aria-controls="mobile-menu"
              aria-expanded="false"
            >
              <span class="sr-only">Open main menu</span>
              <svg
                class="block h-6 w-6"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="2"
                stroke="currentColor"
                aria-hidden="true"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M4 6h16M4 12h16M4 18h16"
                />
              </svg>
              <svg
                class="hidden h-6 w-6"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="2"
                stroke="currentColor"
                aria-hidden="true"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M6 18L18 6M6 6l12 12"
                />
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Mobile menu, show/hide based on menu state.
    <div class="md:hidden" id="mobile-menu">
      <div class="pt-2 pb-3 space-y-1">
        <a
          href="#"
          class="
            bg-sky-50
            border-sky-500
            text-sky-700
            block
            pl-3
            pr-4
            py-2
            border-l-4
            text-base
            font-medium
            sm:pl-5 sm:pr-6
          "
          >Dashboard</a
        >
        <a
          href="#"
          class="
            border-transparent
            text-slate-500
            hover:bg-slate-50 hover:border-slate-300 hover:text-slate-700
            block
            pl-3
            pr-4
            py-2
            border-l-4
            text-base
            font-medium
            sm:pl-5 sm:pr-6
          "
          >Team</a
        >
        <a
          href="#"
          class="
            border-transparent
            text-slate-500
            hover:bg-slate-50 hover:border-slate-300 hover:text-slate-700
            block
            pl-3
            pr-4
            py-2
            border-l-4
            text-base
            font-medium
            sm:pl-5 sm:pr-6
          "
          >Projects</a
        >
        <a
          href="#"
          class="
            border-transparent
            text-slate-500
            hover:bg-slate-50 hover:border-slate-300 hover:text-slate-700
            block
            pl-3
            pr-4
            py-2
            border-l-4
            text-base
            font-medium
            sm:pl-5 sm:pr-6
          "
          >Calendar</a
        >
      </div>
      <div class="pt-4 pb-3 border-t border-slate-200">
        <div class="flex items-center px-4 sm:px-6">
          <div class="flex-shrink-0">
            <img
              class="h-10 w-10 rounded-full"
              src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
              alt=""
            />
          </div>
          <div class="ml-3">
            <div class="text-base font-medium text-slate-800">Tom Cook</div>
            <div class="text-sm font-medium">tom@example.com</div>
          </div>
          <button
            type="button"
            class="
              ml-auto
              flex-shrink-0
              bg-white
              p-1
              rounded-full
              text-slate-400
              hover:text-slate-500
              focus:outline-none
              focus:ring-2
              focus:ring-offset-2
              focus:ring-sky-500
            "
          >
            <span class="sr-only">View notifications</span>
            <svg
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="2"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
              />
            </svg>
          </button>
        </div>
        <div class="mt-3 space-y-1">
          <a
            href="#"
            class="
              block
              px-4
              py-2
              text-base
              font-medium
              text-slate-500
              hover:text-slate-800 hover:bg-slate-100
              sm:px-6
            "
            >Your Profile</a
          >
          <a
            href="#"
            class="
              block
              px-4
              py-2
              text-base
              font-medium
              text-slate-500
              hover:text-slate-800 hover:bg-slate-100
              sm:px-6
            "
            >Settings</a
          >
          <a
            href="#"
            class="
              block
              px-4
              py-2
              text-base
              font-medium
              text-slate-500
              hover:text-slate-800 hover:bg-slate-100
              sm:px-6
            "
            >Sign out</a
          >
        </div>
      </div>
    </div> -->
  </nav>
  <main class="max-w-6xl mx-auto mb-48 px-4 pt-8 sm:pt-20 sm:px-6 lg:px-8">
    <div class="flex flex-col sm:flex-row justify-between items-baseline">
      <h2 class="text-xl font-medium">Account Overview</h2>
      <div class="flex mt-3 sm:mt-0 items-end space-x-2 text-xs text-slate-500">
        <input
          v-on:focus="$event.target.select()"
          ref="clone"
          readonly
          :value="wallet_address"
          class="ml-1 w-80 text-right border-0 ring-0 focus:ring-0"
        />
        <button @click="copy_address">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-4 w-4 text-slate-400 hover:text-slate-600"
            viewBox="0 0 20 20"
            fill="currentColor"
          >
            <path
              d="M9 2a2 2 0 00-2 2v8a2 2 0 002 2h6a2 2 0 002-2V6.414A2 2 0 0016.414 5L14 2.586A2 2 0 0012.586 2H9z"
            />
            <path d="M3 8a2 2 0 012-2v10h8a2 2 0 01-2 2H5a2 2 0 01-2-2V8z" />
          </svg>
        </button>
      </div>
    </div>
    <dl class="mt-10 grid grid-cols-1 gap-4 sm:grid-cols-3">
      <div
        class="
          relative
          px-4
          py-5
          bg-black
          rounded-md
          overflow-hidden
          sm:p-6
          row-span-2
        "
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="
            h-4
            w-4
            absolute
            top-3
            right-3
            text-slate-300
            hover:text-white
            cursor-pointer
          "
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M4 2a1 1 0 011 1v2.101a7.002 7.002 0 0111.601 2.566 1 1 0 11-1.885.666A5.002 5.002 0 005.999 7H9a1 1 0 010 2H4a1 1 0 01-1-1V3a1 1 0 011-1zm.008 9.057a1 1 0 011.276.61A5.002 5.002 0 0014.001 13H11a1 1 0 110-2h5a1 1 0 011 1v5a1 1 0 11-2 0v-2.101a7.002 7.002 0 01-11.601-2.566 1 1 0 01.61-1.276z"
            clip-rule="evenodd"
          />
        </svg>
        <dt class="text-sm text-slate-300 truncate">Total Staked</dt>
        <dd class="mt-1.5 text-5xl font-semibold text-white">15,061.19</dd>
        <div class="flex items-end justify-between">
          <div>
            <dt class="mt-8 text-sm text-slate-300 truncate">
              Total USD Value
            </dt>
            <dd class="mt-1.5 text-4xl font-semibold text-white">$1,219.95</dd>
          </div>
          <div class="mb-2 flex items-center space-x-2 text-white">
            <img src="/pokt.png" class="w-5 h-5" />
            <p class="text-white">0.081</p>
          </div>
        </div>
      </div>
      <div
        class="
          px-4
          py-5
          bg-slate-100
          rounded
          overflow-hidden
          sm:p-6
          grow-span-1
        "
      >
        <dt class="text-sm text-slate-600 truncate">Gross Rewards</dt>
        <dd class="mt-1.5 text-2xl font-semibold">4,086.51</dd>
      </div>
      <div
        class="
          px-4
          py-5
          bg-slate-100
          rounded
          overflow-hidden
          sm:p-6
          grow-span-1
        "
      >
        <dt class="text-sm text-slate-600 truncate">Net Rewards</dt>
        <dd class="mt-1.5 text-2xl font-semibold">2,205.38</dd>
      </div>
      <div
        class="
          px-4
          py-5
          bg-slate-100
          rounded
          overflow-hidden
          sm:p-6
          grow-span-1
        "
      >
        <dt class="text-sm text-slate-600 truncate">Total Swept</dt>
        <dd class="mt-1.5 text-2xl font-semibold">0.00</dd>
      </div>
      <div
        class="
          px-4
          py-5
          bg-slate-100
          rounded
          overflow-hidden
          sm:p-6
          grow-span-1
        "
      >
        <dt class="text-sm text-slate-600 truncate">Total Unstaked</dt>
        <dd class="mt-1.5 text-2xl font-semibold">0.00</dd>
      </div>
    </dl>
    <div class="mt-20">
      <div class="flex justify-between items-baseline">
        <h2 class="text-xl font-medium">Balance History</h2>
        <div class="flex items-center space-x-4">
          <button class="text-xs font-medium text-slate-500 mr-4">Reset</button>
          <div class="relative inline-block text-left">
            <div>
              <button
                type="button"
                class="
                  inline-flex
                  items-center
                  justify-center
                  w-full
                  rounded-md
                  border border-slate-300
                  shadow-sm
                  px-4
                  py-2
                  bg-white
                  text-slate-700
                  hover:bg-slate-50
                  focus:outline-none
                  focus:ring-2
                  focus:ring-offset-2
                  focus:ring-offset-slate-100
                  focus:ring-sky-500
                "
                id="menu-button"
                aria-expanded="true"
                aria-haspopup="true"
              >
                Tranche 48
                <!-- Heroicon name: solid/chevron-down -->
                <svg
                  class="-mr-1 ml-2 h-5 w-5"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                  aria-hidden="true"
                >
                  <path
                    fill-rule="evenodd"
                    d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                    clip-rule="evenodd"
                  />
                </svg>
              </button>
            </div>
          </div>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5 text-slate-400"
            viewBox="0 0 20 20"
            fill="currentColor"
          >
            <path
              fill-rule="evenodd"
              d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
              clip-rule="evenodd"
            />
          </svg>
          <div class="relative inline-block text-left">
            <div>
              <button
                type="button"
                class="
                  inline-flex
                  items-center
                  justify-center
                  w-full
                  rounded-md
                  border border-slate-300
                  shadow-sm
                  px-4
                  py-2
                  bg-white
                  text-slate-700
                  hover:bg-slate-50
                  focus:outline-none
                  focus:ring-2
                  focus:ring-offset-2
                  focus:ring-offset-slate-100
                  focus:ring-sky-500
                "
                id="menu-button"
                aria-expanded="true"
                aria-haspopup="true"
              >
                Tranche 60
                <!-- Heroicon name: solid/chevron-down -->
                <svg
                  class="-mr-1 ml-2 h-5 w-5"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                  aria-hidden="true"
                >
                  <path
                    fill-rule="evenodd"
                    d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                    clip-rule="evenodd"
                  />
                </svg>
              </button>
            </div>
          </div>
        </div>
      </div>
      <v-chart class="h-[640px] mt-10 mb-8" :option="option" />
      <ul class="mb-20 flex items-center justify-center space-x-10 text-xs">
        <li class="flex items-center">
          <svg
            class="w-3 h-3 mr-2 text-sky-600"
            viewBox="0 0 10 10"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect width="10" height="10" fill="currentColor" />
          </svg>
          Total Staked
        </li>
        <li class="flex items-center">
          <svg
            class="w-3 h-3 mr-2 text-emerald-500"
            viewBox="0 0 10 10"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect width="10" height="10" fill="currentColor" />
          </svg>
          Net Rewards
        </li>
        <li class="flex items-center">
          <svg
            class="w-3 h-3 mr-2 text-green-200"
            viewBox="0 0 10 10"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect width="10" height="10" fill="currentColor" />
          </svg>
          Fees
        </li>
        <li class="flex items-center">
          <svg
            class="w-3 h-3 mr-2 text-indigo-500"
            viewBox="0 0 11.7 11"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M5.29438 0.840671L0.385723 10.1671C0.210483 10.5001 0.451927 10.9 0.828182 10.9H10.6455C11.0218 10.9 11.2632 10.5001 11.088 10.1671L6.1793 0.840672C5.99184 0.484503 5.48184 0.484502 5.29438 0.840671Z"
              fill="currentColor"
            />
          </svg>
          Injection
        </li>
        <li class="flex items-center">
          <svg
            class="w-3 h-3 mr-2 text-orange-600"
            viewBox="0 0 11.7 11"
            transform="scale(1,-1)"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M5.29438 0.840671L0.385723 10.1671C0.210483 10.5001 0.451927 10.9 0.828182 10.9H10.6455C11.0218 10.9 11.2632 10.5001 11.088 10.1671L6.1793 0.840672C5.99184 0.484503 5.48184 0.484502 5.29438 0.840671Z"
              fill="currentColor"
            />
          </svg>
          Unstake
        </li>
      </ul>
    </div>
    <div class="mt-20">
      <div class="overflow-auto">
        <table class="min-w-full divide-y divide-slate-200">
          <thead>
            <tr>
              <th scope="col" class="py-3 pl-3 text-left text-sm font-medium">
                Tranche
              </th>
              <th
                scope="col"
                class="pr-3 text-left text-sm font-medium sr-only"
              >
                Date
              </th>
              <th scope="col" class="pl-8 pr-3 text-left text-sm font-medium">
                Total Staked
              </th>
              <th scope="col" class="px-3 text-left text-sm font-medium">
                Gross Rewards
              </th>
              <th scope="col" class="px-3 text-left text-sm font-medium">
                Net Rewards
              </th>
              <th scope="col" class="px-3 text-left text-sm font-medium">
                Fees
              </th>

              <th scope="col" class="px-3 text-left text-sm font-medium">
                Injections
              </th>
              <th scope="col" class="px-3 text-left text-sm font-medium">
                Sweeps
              </th>
              <th scope="col" class="px-3 text-left text-sm font-medium">
                Unstake
              </th>
            </tr>
          </thead>
          <tbody class="divide-y divide-slate-100">
            <tr
              v-for="record in records.slice().reverse()"
              class="odd:bg-slate-50 even:bg-white"
            >
              <td
                class="whitespace-nowrap py-2.5 pl-3 pr-3 text-sm font-medium"
              >
                {{ record.tranche }}
              </td>
              <td
                class="whitespace-nowrap px-3 text-sm border-r border-slate-200"
              >
                {{ record.date }}
              </td>
              <td class="whitespace-nowrap pl-8 pr-3 text-sm">
                {{ Number(record.total_staked).toLocaleString() }}
              </td>
              <td class="whitespace-nowrap px-3 text-sm">
                {{ Number(record.gross_rewards).toLocaleString() }}
              </td>
              <td class="whitespace-nowrap px-3 text-sm">
                {{ Number(record.net_rewards).toLocaleString() }}
              </td>
              <td class="whitespace-nowrap px-3 text-sm">
                {{ Number(record.fees).toLocaleString() }}
              </td>
              <td class="whitespace-nowrap px-3 text-sm">
                {{ Number(record.injection).toLocaleString() }}
              </td>
              <td class="whitespace-nowrap px-3 text-sm">
                {{ Number(record.sweeps).toLocaleString() }}
              </td>
              <td class="whitespace-nowrap px-3 text-sm">
                {{ Number(record.unstake).toLocaleString() }}
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      <div
        class="
          bg-white
          px-0
          py-6
          flex
          items-center
          justify-between
          border-t border-slate-200
        "
      >
        <div class="flex-1 flex items-center justify-between sm:hidden">
          <div>
            <p class="text-sm text-slate-700">
              Showing
              <span class="font-medium">1</span>
              to
              <span class="font-medium">15</span>
              of
              <span class="font-medium">15</span>
              results
            </p>
          </div>
          <div class="sr-only">
            <a
              href="#"
              class="
                relative
                inline-flex
                items-center
                px-4
                py-2
                border border-slate-300
                text-sm
                font-medium
                rounded-md
                text-slate-700
                bg-white
                hover:bg-slate-50
              "
            >
              Previous
            </a>
            <a
              href="#"
              class="
                ml-3
                relative
                inline-flex
                items-center
                px-4
                py-2
                border border-slate-300
                text-sm
                font-medium
                rounded-md
                text-slate-700
                bg-white
                hover:bg-slate-50
              "
            >
              Next
            </a>
          </div>
        </div>
        <div
          class="hidden sm:flex-1 sm:flex sm:items-center sm:justify-between"
        >
          <div>
            <p class="text-sm text-slate-700">
              Showing
              <span class="font-medium">1</span>
              to
              <span class="font-medium">15</span>
              of
              <span class="font-medium">15</span>
              results
            </p>
          </div>
          <div class="sr-only">
            <nav
              class="relative z-0 inline-flex rounded-md shadow-sm -space-x-px"
              aria-label="Pagination"
            >
              <a
                href="#"
                class="
                  relative
                  inline-flex
                  items-center
                  px-2
                  py-2
                  rounded-l-md
                  border border-slate-300
                  bg-white
                  text-sm
                  font-medium
                  text-slate-500
                  hover:bg-slate-50
                "
              >
                <span class="sr-only">Previous</span>
                <!-- Heroicon name: solid/chevron-left -->
                <svg
                  class="h-5 w-5"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                  aria-hidden="true"
                >
                  <path
                    fill-rule="evenodd"
                    d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z"
                    clip-rule="evenodd"
                  />
                </svg>
              </a>
              <!-- Current: "z-10 bg-sky-50 border-sky-500 text-sky-600", Default: "bg-white border-slate-300 text-slate-500 hover:bg-slate-50" -->
              <a
                href="#"
                aria-current="page"
                class="
                  z-10
                  bg-sky-50
                  border-sky-500
                  text-sky-600
                  relative
                  inline-flex
                  items-center
                  px-4
                  py-2
                  border
                  text-sm
                  font-medium
                "
              >
                1
              </a>
              <a
                href="#"
                class="
                  bg-white
                  border-slate-300
                  text-slate-500
                  hover:bg-slate-50
                  relative
                  inline-flex
                  items-center
                  px-4
                  py-2
                  border
                  text-sm
                  font-medium
                "
              >
                2
              </a>
              <a
                href="#"
                class="
                  bg-white
                  border-slate-300
                  text-slate-500
                  hover:bg-slate-50
                  hidden
                  md:inline-flex
                  relative
                  items-center
                  px-4
                  py-2
                  border
                  text-sm
                  font-medium
                "
              >
                3
              </a>
              <a
                href="#"
                class="
                  bg-white
                  border-slate-300
                  text-slate-500
                  hover:bg-slate-50
                  hidden
                  md:inline-flex
                  relative
                  items-center
                  px-4
                  py-2
                  border
                  text-sm
                  font-medium
                "
              >
                4
              </a>
              <a
                href="#"
                class="
                  relative
                  inline-flex
                  items-center
                  px-2
                  py-2
                  rounded-r-md
                  border border-slate-300
                  bg-white
                  text-sm
                  font-medium
                  text-slate-500
                  hover:bg-slate-50
                "
              >
                <span class="sr-only">Next</span>
                <!-- Heroicon name: solid/chevron-right -->
                <svg
                  class="h-5 w-5"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                  aria-hidden="true"
                >
                  <path
                    fill-rule="evenodd"
                    d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
                    clip-rule="evenodd"
                  />
                </svg>
              </a>
            </nav>
          </div>
        </div>
      </div>
    </div>
  </main>
  <footer class="bg-slate-50">
    <div
      class="
        flex
        items-center
        justify-between
        max-w-6xl
        mx-auto
        pb-24
        px-4
        pt-8
        sm:pt-20 sm:px-6
        lg:px-8
      "
    >
      <div>
        <ul
          class="flex items-center justify-start space-x-8 text-sm font-medium"
        >
          <li><a href="#" class="text-slate-900">Pool Stats</a></li>
          <li><a href="#" class="text-slate-900">About</a></li>
          <li><a href="#" class="text-slate-900">Blog</a></li>
          <li>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="w-6 h-6"
              viewBox="0 0 50 50"
              fill="currentColor"
            >
              <path
                d="M25,2c12.703,0,23,10.297,23,23S37.703,48,25,48S2,37.703,2,25S12.297,2,25,2z M32.934,34.375	c0.423-1.298,2.405-14.234,2.65-16.783c0.074-0.772-0.17-1.285-0.648-1.514c-0.578-0.278-1.434-0.139-2.427,0.219	c-1.362,0.491-18.774,7.884-19.78,8.312c-0.954,0.405-1.856,0.847-1.856,1.487c0,0.45,0.267,0.703,1.003,0.966	c0.766,0.273,2.695,0.858,3.834,1.172c1.097,0.303,2.346,0.04,3.046-0.395c0.742-0.461,9.305-6.191,9.92-6.693	c0.614-0.502,1.104,0.141,0.602,0.644c-0.502,0.502-6.38,6.207-7.155,6.997c-0.941,0.959-0.273,1.953,0.358,2.351	c0.721,0.454,5.906,3.932,6.687,4.49c0.781,0.558,1.573,0.811,2.298,0.811C32.191,36.439,32.573,35.484,32.934,34.375z"
              ></path>
            </svg>
          </li>
          <li>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="w-8 h-8"
              viewBox="0 0 50 50"
              fill="currentColor"
            >
              <path
                d="M38.129,12.004c0,0,5.871,6.8,5.871,19.049v2.568c0,0-7.414,4.832-9.674,4.832l-2.192-3.187	c1.362-0.61,3.221-1.669,3.221-1.669l-0.679-0.526c0,0-4.344,2.012-9.675,2.012s-9.675-2.012-9.675-2.012l-0.679,0.526	c0,0,1.858,1.059,3.221,1.669l-2.192,3.187C13.414,38.452,6,33.62,6,33.62v-2.568c0-12.249,5.871-19.049,5.871-19.049	s4.016-1.944,7.725-2.456l1.151,2.181c0,0,1.829-0.424,4.254-0.424s4.254,0.424,4.254,0.424l1.151-2.181	C34.113,10.06,38.129,12.004,38.129,12.004z M18.674,29.262c1.869,0,3.384-1.702,3.384-3.801c0-2.099-1.515-3.801-3.384-3.801	s-3.384,1.702-3.384,3.801C15.29,27.561,16.805,29.262,18.674,29.262z M31.326,29.262c1.869,0,3.384-1.702,3.384-3.801	c0-2.099-1.515-3.801-3.384-3.801c-1.869,0-3.384,1.702-3.384,3.801C27.943,27.561,29.458,29.262,31.326,29.262z"
              ></path>
            </svg>
          </li>
          <li>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="w-6 h-6"
              viewBox="0 0 30 30"
              fill="currentColor"
            >
              <path
                d="M28,6.937c-0.957,0.425-1.985,0.711-3.064,0.84c1.102-0.66,1.947-1.705,2.345-2.951c-1.03,0.611-2.172,1.055-3.388,1.295 c-0.973-1.037-2.359-1.685-3.893-1.685c-2.946,0-5.334,2.389-5.334,5.334c0,0.418,0.048,0.826,0.138,1.215 c-4.433-0.222-8.363-2.346-10.995-5.574C3.351,6.199,3.088,7.115,3.088,8.094c0,1.85,0.941,3.483,2.372,4.439 c-0.874-0.028-1.697-0.268-2.416-0.667c0,0.023,0,0.044,0,0.067c0,2.585,1.838,4.741,4.279,5.23 c-0.447,0.122-0.919,0.187-1.406,0.187c-0.343,0-0.678-0.034-1.003-0.095c0.679,2.119,2.649,3.662,4.983,3.705 c-1.825,1.431-4.125,2.284-6.625,2.284c-0.43,0-0.855-0.025-1.273-0.075c2.361,1.513,5.164,2.396,8.177,2.396 c9.812,0,15.176-8.128,15.176-15.177c0-0.231-0.005-0.461-0.015-0.69C26.38,8.945,27.285,8.006,28,6.937z"
              ></path>
            </svg>
          </li>
          <li>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="w-6 h-6"
              viewBox="0 0 24 24"
              fill="currentColor"
            >
              <path
                d="M0 3v18h24v-18h-24zm6.623 7.929l-4.623 5.712v-9.458l4.623 3.746zm-4.141-5.929h19.035l-9.517 7.713-9.518-7.713zm5.694 7.188l3.824 3.099 3.83-3.104 5.612 6.817h-18.779l5.513-6.812zm9.208-1.264l4.616-3.741v9.348l-4.616-5.607z"
              />
            </svg>
          </li>
        </ul>
        <ul class="flex items-baseline justify-start space-x-6 mt-4 text-xs">
          <li><a href="#" class="text-slate-900">Disclaimer</a></li>
          <li><a href="#" class="text-slate-900">Terms of Service</a></li>
          <li><a href="#" class="text-slate-900">Privacy Policy</a></li>
        </ul>
      </div>
      <img src="../assets/coincover.webp" class="block h-16" />
    </div>
  </footer>
</template>

<style scoped>
</style>
