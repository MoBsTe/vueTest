<template>
  <div class="list_item">
    {{ mess.mes }}
    <div class="closet" @click="delateData(index)">X</div>
  </div>
</template>

<script>
export default {
  props: {
    mess: {
      type: Object,
      required: true,
    },
    delateData: {
      type: Function,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style></style>
