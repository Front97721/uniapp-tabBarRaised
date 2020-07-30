# uniapp-tabBarRaised
uniapp 实现tabBar图标凸起的两种方式（App端）

# management

> A Vue.js project

#### 技术栈

vue2.x + vuex + vue-router + webpack + ES6/7 + axios + elementUI + 阿里图标iconfont + stylus

#### 效果图

![image](https://github.com/ly97721/vue-element-admin/blob/master/screenshots/%E5%93%81%E7%B1%BB%E7%AE%A1%E7%90%86.png)
![image](https://github.com/ly97721/vue-element-admin/blob/master/screenshots/%E9%A6%96%E9%A1%B5-%E5%9B%BE%E8%A1%A8%E7%AE%A1%E7%90%86.png)
![image](https://github.com/ly97721/vue-element-admin/blob/master/screenshots/%E5%95%86%E5%93%81%E7%AE%A1%E7%90%86.png)
![image](https://github.com/ly97721/vue-element-admin/blob/master/screenshots/%E6%B7%BB%E5%8A%A0%E5%95%86%E5%93%81.png)

#### 说明

>  本项目主要用于vue2.x 架构一个后台管理平台项目

>  后端提供.do请求接口路径,axios发送请求到该接口，会返回一系列数据,进行相对应的界面渲染

>  为了方便后期修改使用，模拟数据在页面中，具体修改看下面【强调】

>  开发环境 win 10  Chrome 84.0.4136.7

#### 强调

项目请求具有默认假数据，例如：
``` bash
//商品数据
				listData: [
          {
            id:"256986",
            name:"内蒙古华章大棉袄",
            price:"￥158",
            status:""
          },
          {
            id:"256986",
            name:"内蒙古华章大棉袄",
            price:"￥158",
            status:""
          }
        ]

        created() {
        	this.$axios.post("api/manage/product/list.do")
        		.then(res => {
        			this.listData = res.data.data.list
        			this.total = res.data.data.pages * 10 //根据请求过来的数据改变页码数
        	})
        }
```
接口地址需要修改config/index.js文件 dev
``` bash
proxyTable: {
    '/api': {
        target: 'http://xxx.xxx.xxx.xxx:xxx', // 你请求的第三方接口
        changeOrigin: true, // 在本地会创建一个虚拟服务端，然后发送请求的数据，并同时接收请求的数据，这样服务端和服务端进行数据的交互就不会有跨域问题
        pathRewrite: { // 路径重写，
            '^/api': '/api' // 替换target中的请求地址，也就是说以后你在请求http://api.jisuapi.com/XXXXX这个地址的时候直接写成/api即可。
        }
    }
},

```

## Related parameters

``` bash
商品数据：goodsData 
商品详情：goodsDetails 
获取详情：getGoodsDetails 

品类数据：categoryData 
获取品类：getCategoryData 
添加品类：addCategory

订单数据：odersData
订单详情：odersDetails
获取详情：getOdersDetails

一级品类：primaryMenu 
当前产品的一级品类: nowPrimaryMenu 
二级品类：towMenu 
当前产品的二级品类: nowTowMenu 

用户列表： userListData

```

## Project start

``` bash

## Build Setup

# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report


```
## catalogue About it

``` bash
.
├── build                                       // webpack配置文件
├── config                                      // 项目打包路径
├── dist                                        // 项目打包文件
├── screenshots                                 // 项目截图
├── src                                         // 源码目录
│   ├── api                                     // 数据请求入口文件
│   │   ├── axiosFun                            // axios请求及通用方法封装
│   │
│   │── assets                                  // 静态文件
│   │   ├── icon                                // icon矢量图标
│   │   ├── img                                 // 界面所需要图片
│   │
│   │── common                                  // 通用文件
│   │   ├── stylus                              // stylus通用样式
│   ├
│   │── components                              // 组件
│   │   ├── HeaderNav                           // 头部导航栏公共组件
│   │   ├── LeftNav                             // 左边导航栏公共组件
│   │   ├── PageNumber                          // 页码公共组件
│   │   ├
│   │── router                                  // 路由
│   │   │
│   │──utils                                    // 个人工具库
│   │   │
│   │── view                                    // 页面
│   │   ├── basic                               // 商品
│   │   │   └── goods
│   │   │   │    ├── Goods.vue                  // 商品管理
│   │   │   │    ├── addGoods.vue               // 添加商品
│   │   │   │    ├── toViewGoods.vue            // 商品详情
│   │   │   │    └── modifyGoods .vue           // 编辑商品
│   │   │   └── category
│   │   │       ├── Category.vue                // 品类管理
│   │   │       └── addCategory.vue             // 添加商品
│   │   ├── order
│   │   │   └── Orders.vue                      // 订单管理
│   │   │   └── lookOrders.vue                  // 查看订单
│   │   ├── user
│   │   │   └── Usres.vue                       // 用户管理
│   │   ├── home
│   │   │   └── Chart.vue                       // 图表管理
│   │   │
│   │   ├── index.vue                           // 首页
│   │   │
│   │   ├── login.vue                           // 登录
│   │   │
│   │── vuex                                    // vuex状态管理
│   │   │
│   │── App.vue                                 // 页面入口文件
│   │   │
│   │── main.js                                 // 程序入口文件，加载各种公共组件
│   │
├── static
│   ├── favicon .ico                            // 浏览器加载logo
│   │
├── .eslintrc.js                                // eslint代码校验规则
│   │
├── index.html                                  // 入口html文件
│   │
├── package.json                                // 配置文件


```
## Browser support

Modern browsers and IE 10+.

``` bash

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
