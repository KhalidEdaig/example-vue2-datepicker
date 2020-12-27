<template>
  <div class="py-6 bg-white z-40 rounded">
    <VueDatepicker msg="Demo vue2 datepicker all options"/>
  </div>
</template>

<script>
// @ is an alias to /src
import VueDatepicker from '@/components/VueDatepicker.vue'

export default {
  name: 'Home',
  components: {
    VueDatepicker
  }
}
</script>
