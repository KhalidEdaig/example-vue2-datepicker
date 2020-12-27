<template>
  <div class="py-6 bg-white z-40 rounded">
    <div class="max-full mx-auto px-4 sm:px-6 lg:px-8">
      <div class="lg:text-center">
        <p
          class="mt-2 text-2xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl"
        >
          A better way to input date
        </p>
        <p
          class="mt-2 text-2xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl"
        >
          With
        </p>
        <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
          vue2-datepicker
          <a
            href="https://github.com/mengxiong10/vue2-datepicker"
            target="_blank"
            class="text-indigo-500"
            >GitHub</a
          >
        </p>
      </div>

      <div class="mt-10">
        <div class="lg:text-center mb-6">
          <h2 class="text-base text-indigo-600 font-semibold tracking-wide uppercase">
            All options
          </h2>
        </div>
        <dl class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 md:gap-x-8 md:gap-y-10">
          <card title="type date" :date="date">
            <date-picker
              :lang="lang"
              :type="'date'"
              format="DD-MMMM-YYYY"
              v-model="date"
              input-class="px-4 py-2 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md bg-gray-200 text-gray-900 font-semibold"
            ></date-picker>
            <dt class="flex text-lg leading-6 font-medium text-gray-900">
              Display : {{ date | moment("DD-MM-YYYY") }}
            </dt>
          </card>
          <card title="type month" :date="month">
            <date-picker
              :type="'month'"
              format="MM-YYYY"
              v-model="month"
              input-class="px-4 py-2 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md bg-gray-200 text-gray-900 font-semibold"
            ></date-picker>
            <dt class="flex text-lg leading-6 font-medium text-gray-900">
              Display : {{ month | moment("MM-YYYY") }}
            </dt>
          </card>
          <card title="Type range" :date="range">
            <date-picker :range="true" v-model="range" @change="onChange">
              <div slot="input">
                {{ range[0] | moment("DD-MM-YYYY") }} to
                {{ range[1] | moment("DD-MM-YYYY") }}
              </div>
            </date-picker>
            <dt class="flex text-lg leading-6 font-medium text-gray-900"></dt>
            <dt class="flex text-lg leading-6 font-medium text-gray-900">
              Display : from : {{ range[0] | moment("DD-MM-YYYY") }} to:
              {{ range[1] | moment("DD-MM-YYYY") }}
            </dt>
          </card>
        </dl>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./utils/Card";
import DatePicker from "vue2-datepicker";
import "vue2-datepicker/index.css";
let d = new Date();
export default {
  name: "VueDatepicker",
  props: {
    msg: String,
  },
  components: {
    Card,
    DatePicker,
  },
  data() {
    return {
      lang:"fr",
      date: d,
      month: d,
      range: [new Date(d.getFullYear(), d.getMonth(), 1), d],
    };
  },
  methods: {
    onChange() {
      console.log("from :" + this.range[0]);
      console.log("to :" + this.range[1]);
    },
  },
  computed: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
