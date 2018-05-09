<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对React的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Add :addCommont="addCommont"/>
      <List :commonts="commonts" :deleteC="deleteC"/>
    </div>
  </div>
</template>

<script>
  import Add from './components/Add'
  import List from './components/List'
  export default {
    components:{
      Add , List
    },
    data() {
      return {
        commonts:/*[
          {name:'Tom' , content:'vue 还不错'},
          {name:'Danny' , content:'vue 不错'},
          {name:'Jenny' , content:'vue 挺难de'}
        ]*/
       JSON.parse(localStorage.getItem('commont-key') || '[]')
      }
    },
    methods:{
      addCommont(commont){
        this.commonts.unshift(commont)
      },
      deleteC(index){
        this.commonts.splice(index , 1)
      }
    },
    watch:{
      commonts:{
        deep:true,
        handler:function (value) {
          localStorage.setItem('commont-key',JSON.stringify(value))
        }
      }
    }
  }

</script>

<style>

</style>
