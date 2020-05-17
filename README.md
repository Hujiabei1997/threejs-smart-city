# threejs-smart-city
基于threejs实现城市模型的web端3D展示

项目技术栈：

1.HTML

2.创建场景（要素：scene/background/camera/render/Light/axes/）

4.stats（性能监视器）加载

5.Controls轨道控制器：使鼠标可以旋转角度查看模型

6.xhr（XMLHttpRequest）控制台显示加载信息

7.加载城市模型及纹理

8.THREE.Raycaster 实现模型选中与信息显示（重点理解：利用光线投射原理获取与光线相交的事件数组及三种坐标系转化，参考：https://blog.csdn.net/ithanmang/article/details/80897888）

9.基于EffectComposer实现辉光(bloompass)效果（城市道路等场景）

10.基于focusShader使中央区域渲染的比较锐利，单周围比较模糊，加强场景效果

11.基于Sprite进行半透明贴图标识城市场景（例如可在图中某位置进行火灾报警标识）

12.场景循环渲染animate()

项目不足：

1.three.js是Webgl的Javascript封装，可以在Web端进行3D展示，但对于城市场景缺少空间信息数据和地理底图，后续可考虑使用cesium(https://cesium.com/cesiumjs/),cesium是一个开源的3D Mapping，可以创建用于共享动态地理空间数据的交互式Web应用程序。

2.项目暂时未实现一些动态效果，例如地铁在城市中穿行。路线循环流动效果可以创建一个管道，然后增加一个路径一样的贴图，设置wrap为重复，在animate中不断更改texture.offset即可。

3.目前项目仅限于前端展示，没有后台服务器和数据库。后续后端可基于nodejs平台express框架，实现用户点击某一模型可向后台请求并返回数据进行弹窗显示等功能，开发一个完整的系统。

参考博客：https://blog.csdn.net/qq_37540004/article/details/102862348
