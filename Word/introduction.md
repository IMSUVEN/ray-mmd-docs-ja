# ·Ray的介绍
[返回目录](../ReadMe.md) 
- ### 关于本说明文档的观看说明
------------
　在本说明文档中将会出现许多专业术语，有一部分会贴有解释说明，还有一部分需要您自己Baidu或者Google
- ### 基于物理的渲染 
------------
　Ray-MMD是Rui（github账户：@ray-cast，Twitter：[Rui_cg](https://twitter.com/Rui_cg)），用hlsl语言所写，基于MikuMikuEffect的一个渲染库
　目前Ray已经更新到了稳定版1.5.0，并且在不断的更新新的功能和效果。
　如果您喜欢这个渲染，希望您可以[赞助作者](https://github.com/ray-cast/ray-mmd/blob/master/README_chs.md)，你的帮助将能使这个渲染走的更远

- ### Ray的系统需求
------------
* [MikuMikuDance](http://www.geocities.jp/higuchuu4/index_e.htm) - 926ver (x64) (没有抗锯齿)
* [MikuMikuEffect](https://bowlroll.net/file/35012) - 037ver (x64)
* Direct3D 9 With Shader Model 3.0 (ps_3_0)

- ### 特性
------------
* 基于物理的材质: 基本色, 金属性, 光滑/粗糙度, 反射率, 自发光, 等 
* 模拟清漆的多层材质 
* 模拟布料材质的镜面反射 
* 各向异性的多层材质 
* 湿度贴图的支持 
* 近似的次表面散射用于模拟玉器和皮肤 
* GGX镜面光照模型和burley的漫反射光照模型 
* 物理的光源 
* 点光源, 聚光灯, 太阳光, 面积光, IES 的多光源的支持 
* 点光源和聚光的IES配置 
* PCF, VSM, PSSM 的软阴影 
* 基于双抛面的全方位点光源阴影
* 高动态范围照明(High-Dynamic Lighting)
* 点光源, 聚光灯, IES 的体积光 
* 方形和球形的体积雾 
* 云隙光效果 
* 模拟雾气和天空的近似的大气散射 
* 地面雾特效 
* 基于RGBT编码的高动态天空盒 
* 基于RGBT编码的高动态图像照明(Image-Based Lighting) 
* 屏幕空间反射 
* 屏幕空间环境光遮蔽 
* 屏幕空间次表面散射 
* 后处理的景深特效 
* 后处理的泛光特效 
* 后处理的人眼适应特效 
* 后处理的色调映射 (ACES-like,Reinhard,Hable,Hejl2015,NaughtyDog support) 
* 后处理的色彩调整 
* FXAA抗锯齿 
* SMAA抗锯齿 

[使用协议 (MIT)](https://raw.githubusercontent.com/ray-cast/ray-mmd/master/LICENSE.txt)
------------
	Copyright (C) 2016-2018 Rui. 保留所有版权.

	https://github.com/ray-cast/ray-mmd

	被授权人权利:
	被授权人有权利使用、复制、修改、合并、出版发行、散布、再授权及贩售软件及软件的副本。
	被授权人可根据程序的需要修改授权条款为适当的内容。

	被授权人义务:
	在软件和软件的所有副本中都必须包含版权声明和许可声明。由版权持有人及其他责任者“按原样”提供，包括
	但不限于商品的内在保证和特殊目的适用，将不作任何承诺，不做任何明示或暗示的保证。 在任何情况下，不
	管原因和责任依据，也不追究是合同责任、后果责任或侵权行为(包括疏忽或其它)，即使被告知发生损坏的可
	能性，在使用本软件的任何环节造成的任何直接、间接、偶然、特殊、典型或重大的损坏(包括但不限于使用替
	代商品的后果：使用、数据或利益的损失或业务干扰)，版权持有人、其他责任者或作者或所有者概不承担任何责任

	其他重要特性:
	此授权条款并非属Copyleft的自由软件授权条款，允许在自由/开放源码软件或非自由软件（proprietary software）所使用。
	MIT的内容可依照程序著作权者的需求更改内容。此亦为MIT与BSD（The BSD license, 3-clause BSD license）本质上不同处。
	MIT条款可与其他授权条款并存。另外，MIT条款也是自由软件基金会（FSF）所认可的自由软件授权条款，与GPL兼容

[下一章 2.下载](download.md)