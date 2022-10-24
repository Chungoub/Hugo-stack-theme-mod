---
title: ChunのBlender学习记录 Lv.1
description:
date: 2022-09-28
tags:
    - Blender
categories:
    - Software
---

## 基础操作
- 三视图：小键盘，俯视图 7；正视图 1；侧视图 3；四视图模式 ctrl+alt+Q
- 移动 grab：选中物体后鼠标点击左侧边栏自由拖动，快捷键G；按住坐标轴拖动可以沿着坐标轴移动，按住平面拖动可以在平面内移动。
- 旋转 rotate左侧边栏旋转快捷键R；按住与坐标轴相同的曲线可以沿着对应坐标轴旋转。
- 缩放 scale：左侧边栏缩放快捷键S；按住坐标轴拖动可以沿着坐标轴缩放，按住平面拖动可以保持该方向大小不变在另外两个方向按比例缩放。
- 复位：alt+G移动复位，alt+R旋转复位，alt+S缩放复位。也可以在transform中手动输入原始数据进行复位。
- 删除：选中物体后按X，提示是否删除；选中物体后Delete不提示直接删除。
- 复制：ctrl+C/V在原位复制；shift+D复制后直接抓取。
- 游标 cursor: 可以通过手动移动改变位置，可以通过选中物体->右键snap->调整游标位置，也可以在游标工具上方选择吸附模式（激活小磁铁标志就是自动吸附，选择vertex/edge/face则是分别吸附点线面）。可在右上角的overlay界面打开或关闭cursor显示。
- 原点 origin: 通过游标工具将游标定位到想要选择的点，再右键set origin选择将原点设置为游标所在位置即可。

## 认识模型
- 点线面：长按选择工具可以弹出二级选框，有框选模式、刷选模式、套索模式等。shift加选，ctrl减选，a全选。
- 面的基础操作：细分subdivide，在左下角设置分割的面数；删除面，可以选择仅删除面或者删除面和线；挤出extrude，将一个面向外拉或者向内压缩；内插insert，选中面后快捷键i，将选中的面向内缩圈，可以设置为外插outset。
- 面的分割：尖分poke faces，在面中心添加新的顶点拆分成三角形；三角化triangulate faces，不添加新的顶点将面拆成三角形；融并面dissolve faces，将分割的面融合为一个面。切割工具knife，快捷键K，shift（快捷键因人而异）吸附线的中点，回车确认；整体切割biset，选中多个面划一刀，黄色箭头表示法线方向，填充fill可以补上切面。
- 面的法向：在右上角Overlays中可以打开显示法向normals的按钮和面朝向face orientation的开关，用于确定模型的内外两面；也可以在Shading中勾选背面剔除Backface Culling，取消对内面的渲染。
- 面的填充：相当于删除面的反向操作，选中所有边线后快捷键F即可自动填充，也可在上方栏的Face中手动选择，普通填充方式fill是alt+F用三角形填充，栅格填充grid fill是用四边形填充，山歌填充只支持偶数边线的填充。
- X光模式：右上角Toggle X-Ray可以查看透明的模型，快捷键alt+Z。
![边线倒角示例](bevel.png)![循环面切变示例](shear.png)
- 线的基础操作：切分subdivide和面相同，滑移edge slide沿着邻边轨道进行移动，融并dissolve将边线消除使两个面相融，倒角bevel将边线磨平；环切loop cut，循环边通过alt+LMB选中，并排边通过CTRL+ALT+LMB选中（就是纵向选择alt加左键，横向选择alt+ctrl+左键）；切变shear可以在选中循环边或循环面之后向内或向外扭曲。