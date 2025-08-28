<script setup lang="ts">
import { ref, reactive } from 'vue'

const isRegister = ref(false)
const form = reactive({
  account: '',
  password: ''
})

function onSubmit() {
  console.log('login')
}
</script>

<template>
  <el-form v-if="isRegister==false" :model="form" label-width="auto" style="max-width: 600px">
    <el-form-item>
      <h1>{{ isRegister?'注册':'登录' }}</h1>
    </el-form-item>
    <el-form-item label="账号">
      <el-input v-model="form.account" />
    </el-form-item>
    <el-form-item label="密码">
      <el-input v-model="form.password" />
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="isRegister=!isRegister">注册</el-button>
      <el-button type="primary" @click="onSubmit">登录</el-button>
    </el-form-item>
  </el-form>
  <!--  注册-->
  <el-form v-else :model="form" label-width="auto" style="max-width: 600px">
    <el-form-item label="账号">
      <el-input v-model="form.account" />
    </el-form-item>
    <el-form-item label="密码">
      <el-input v-model="form.password" />
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="">确定</el-button>
      <el-button type="primary" @click="isRegister=!isRegister">返回</el-button>
    </el-form-item>
  </el-form>
</template>

<style scoped>

</style>
