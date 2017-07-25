<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">

      <add :add-comment="addComment"></add>
      <!--通过:comments="comments" :delete-comment="deleteComment"通过数据向我的子组件传递数据-->
      <list :comments="comments" :delete-comment="deleteComment" ></list>

    </div>
  </div>

</template>


<script>
  import add from './add.vue'
  import list from './list.vue'
  export default {
    data () {
      return {
        comments: []
      }
    },
   //执行异步代码
    created () {
      //模拟发送ajax请求 迅速获取数据
      setTimeout(()=>{
      //得到数据
     const comments=  [
       {
         username:'tom',
         content:'Vue 不错'
       },
       {
         username: 'sunwukong',
         content:'很好学的'
       }

     ]
        //更新数据
        this.comments =comments

      },1000)
    },
    methods: {
      addComment (comment){
        //把更新的值压入comments的数组里
        this.comments.unshift(comment)

      },
      deleteComment (index) {

        this.comments.splice(index, 1)
      }

    },



    components: {
      add,
      list
    }
  }



</script>

<style></style>
