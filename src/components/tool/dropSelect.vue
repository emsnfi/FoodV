<template>
  <select v-model="selected">
    <option value="">請選擇</option>
    <option v-for="item in infor" :value="item" :key="item">
      {{ item }}
    </option>
  </select>
</template>

<script>
export default {
  data() {
    return {
      selected: "",
    };
  },
  //   delimiters: ["${", "}"],
  props: {
    infor: {
      type: Array,
      required: true,
    },
  },
  methods: {
    selectItem() {
      alert(this.selected);
    },
  },
  watch: {
    selected: {
      deep: true,
      handler: function () {
        this.$emit("selectItem", this.selected);
      },
    },
  },
};
</script>
