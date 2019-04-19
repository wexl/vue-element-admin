<!--<template functional>
  <div style="padding:30px;">
    <el-alert :closable="false" title="menu 2-1" type="warning" />
  </div>
</template>-->
<template>
  <div class="thform">
    <el-form :inline="false" :model="form" label-width="80px">
      <el-form-item label="性别">
        <el-radio v-model="form.radio" label="1">备选项</el-radio>
        <el-radio v-model="form.radio" label="2">备选项</el-radio>
      </el-form-item>

      <el-form-item label="审批名称">
        <el-input :model="form.time" placeholder="审批名称" />
      </el-form-item>

      <el-form-item label="审批时间">
        <el-col :span="7">
          <el-date-picker v-model="form.data1" type="date" placeholder="选择日期" style="width: 100%" />
        </el-col>
        <el-col class="line" :span="1" style="text-align: center">-</el-col>
        <el-col :span="'7'">
          <el-time-picker v-model="form.data2" placeholder="选择时间" style="width: 100%" />
        </el-col>
      </el-form-item>

      <el-form-item label="审批人">
        <el-select v-model="form.user" placeholder="审批人">
          <el-option-group>
            <el-option label="张三" value="zs" />
            <el-option label="李四" value="lis" />
            <el-option label="王五" value="ww" />
          </el-option-group>
          <el-option-group>
            <el-option label="赵六" value="zl" />
            <el-option label="马七" value="maq" />
            <el-option label="陈八" value="cb" />
          </el-option-group>
        </el-select>
      </el-form-item>
      <el-form-item label="立即生效">
        <el-switch v-model="form.liji" />
      </el-form-item>
      <el-form-item label="审批意见">
        <el-input v-model="form.remark" type="textarea" placeholder="请填写审批意见" />
      </el-form-item>
      <el-form-item label="审批性质">
        <el-checkbox-group v-model="form.type">
          <el-checkbox label="美食/餐厅线上活动" name="type" />
          <el-checkbox label="地推活动" name="type" />
          <el-checkbox label="线下主题活动" name="type" />
          <el-checkbox label="单纯品牌曝光" name="type" />
        </el-checkbox-group>
      </el-form-item>
      <el-form-item label="进度">
        <el-progress type="circle" :percentage="25" />
        <el-progress :text-inside="true" :stroke-width="18" :percentage="70" />
      </el-form-item>
      <el-form-item label="操作">
        <el-button type="primary" @click="submit">提交</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<style lang="scss" scoped>
.thform{
  width: 800px;
  margin-left: 50px;
  border: #0a76a4 2px;
}
</style>
<script>
export default {
  data() {
    return {
      form: {
        radio: '1',
        user: '',
        time: '',
        remark: '',
        type: [],
        data1: '',
        data2: '',
        liji: false
      }
    }
  },
  methods: {
    submit() {
      this.$confirm('确定要提交审核数据?', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        type: 'warning'
      }).then(() => {
        this.$message({
          type: 'success',
          message: '提交成功'
        })
      }).catch(action => {
        this.$message({
          type: 'info',
          message: action === 'cancel'
            ? '放弃提交'
            : '停留在当前页面'
        })
      })
    }
  }
}
</script>
