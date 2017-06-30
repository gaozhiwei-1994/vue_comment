<template>
    <div>
      <div class="handle">
        <a href="javascript:;" @click="remove">删除</a>
      </div>
      <p class="user"><span >{{comment.username}}</span><span>说:</span></p>
      <p class="centence">{{comment.content}}</p>
    </div>
</template>

<script>
  export default {
    props: ['comment','removeComment'],
    methods: {
      remove () {
        const username = this.comment.username
        if(confirm(`确认删除${username}吗`)){
          console.log(this.comment)
          this.removeComment(this.comment)
        }
      }
    }
  }
</script>

<style scoped>
</style>
