<template>
  <div class="popup absolute top-0 left-0 right-0 pin z-40 py-view bg-primary-70% overflow-y-auto">
    <div class="absolute pin z-20" @click="$parent.$parent.popup = null"></div>

    <div class="relative z-30 bg-white p-8 rounded-lg shadow-lg m-auto">

      <button type="button" class="nml-close select-none" @click="$parent.$parent.popup = null">&times;</button>

      <Library :field="field.attribute" :isArray="field.nmlArray" :types="types" />

    </div>

  </div>
</template>

<script>
import Library from '../../tool/'

export default {
  props: ['field'],
  components: { Library },
  data() {
    return {
      types: Array.isArray(this.field.nmlTypes) ? this.field.nmlTypes : []
    }
  },
  mounted() {
    //document.body.classList.add('overflow-hidden');
  },
  beforeUnmount() {
    document.body.classList.remove('overflow-hidden');
  }
}
</script>
