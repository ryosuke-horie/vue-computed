<script setup lang="ts">
import { ref, computed } from 'vue'

// 半径の初期値を乱数で取得
const radiusInit = Math.round(Math.random() * 10)

// 演習率のテンプレート変数を用意
const PI = ref(3.14)

// 半径のテンプレート変数を用意
const radius = ref(radiusInit)

// 円の面積の算出プロパティを用意
const area = computed(() => {
  return radius.value * radius.value * PI.value
})

// 半径のテンプレート変数に新しい乱数を1秒ごとに格納
setInterval((): void => {
  radius.value = Math.round(Math.random() * 10)
}, 1000)
</script>

<template>
  <div>
    <p>半径{{ radius }}の円の面積の円周率を{{ PI }}で計算すると、{{ area }}</p>
  </div>
</template>