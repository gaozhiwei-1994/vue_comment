<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对VUE的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <add :addComment="addComment"></add>
      <list :comments="comments" :removeComment="removeComment"></list>
    </div>
  </div>
</template>

<script>
  import add from './add.vue'
  import list from './list.vue'
  export default {
    //初始化数据
    data () {
      return {
        comments: []
      }
    },
    created () {
      setTimeout(()=>{
        this.comments = [
          {username: '悟空',content: 'vue,不错'},
          {username: '八戒',content: 'vue,很好'}
        ]
      },100)
    },
    methods: {
      //添加提交评论
      addComment (comment) {
        this.comments.unshift(comment)
      },
      //删除评论
      removeComment (comment) {
        var index = this.comments.indexOf(comment)
        this.comments.splice(index,1)
      }
    },
    //组件 标签映射
    components: {
      add,
      list
    }
  }
</script>

<style>

</style>
