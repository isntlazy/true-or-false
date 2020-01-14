<template>
  <div class="game-container">
    <el-row :gutter="20">
      <el-col :span="12" :offset="6">
        <el-row :gutter="10">
          <el-col :span="8">
            <div class="grid-content">
              <el-tag type="warning">Questions left: 5</el-tag>
            </div>
          </el-col>
          <el-col :span="8">
            <div class="grid-content">
              <el-tag type="info">Complexity: easy</el-tag>
            </div>
          </el-col>
          <el-col :span="8">
            <div class="grid-content">
              <el-tag type="success">Points: 3</el-tag>
            </div>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
    <el-row></el-row>
    <h1><span class="true">True</span> or <span class="false">False</span>?</h1>
    <el-row></el-row>
    <el-row :gutter="20">
      <el-col :offset="4" :span="16">
        <div class="grid-content">
          <el-row :gutter="12">
            <el-col :span="24">
              <el-card shadow="never">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore
                et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
                aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
                cillum dolore eu fugiat nulla pariatur.
              </el-card>
            </el-col>
          </el-row>
        </div>
      </el-col>
    </el-row>
    <el-row :gutter="20">
      <el-col :offset="4" :span="16">
        <div class="grid-content">
          <el-row :gutter="12">
            <el-col :span="12">
              <el-card shadow="hover">
                <i class="el-icon-check"></i> True
              </el-card>
            </el-col>
            <el-col :span="12">
              <el-card shadow="hover">
                <i class="el-icon-close"></i>False
              </el-card>
            </el-col>
          </el-row>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'GameContainer'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .true {
    color: #67C23A;
  }
  .false {
    color: #f56C6C;
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
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
</style>
