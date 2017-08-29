<template>
  <div class="page-home">
    <mt-button type="primary" @click="goNewArticle">新建文章</mt-button>
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
    goNewArticle () {
      // console.log(this.content)
      this.$router.push('/article/new')
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="scss" scoped>
</style>
