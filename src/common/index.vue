<template>
  <div class="index-wrap">
    <div class="index-left">
      <div class="index-left-block">
        <h2>树形侧边导航栏</h2>
        <ul v-for="menuItem in theModel">
          <myTree class="item" :model="menuItem"></myTree>
        </ul>
      </div>
    </div>
    <div class="index-medium">
      <div class="index-right-block">
        <h2 align="center">数据展示</h2>
        <div id="myChart" :style="{width: '300px',height: '300px'}"></div>
      </div>
    </div>
    <div class="index-right">
      <div class="index-left-block">
        <h2>功能面板</h2>
        <ul>
          <br/>
          <div>
          <button class="button">增加</button>
          </div>
          <br/>
          <div>
          <button class="button">删除</button>
          </div>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import myTree from '../components/treeMenu.vue'

var myData =[{
  'id': '1',
  'menuName': '大学信息',
  'menuCode': '10',
      'childList' : [
      {
        'menuName': '教务信息',
        'menuCode': '12',
        'childList': [
          {
            'menuName': '学生成绩',
            'menuCode': '111'
          },
          {
            'menuName': '教师授课 ',
            'menuCode': '112'
          }]
      },
      {
        'menuName': '人事信息',
        'menuCode': '12',
        'childList': [
            {
                'menuName': '教师职称',
                'menuCode': '121'
            }]
      },
      {
          'menuName': '保卫信息',
          'menuCode': '13'
      }]

}]

export default {
  name: 'items',
  props: ['model'],
  components: {
    myTree
  },
  data () {
    return {
      theModel: myData
    }
  },
  mounted() {
  },
  methods: {
  }
}
</script>

<style scoped>
.index-wrap {
  width: 1500px;
  margin: 0 auto;
  overflow: hidden;
}
.index-right {
  float: left;
  width: 300px;
  text-align: center;
}
.index-left {
  float: left;
  width: 300px;
  text-align: left;
}
.index-medium {
  float: left;
  width: 900px;
}
.index-left-block, .index-right-block{
  height: 700px;
  margin: 15px;
  background: #fff;
  box-shadow: 0 0 1px #ddd;
}

.index-left-block h2,.index-right-block h2 {
  background: #4fc08d;
  color: #fff;
  padding: 20px 20px;
  font-size: 1.5em;
}
.cb{
  height: 100px;
  width: 30px;
  margin:0 5px 0 5px;
}
.item {
  cursor: pointer;
}
.button {
  background-color: gray; /* Green */
  border: none;
  color: white;
  padding: 10px 30px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 15px;
}
ul{
  line-height: 40px;
  list-style-type: dot;
}

li div:active,li div:hover {
  background: #9FDABE;
  color: #eee;
}

ul li:hover {
  background: #A6C2B0;
}

</style>
