<script setup lang="ts">
import HeaderView from "./components/HeaderView.vue";
import {ref , watch} from "vue";

const section1 = ref();
const section2 = ref();
const section3 = ref();
const sectionN = ref();
sectionN.value.scrollIntoView({behavior: "smooth"})
const target = ref(1)
watch(target , (newVal, oldVal) => {
  showScrollInto(newVal)
} )
function chanceTarget(section_id) {
target.value = section_id
}
function showScrollInto(section_id) {


  let section = null;
  switch (section_id) {
    case 1:
      section = section1.value;
      break;
    case 2:
      section = section2.value;
      break;
    case 3:
      section = section3.value;
      break;
    default:
      return
  }
  section.scrollIntoView({behavior: "smooth"});
}
</script>

<template>
  <span ref="section1">
    <HeaderView ref="sectionN" @target="chanceTarget" ></HeaderView>
  </span>
  <span ref="section2">
    <HeaderView></HeaderView>
  </span>
  <span ref="section3">
    <HeaderView></HeaderView>
  </span>
</template>

<style scoped>
#section1 .image {
  padding: 0;
  margin: 0;
  position: absolute;
  top: 0;
  left: 0;
  opacity: 1;
  height: 100vh;
  width: 100%;
  background: url("@/assets/Header.png") center/cover no-repeat;
  z-index: -100;
}
</style>
