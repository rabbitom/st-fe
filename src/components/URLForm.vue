<template>
  <div>
    <el-form class="url-form">
      <el-form-item label="网址">
        <el-input v-model="url"></el-input>
      </el-form-item>
      <el-form-item label="格式">
        <el-radio-group v-model="format">
          <el-radio label="json">JSON</el-radio>
          <el-radio label="text">文本</el-radio>
        </el-radio-group>
      </el-form-item>
      <el-form-item label="分割线">
        <el-input :disabled="format !== 'text'" v-model="separator"></el-input>
      </el-form-item>
      <el-button @click="onConfirm">确定</el-button>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      url: '',
      format: 'json',
      separator: ''
    }
  },
  methods: {
    onConfirm() {
      var url = `/api/thread/?url=${encodeURIComponent(this.url)}&format=${this.format}`
      if(this.format === 'text')
        url += `&separator=${this.separator}`
      document.location = url
    }
  }
}
</script>

<style scoped>
.url-form {
  max-width: 1024px;
  margin-left: auto;
  margin-right: auto;
}
</style>
