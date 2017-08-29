<template>
  <div class="page-home">
    <vue-html5-editor :content="content" @change="updateData" :height="200"></vue-html5-editor>
    <mt-button type="primary" @click="submit">提交</mt-button>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    // hahah
    return {
      content: ''
    }
  },
  methods: {
    submit () {
      console.log(this.content)
    },
    updateData (c) {
      this.content = c
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="scss" scoped>
</style>
