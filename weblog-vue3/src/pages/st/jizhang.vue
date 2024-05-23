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
  <el-table :data="tableData" stripe style="width: 100%" class="mt-4" v-loading="tableLoading">
            <el-table-column prop="title" label="标题" width="380" />
            <el-table-column label="预览图" width="180">
                <template #default="scope">
                    <el-image style="width: 50px;" :src="scope.row.titleImage" />
                </template>
            </el-table-column>
            <el-table-column prop="createTime" label="发布时间" width="180" />
            <el-table-column label="操作">
                <template #default="scope">
                    <el-button size="small" @click="showArticleUpdateEditorShow(scope.row)">
                        <el-icon class="mr-1">
                            <Edit />
                        </el-icon>
                        编辑</el-button>
                    <el-button size="small" @click="previewArticle(scope.row)">
                        <el-icon class="mr-1">
                            <View />
                        </el-icon>
                        预览</el-button>
                    <el-button type="danger" size="small" @click="deleteArticleSubmit(scope.row)">
                        <el-icon class="mr-1">
                            <Delete />
                        </el-icon>
                        删除
                    </el-button>
                </template>
            </el-table-column>
        </el-table>
</template>

<script setup>

</script>

<style scoped>

</style>
