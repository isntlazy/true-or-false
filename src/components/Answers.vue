<template>
  <el-row :gutter="20">
    <el-col :offset="4" :span="16">
      <div class="grid-content">
        <el-row :gutter="12">
          <el-col :span="12">
            <div @click="onAnswer(true)">
              <el-card class="answer" shadow="hover">
                <i class="el-icon-check"></i> True
              </el-card>
            </div>
          </el-col>
          <el-col :span="12">
            <div @click="onAnswer(false)">
              <el-card class="answer" shadow="hover">
                <i class="el-icon-close"></i>False
              </el-card>
            </div>
          </el-col>
        </el-row>
      </div>
    </el-col>
  </el-row>
</template>

<script>
export default {
  props: {
    correctAnswer: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    onAnswer (userAnswer) {
      if (userAnswer === this.correctAnswer) {
        this.$emit('correctAnswer')
      } else {
        this.$emit('wrongAnswer')
      }
    }
  }
}
</script>

<style lang="scss">
  .answer {
    cursor: pointer;
  }
  .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
</style>
