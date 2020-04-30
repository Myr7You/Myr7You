<template>
  <div class="icon-wrapper">
    <svg class="icon" :width="width" :height="height" stroke="black">
      <use v-bind="{ 'xlink:href': '/skills.svg#' + name }" />
    </svg>
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    width: {
      type: [Number, String],
      default: 100
    },
    height: {
      type: [Number, String],
      default: 100
    }
  }
};
</script>

<style scoped>
.icon-wrapper {
  display: inline-flex;
  align-items: center;
  color: rgba(0, 0, 0, 0.4);
  font-size: 1rem;
  font-weight: 600;
}
.icon {
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
  margin-right: 6px;
}
</style>
