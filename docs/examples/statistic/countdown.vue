<template>
  <div class="play-container2">
    <div class="s-card">
      <el-row>
        <el-col :span="8">
          <ElCountdown title="Start to grab" countdown :value="value" />
        </el-col>
        <el-col :span="8">
          <ElCountdown
            title="Remaining VIP time"
            format="HH:mm:ss"
            :value="value1"
          />
          <div class="f-center">
            <el-button type="primary" @click="reset">Reset</el-button>
          </div>
        </el-col>
        <el-col :span="8">
          <ElCountdown :value="value2" format="DD day HH:mm:ss">
            <template #title>
              <el-icon style="margin-right: 4px" :size="12"
                ><Calendar
              /></el-icon>
              <span> New Year's Day is still to come </span>
            </template>
          </ElCountdown>
          <div class="f-center">2023-01-01 00:00:00</div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import dayjs from 'dayjs'
import { Calendar } from '@element-plus/icons-vue'
const value = ref(Date.now() + 1000 * 60 * 60 * 7)
const value1 = ref(Date.now() + 1000 * 60 * 60 * 24 * 2)
const value2 = ref(dayjs('2023-01-01 00:00:00').valueOf())

function reset() {
  value1.value = Date.now() + 1000 * 60 * 60 * 24 * 2
}
</script>

<style lang="scss" scoped>
.play-container2 {
  height: 100%;
  width: 100%;
  .f-center {
    text-align: center;
    margin-top: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .s-card {
    width: 100%;
    margin-top: 20px;
  }
  .s-bg {
    box-sizing: border-box;
    width: 100%;
    padding: 20px;
    background: #f0f2f5;
    border: 1px solid #dcdfe6;
  }
  .item {
    width: 100%;
    height: 200px;
    text-align: left;
  }
}
</style>
