<template>
<div>
    <div class="item" v-for="(item,index) in list" :key='index' >
        <div :class="['yuan',item.flagclass]">{{item.flag}}</div>
        <h6><strong>标题：{{item.title}}</strong></h6>
        <p><span>发布于：{{item.start_time}}</span>  发布人：{{item.nickname}}</p>
        <p><span>分类：{{item.type}}</span> 悬赏金额：{{item.money}}</p>
    </div>
    <p id="load">点击加载更多...</p>
    <p id="loaded">已加载全部...</p>
</div>
</template>
<script>
import axios from 'axios'
import $ from 'jquery'
export default {
  name: 'Axios',
  data: function () {
    return {
      list: []
    }
  },
  mounted () {
    var self = this
    var page = 0
    var num = page + 5
    function getData (url) {
      axios.get(url).then(res => {
        if (res.data.length < 5) {
          $('#load').hide()
          $('#loaded').show()
        }
        self.list = self.list.concat(res.data)
      })
    }
    $(function () {
      $('#load').click(function () {
        page = page + 5
        let url = '/api/all1?phone=18268756048&page=' + page + '&num=' + num
        getData(url)
      })
    })
    let url = '/api/all1?phone=18268756048&page=0&num=5'
    getData(url)
  }
}

</script>
<style>
.item{
position: relative;
width: 100%;
background: white;
padding: 10px;
margin: 0px auto;
box-sizing: border-box;
border: none;
box-shadow: 1px 1px 3px rgba(0,0,0,0.5);
}
.item p{
font-size: 10px;
}
.item p span{
margin-right: 20px;
}
.yuan{
position: absolute;
border-radius: 50%;
top: 30px;
right:30px;
width: 50px;
height: 50px;
line-height: 50px;
text-align: center;
transform: rotate(-25deg);
font-size: 8px;
border:1px solid black;
}
.gqclass{
border: 1px solid grey;
color: grey;
}
.jqclass{
border: 1px solid red;
color: red;
}
.jjclass{
border: 1px solid blue;
color: blue;
}
.yjjclass{
border: 1px solid green;
color: green;
}
#load,#loaded{
font-size: 10px;
text-align: center;
margin: 5px 0px;
}
#loaded{
display: none;
}
</style>>
