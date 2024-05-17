<template>
  <el-card shadow="never" :body-style="{ padding: '20px' }" class="mb-5 border-1">
    <!-- card body -->
    <el-text class="mx-1 mr-3">文章标题</el-text>
    <el-input v-model="searchTitle" placeholder="请输入（模糊查询）" class="w-50 mr-5" />

    <el-text class="mx-1 mr-3">发布日期</el-text>
    <el-date-picker style="top: 3px" v-model="pickDate" type="daterange" range-separator="至" start-placeholder="开始时间"
                    end-placeholder="结束时间" :shortcuts="shortcuts" size="default" @change="datepickerChange" />

    <el-button type="primary" class="ml-3" :icon="Search" @click="getTableData">查询</el-button>
    <el-button class="ml-3" :icon="RefreshRight" @click="reset">重置</el-button>
  </el-card>
</template>

<script setup>

</script>

<style scoped>

</style>
