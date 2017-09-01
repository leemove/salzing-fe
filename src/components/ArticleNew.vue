<template>
<div class="page-article-new">
  <h1>新建文章</h1>
      <mt-field label="标题" placeholder="没有标题的文章也是一篇好文章" v-model="title"  :attr="{ maxlength: 10 }"></mt-field>
      <mt-field label="作者" placeholder="请署名" v-model="author"  :attr="{ maxlength: 10 }"></mt-field>
      <vue-html5-editor @focus.native="focusHandel" :content="articleString" @change="updateData" :height="200"></vue-html5-editor>
      <div class="submit">
        <mt-button type="primary" @click="submit">提交</mt-button>
      </div>
</div>
</template>
<script>
export default {
  data () {
    return {
      articleString: '',
      author: '',
      title: ''
    }
  },
  components: {
  },
  methods: {
    updateData (c) {
      this.articleString = c
    },
    focusHandel () {
    },
    async submit () {
      console.log(this.articleString)
      try {
        this.$indicator.open()
        var res = await this.$http.post('/article/new', {
          author: this.author,
          content: this.articleString,
          title: this.title
        })
        this.$indicator.close()
      } catch (error) {
        this.$indicator.close()
        this.$toast('网络不太稳定,请重试.')
      }
      console.log(res)
      if (res.data.status !== 'ok') {
        this.$toast(res.data.status)
      } else {
        this.$router.push('/')
      }
    }
  }
}
</script>
<style lang="scss" scoped>

</style>

