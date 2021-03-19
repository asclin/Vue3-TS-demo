<template>
  <div class="home">
    <el-form :model="ruleForm" label-width="100px" class="demo-ruleForm">
      <el-form-item label="id" prop="id">
        <el-input v-model="ruleForm.id"></el-input>
      </el-form-item>
      <el-form-item label="用户名" prop="username">
        <el-input v-model="ruleForm.username"></el-input>
      </el-form-item>
      <el-form-item label="密码" prop="password">
        <el-input v-model="ruleForm.password"></el-input>
      </el-form-item>
    </el-form>
    <el-button @click="submit">submit</el-button>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import axios from "axios";

@Options({
  components: {},
  data() {
    return {
      ruleForm: {
        id:'',
        username: "",
        password: "",
      },
    };
  },
  methods: {
    submit() {
      axios.post("/api/user", {
        _id: this.ruleForm.id,
        user_name: this.ruleForm.username,
        password: this.ruleForm.password,
      });
    },
  },
})
export default class Regist extends Vue {}
</script>
