<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 v-show="comments.length===0">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <item v-for="(comment,index) in  comments" :comment="comment"
            :key="index" :delete-comment="deleteComment" :index="index"></item>

    </ul>
  </div>
</template>
<script>
  import item from './item.vue'

export default{
  // props 用来接收父组件的数据 和 数据类型 主要接受的是 :comments="comments" :delete-comment="deleteComment"
  props: ['comments','deleteComment'],
  components: {
    item
  }
}


</script>
<style>
  .reply {
    margin-top: 0px;
  }


</style>
