<template>
  <div class="slider">
    <ul id="customize-controls" class="controls">
      <li>‹</li>
      <li>›</li>
    </ul>
    <ul class="my-slider">
      <li v-for="item in items" :key="item.caption" :class="item.color">
        <div>
          <h3>{{ item.value.toLocaleString() }}</h3>
          <p>{{ item.caption }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import { tns } from "tiny-slider/src/tiny-slider";
import "tiny-slider/dist/tiny-slider.css";

export default {
  props: ["items"],
  mounted() {
    tns({
      container: ".my-slider",
      items: 1,
      slideBy: "page",
      autoplay: true,
      autoplayText: ["▶", "❚❚"],
      nav: true,
      controlsContainer: "#customize-controls"
    });
  }
};
</script>

<style scoped>
li {
  width: 100%;
  text-align: center;
}

p {
  line-height: 0.8;
  font-size: 1.5em;
}

h3 {
  font-size: 7vmax;
  line-height: 120%;
}
</style>
