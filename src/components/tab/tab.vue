<template>
<div class="tab">
  <cube-tab-bar 
    :useTransition=false
    :showSlider=true
    v-model="selectedLabel"
    :data="tabs"
    ref="tabBar"
    class="border-bottom-1px">
     
  </cube-tab-bar>
  <div class="slide-wrapper">
   <cube-tab-panels v-model="selectedLabel">
    <cube-tab-panel v-for="(item, index) in tabs" :label="item.label" :key="item.label">
      <ul>
        <li class="tab-panel-li" v-for="(hero, index) in item.heroes">
          {{hero}}
        </li>
      </ul>
    </cube-tab-panel>
  </cube-tab-panels>
  </div>
</div>
</template>

<script>
export default {
  name:tab,
  props:{
    tabs:
  }
}
</script>
