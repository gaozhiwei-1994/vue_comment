<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <li class="list-group-item" v-for="comment in comments">
        <item :comment="comment" :removeComment="removeComment"></item>
      </li>
    </ul>
  </div>
</template>

<script>
  import item from './item.vue'
  export default {
    props: ['comments','removeComment'],
    components: {
      item
    }
  }
</script>

<style scoped>
</style>
