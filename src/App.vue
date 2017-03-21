<template>
  <div>
    <el-menu theme="dark" :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <el-menu-item index="1">Api Center</el-menu-item>
      <el-submenu index="2">
        <template slot="title">我的api</template>
        <el-menu-item index="2-1">选项1</el-menu-item>
        <el-menu-item index="2-2">选项2</el-menu-item>
        <el-menu-item index="2-3">选项3</el-menu-item>
      </el-submenu>
      <el-menu-item index="3"><a href="#" target="_blank">个人信息管理</a></el-menu-item>
    </el-menu>
    <div class="line"></div>

    <el-carousel :interval="4000" type="card" height="500px">
      <el-carousel-item v-for="item in 6">
        <h3>{{ item }}</h3>
      </el-carousel-item>
    </el-carousel>
    <el-row :gutter="20">
      <el-col :span="12" :offset="6"><div class="grid-content lg-purple">
        <el-input
              placeholder="请输入关键字"
              icon="search"
              v-model="input2"
              :on-icon-click="handleIconClick" >
            </el-input>
      </div></el-col>
    </el-row>


    <el-row class="bar">
      <el-col :span="8" v-for="(o, index) in 5" :offset="index > 0 ? 2 : 2">
        <el-card :body-style="{ padding: '20px' }" class="eachcard">
          <div style="padding: 24px;">
            <span>时间你好。。。。。。</span>
            <div class="bottom clearfix">
              <time class="time">{{ currentDate }}</time>
              <el-button type="text" class="button">操作按钮</el-button>
            </div>
          </div>
        </el-card>
      </el-col>
    </el-row>

  </div>
</template>

<script>
export default {
  data () {
    return {
      name: 'app',
      currentDate: new Date(),
      input2: ''
    }
  },
  methods: {
    handleIconClick (ev) {
      console.log(ev)
    }
  }
}
</script>

<style src="./assets/css/app.css" scoped></style>
