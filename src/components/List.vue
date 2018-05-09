<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 v-show="commonts.length === 0">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <Item v-for="(commont , index) in commonts" :key="index"
            :commont="commont" :deleteC="deleteC" :index="index"/>
    </ul>
  </div>
</template>

<script>
  import Item from './Item'
    export default {
      props:['commonts','deleteC'],
      components:{
        Item
      },
    }
</script>

<style>
  .reply {
    margin-top: 0px;
  }

</style>
