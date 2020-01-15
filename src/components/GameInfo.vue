<template>
  <el-row :gutter="20">
    <el-col :span="12" :offset="6">
      <el-row :gutter="10">
        <el-col :span="8">
          <div class="grid-content">
            <el-tag type="warning">Questions left: {{ questionsLeft }}</el-tag>
          </div>
        </el-col>
        <el-col :span="8">
          <div class="grid-content">
            <el-tag type="info">Question difficulty: {{ difficulty }}</el-tag>
          </div>
        </el-col>
        <el-col :span="8">
          <div class="grid-content">
            <el-tag type="success">Points: {{ points }}</el-tag>
          </div>
        </el-col>
      </el-row>
    </el-col>
  </el-row>
</template>

<script>
export default {
  props: {
    difficulty: { type: String, required: true },
    points: { type: Number, required: true },
    questionsLeft: { type: Number, required: true }
  }
}
</script>
