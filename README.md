# Vue2.5开发去哪儿网App

> 从基础到项目，从零开发去哪儿网App

## 在开发过程中遇到的一些困难及解决方案

### 1.Vue项目中使用iconfontcss，无法显示正确图标

1).文件存放路径为
  
![](http://oriq21dog.bkt.clouddn.com/bloc/2018-05-30-QQ20180530-153237.png)  

2).iconfont.css里面的路径设置
![](http://oriq21dog.bkt.clouddn.com/bloc/2018-05-30-QQ20180530-153358.png)

3).iconfont的使用:class为iconfont,内容为16进制  
![](http://oriq21dog.bkt.clouddn.com/bloc/2018-05-30-QQ20180530-153547.png)

### 2.轮播图padding-bottom的值 200/750 = 26.67

![](http://oriq21dog.bkt.clouddn.com/bloc/2018-05-30-QQ20180530-163433.png)

### 3.轮播图索引点的颜色设置 
 
```
.wrapper >>> .swiper-pagination-bullet-active
    background : #fff
```
### 4.一像素边框问题解决

引入border.css,在用到的地方使用 `class="border-bottom"`

### 5.端口号被占用或者非正常退出时端口号改变的问题

```
我配置的端口号为 8089

1. lsof -i tcp:端口号
2. kill -9 被占用的pid
3. npm run start

```
![](http://oriq21dog.bkt.clouddn.com/bloc/2018-06-01-QQ20180601-093059.png)
