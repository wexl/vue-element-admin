<template>
 <el-form v-model="formInline" class="">
    <el-form-item label="输入数据">
      <el-input v-model="formInline.user" placeholder="请输入名称"></el-input>
    </el-form-item>
 </el-form>
</template>

<script>
export default {
  data() {
    return {
      formInline: {
        user: '',
        region: ''
      }
    }
  },
  methods: {
    onSubmit() {
      console.log('submit!');
    }
  },
  watch: {}
}
</script>
