
<template>
  <el-container>
    <el-header>
      <el-tabs v-model="tabName" @tab-click="handleClick">
        <el-tab-pane label="範例頁面" name="範例頁面"></el-tab-pane>
      </el-tabs>
    </el-header>
    <el-container>
      <el-main>
        <Demo v-if="tabName == '範例頁面'"/>
      </el-main>
    </el-container>
  </el-container>
</template>

<script setup lang="ts">
// TODO: 教學 -- ref, reactive, onMounted
import { onMounted, reactive, ref } from 'vue'
import Demo from '@/components/Demo.vue'
import type { TabsPaneContext } from 'element-plus'

const tabName = ref('範例頁面')

/// 已報名的列表
const signUpList = ref<any>([])

const handleClick = (tab: TabsPaneContext, event: Event) => {
  /// 如果想偵測tab點擊事件可以加在這邊
  console.log(tab, event)
}

function onSubmit(form: any) {
  /// 接收到報名的表單，這邊不審核直接加入已報名列表
  signUpList.value.push(form);
}

onMounted(() => {

})
</script>

<style scoped>
.app-root {
  text-align: center;
}

.form-region {
  margin-top: 40px;
  display: inline-block;
  width: 500px;
}
</style>
