<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" class="form-control" placeholder="用户名" v-model="name">
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea class="form-control" rows="6" placeholder="评论内容" v-model="content"></textarea>
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
      props:{
        addCommont:Function
      },
        data() {
          return {
            name: '',
            content: ''
          }
        },
      methods:{
        add(){
          //判断数据是否合法
          const name = this.name.trim()
          const content = this.content.trim()
          if(!name || !content){
            alert('姓名或内容没有输入')
            return
          }
          //根据数据封装成commont对象
          const commont = { name , content}
          //添加到commonts中
          this.addCommont(commont)
          //清除数据
          this.name=''
          this.content=''
        }
      }
    }
</script>

<style>

</style>
