<template>
  <li class="list-group-item">
    <div class="handle">
      <a href="javascript:;" @click="deleteCommont">删除</a>
    </div>
    <p class="user"><span >{{commont.name}}</span><span>说:</span></p>
    <p class="centence">{{commont.content}}</p>
  </li>
</template>

<script>
    export default {
        props:{
          commont:Object,
          deleteC:Function,
          index:Number
        },
      methods:{
        deleteCommont(){
          this.deleteC(this.index)
        }
      }
    }
</script>

<style>
  li {
    transition: .5s;
    overflow: hidden;
  }

  .handle {
    width: 40px;
    border: 1px solid #ccc;
    background: #fff;
    position: absolute;
    right: 10px;
    top: 1px;
    text-align: center;
  }

  .handle a {
    display: block;
    text-decoration: none;
  }

  .list-group-item .centence {
    padding: 0px 50px;
  }

  .user {
    font-size: 22px;
  }
</style>
