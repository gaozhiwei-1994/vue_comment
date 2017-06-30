<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" class="form-control" placeholder="用户名" v-model.trim="comment.username">
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea class="form-control" rows="6" placeholder="评论内容" v-model.trim="comment.content"></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="button" class="btn btn-default pull-right" @click="add">提交</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    props: ['addComment'],
    data () {
      return {
        comment: {}
      }
    },
    methods: {
      add () {
        const comment = this.comment
        //console.log(comment)
        if(!comment.username || !comment.content){
          alert('请输入内容')
          this.comment = {}
          return
        }
        this.addComment(comment)
        this.comment = {}
      }
    }
  }
</script>

<style>

</style>
