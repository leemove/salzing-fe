<template>
<div class="page-article-new">
  <h1>新建文章哈哈哈</h1>
      <vue-html5-editor @focus.native="focusHandel" :content="articleString" @change="updateData" :height="200"></vue-html5-editor>
      <mt-field label="作者" placeholder="请署名" v-model="author"  :attr="{ maxlength: 10 }"></mt-field>
</div>
</template>
<script>
export default {
  data () {
    return {
      articleString: '',
      author: ''
    }
  },
  components: {
  },
  methods: {
    updateData (c) {
      this.content = c
    },
    focusHandel () {
      console.log(233)
    }
  }
}
</script>
<style lang="scss" scoped>

</style>

