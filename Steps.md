# set up environment

- [MYSQL5.7]
- [JDK1.9]
- [NODE14.16.0]
- [NAVICAT]
- [IDEA]

- vue cli

```sh
npm install -g @vue/cli
```

- element

```sh
npm i element-ui -S
```

# check version

```sh
java --version
node -v
vue -V
```

# cretae vue project

```sh
cd into folder
vue create projectName
```

# start project

```sh
npm run serve
```

# update 1,update view

App.view

```
<template>

  <div id="app">
    <router-view/>
  </div>
</template>

<style>
#app{
  height: 100%;
}
</style>
```

global.css

```
html,body,div{
    margin: 0;
    padding: 0;
}
html,body{
    height:100%;
}
```

HomeView.vue

```
<template>
  <div style="height:100%">
    <el-container style="height: 100%; border: 1px solid #eee">
      <el-aside width="200px" style="background-color: rgb(238, 241, 246); height:100%; overflow:hidden">
        <el-menu :default-openeds="['1', '3']">
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i>导航一</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title"><i class="el-icon-menu"></i>导航二</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="2-1">选项1</el-menu-item>
              <el-menu-item index="2-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="2-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="2-4">
              <template slot="title">选项4</template>
              <el-menu-item index="2-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title"><i class="el-icon-setting"></i>导航三</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="3-1">选项1</el-menu-item>
              <el-menu-item index="3-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="3-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="3-4">
              <template slot="title">选项4</template>
              <el-menu-item index="3-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-menu>
      </el-aside>

      <el-container>
        <el-header style="text-align: right; font-size: 12px; boarder-bottom:1px solid #ccc; line-height: 60px">
          <el-dropdown>
            <i class="el-icon-setting" style="margin-right: 15px"></i>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>查看</el-dropdown-item>
              <el-dropdown-item>新增</el-dropdown-item>
              <el-dropdown-item>删除</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <span>王小虎</span>
        </el-header>

        <el-main>
          <el-table :data="tableData">
            <el-table-column prop="date" label="日期" width="140">
            </el-table-column>
            <el-table-column prop="name" label="姓名" width="120">
            </el-table-column>
            <el-table-column prop="address" label="地址">
            </el-table-column>
          </el-table>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  components: {
    // HelloWorld
  },
  data: function () {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    }
    return {
      tableData: Array(10).fill(item),
      msg: 'hello yuxin'
    }
  }
}
</script>

```

main.js

```
import Vue from 'vue'
import App from './App.vue'
import router from './router'
import ElementUI from 'element-ui'
import 'element-ui/lib/theme-chalk/index.css'
import './assets/global.css'

Vue.config.productionTip = false
Vue.use(ElementUI, { size: 'small' })

new Vue({
  router,
  render: h => h(App)
}).$mount('#app')
```

# update2 beautify

HomeView.vue

```
<template>
  <div style="height:100%">
    <el-container style="height: 100%; border: 1px solid #eee">
      <el-aside width="sideWidth+ 'px'" style="background-color: rgb(238, 241, 246 ); height:100%; overflow:hidden">
        <el-menu :default-openeds="['1', '3']" style="min-height:100%" background-color="rgb(48, 65, 86)" overflow-x:hidden
                 text-color ="#fff" active-text-color="#ffd04b" :collapse-transition="false"
                 :collapse="isCollapse"
        >
          <div>
            <img src="../assets/logo.png" alt="" style="width: 20px; position: relative; top: 5px; margin-right: 5px; margin-left: 5px">
            <b style="color: white" v-show="logoTextShow">management system</b>
          </div>
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i></template>
            <span slot="title">导航一</span>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title"><i class="el-icon-menu"></i></template>
            <span slot="title">导航二</span>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="2-1">选项1</el-menu-item>
              <el-menu-item index="2-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="2-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="2-4">
              <template slot="title">选项4</template>
              <el-menu-item index="2-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title"><i class="el-icon-setting"></i></template>
            <span slot="title">导航三</span>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="3-1">选项1</el-menu-item>
              <el-menu-item index="3-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="3-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="3-4">
              <template slot="title">选项4</template>
              <el-menu-item index="3-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-menu>
      </el-aside>

      <el-container>
        <el-header style="font-size: 12px; boarder-bottom:1px solid #ccc; line-height: 60px;
        display:flex">
          <div style="flex: 1; font-size: 18px">
            <span :class="collapseBtnClass" style="cursor: pointer" @click="collapse"></span>
          </div>
          <el-dropdown style="width: 100px; cursor: pointer">
            <span >王小虎</span><i class="el-icon-bottom" style="margin-left: 5px"></i>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>个人信息</el-dropdown-item>
              <el-dropdown-item>退出</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <span>王小虎</span>
        </el-header>

        <el-main>
          <el-table :data="tableData">
            <el-table-column prop="date" label="日期" width="140">
            </el-table-column>
            <el-table-column prop="name" label="姓名" width="120">
            </el-table-column>
            <el-table-column prop="address" label="地址">
            </el-table-column>
          </el-table>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  components: {
    // HelloWorld
  },
  data: function () {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    }
    return {
      tableData: Array(10).fill(item),
      msg: 'hello yuxin',
      collapseBtnClass: 'el-icon-s-fold',
      isCollapse: false,
      sideWidth: 200,
      logoTextShow: true
    }
  },
  methods: {
    collapse () {
      // click to collapse
      this.isCollapse = !this.isCollapse
      if (this.isCollapse) { // collapse
        this.sideWidth = 64
        this.logoTextShow = false
        this.collapseBtnClass = 'el-icon-s-unfold'
      } else { // expand
        this.sideWidth = 200
        this.logoTextShow = true
        this.collapseBtnClass = 'el-icon-s-fold'
      }
    }
  }
}
</script>

```

App.vue

```
<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style>
#app{
  min-height: 100vh;
}
</style>
```

global.css

```
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

# next update start from here

# next update end at here

[//]: # "These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen."
[jdk1.9]: https://www.oracle.com/sg/java/technologies/downloads/#jdk19-windows
[mysql5.7]: https://www.mysql.com/downloads/
[node14.16.0]: https://nodejs.org/en/download/
[navicat]: https://www.navicat.com/en/download/navicat-premium?gclid=CjwKCAiA5sieBhBnEiwAR9oh2sbX6JPEv372fub8UnseGZmBEmjEdphUSKAjbr_mkf38H4h7dFwD5hoCockQAvD_BwE
[idea]: https://www.jetbrains.com/idea/download/#section=windows
