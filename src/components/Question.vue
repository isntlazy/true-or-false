<template>
    <el-row :gutter="20">
        <el-col :offset="4" :span="16">
            <div class="grid-content">
                <el-row :gutter="12">
                    <el-col :span="24">
                        <el-card shadow="never">
                            <span v-html="text"></span>
                        </el-card>
                    </el-col>
                </el-row>
            </div>
        </el-col>
    </el-row>
</template>
<script>
export default {
  name: 'Question',
  props: {
    text: { type: String, required: true }
  }
}
</script>

<style scoped lang="scss">
    .grid-content {
        border-radius: 4px;
        min-height: 36px;
    }
</style>
