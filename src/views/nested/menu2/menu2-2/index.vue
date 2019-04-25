<template>
 <el-form v-model="formInline" class="">
    <el-form-item label="输入数据">
      <el-input v-model="formInline.user" placeholder="请输入名称" @keyup.enter.native="onSubmit"></el-input>
    </el-form-item>
   <el-button type="text" @click="clearList">清空列表</el-button>
   <el-form-item label="列表">
     <ul class="">
       <li v-for="item in formInline.friends">
         {{item.name}}
       </li>
     </ul>
   </el-form-item>
 </el-form>
</template>

<script>
export default {
  data() {
    return {
      formInline: {
        user: '',
        friends: [
          {name : 'tom'},
          {name : 'jone'}
        ]
      }
    }
  },
  methods: {
    onSubmit() {
      console.log('submit!');
      this.formInline.friends.push({name : this.formInline.user})
      this.formInline.user=''
    },
    clearList(){
      this.formInline.friends=[]
    }
  },
  watch: {}
}
</script>
