# ·Ray的各文件夹说明
[返回目录](../ReadMe.md) 

- ## 该页介绍
　这是Ray文件夹中各个文件夹和文件的简要说明。这是为了向您介绍该文件夹或文件的用途和类型

* ## 根文件夹下的文件和文件夹

    | 文件夹名         | 用途说明 |
    | :----------------- | :--- |
    | LICENSE.txt        | Ray-mmd的MIT许可证</br>既Ray-MMD的使用协议</br>介绍页下有说明 |
    | `README.md`        | Ray-mmd的英文说明 |
    | ray.conf           | ray-mmd的全局设置</br>有关全局设置的详细说明请看5.[全局设置和MME效果分配](Conf.md)|
    | ray_advanced.conf  | ray-mmd的另一个全局设定，基本不需要改动 |
    | ray.x              | 用来加载ray.fx |
    | ray.fx             | ray-mmd的本体文件 |
    | ray_controller.pmx | ray-mmd的控制器|

* ## Extension文件夹

    * 　该文件夹下的MME为独立的MME，它们有的可以在无Ray的时候使用，有的只能在使用了Ray的时候使用。具体请参照14.[扩展](extension.md)

    |文件夹名    | 说明                                             | ray-mmd专用？ |
    | :------------ | :----------------------------------------------- | :------------ |
    | ColorGrading  | 用于颜色调整                                         | No            |
    | Debug         | 用于调试                                       | Yes           |
    | DummyScreen   | 用于MMD屏幕捕获                | Yes           |
    | FXAA          | FXAA抗锯齿                                 | No            |
    | LightBloom    | 模拟明亮部分溢出环境的效果  | No            |
    | OpticalFlares | 模拟镜头光晕的效果                 | No            |
    | SMAA          | SMAA抗锯齿                                 | No            |
    | Spectrum      | 音频频谱   | No            |
    | StereoImage   | 立体效果                                 | No            |

* ## Fog文件夹
    * 添加雾的效果，具体请参考10.[雾](fog.md)

    | 文件名名           | 说明                                  |
    | :------------------- | :------------------------------------ |
    | AtmosphericFog.pmx   | 大气雾                           |
    | GroundFog.pmx        | 地面雾                    |
    | VolumetricCube.pmx   | 体积雾　立方体型          |
    | VolumetricSphere.pmx | 体积雾　球球状                |


* ## Lighting文件夹
    * 额外光源。具体请参考9.[光源](light.md)

    | ファイル名           | 说明                                  |
    | :------------------- | :------------------------------------ |
    | DirectionalLight.pmx | 定向光                        |
    | LED.pmx              | 平面灯光显示图像和电影     |
    | PointLight.pmx       | 点光源|
    | PointLightIES.pmx    | 基于IES的点光源 |
    | RectangleLight.pmx   | 矩形平面光                      |
    | SphereLight.pmx      | 球形光                          |
    | SpotLight.pmx        | 聚光灯                       |
    | SpotLightIES.pmx     | 基于IES的聚光灯 |
    | TubeLight.pmx        | 管状灯                    |

* ## Main文件夹

    * 　在MME的“Main”选项卡中进行设置。有关Main选项卡的设置请参考5.[全局设置和MME效果分配](conf.md)。有关.fx中的设置参数，请参考11.[Main设置](main.md)

    | 文件名             | 说明 |
    | :--------------------- | :--- |
    | main.fx                | 默认配置文件|
    | main.fxsub             | 代码文件，无需编辑 |
    | main_ex_alpha.fx       | 11.[Main设置](main.md) |
    | main_ex_mask.fx        | 没什么用 |
    | main_ex_noalpha.fx     | 请看11.[Main设置](main.md) |
    | main_ex_with_sphmap.fx | 含有sph贴图的材质 |

* ## Materials文件夹
    * 具体情况请参考8.[材质设定](materials.md)

    | ファイル名                | 说明             |
    | :------------------------ | :--------------- |
    | material_2.0.fx           | 默认材质配置文件 |
    | material_common_2.0.fxsub | 代码文件，无需更改 |
    | material_skybox.fx        | Skybox配置文件 |
    | `README.md`                 | 材质说明 英语 |
    | README_chs.md             | 材质说明 中文 |

    | 文件夹名   | 说明                                         |
    | :----------- | :------------------------------------------- |
    | _MaterialMap | 自带贴图                |
    | ClearCoat    | 涂层预设         |
    | Cloth        | 衣料预设                     |
    | Editor       | 可表情控制属性的材质预设|
    | Emissive     | 自发光材质预设   |
    | Hair         | 头发材质预设                   |
    | Metallic     | 金属材质预设|
    | Programmable | 水、海材质预设|
    | Skin         | 皮肤材质预设|
    | Subsurface   | 表面材质预设|
    | Transparent  | 透明材质预设                   |
    | Video        | 视频屏幕材质预设 |

* ## Outline文件夹
    * 轮廓线设置。具体请参考13.[轮廓线](outline.md)

    | 文件名     | 说明             |
    | :------------- | :--------------- |
    | Fixed Color    | 正常轮廓线预设 |
    | Fixed Color x1 | x1粗的轮廓线预设 |
    | Fixed Color x2 | x2粗的轮廓线预设 |
    | Fixed Color x3 | x3粗的轮廓线预设 |


* ## Shader文件夹
    * 渲染所需代码，无需编辑。

* ## Shadow文件夹
    * 用于阴影的设置。详细情况请参考12.[阴影](shadow.md)

    | 文件名                  | 说明            |
    | :-------------------------- | :--------------- |
    | PSSM1～4.fx                 | PSSM设置      |
    | SSAO visibility 0.0～1.0.fx | SSAO密度设置 |

* ## Skybox文件夹
    * MMD天空球预设，用作环境光源提供。详细请参考7.[天空球控制](skybox.md)

    | 文件夹名         | 说明            |
    | :----------------- | :--------------- |
    | Helipad GoldenHour | 提供的预设HDR的天空球 |
    | Sky Hemisphere     | 纯色天空球，也可以做渐变天空，其中颜色可以通过高度改变 |
    | Sky Night          | 静态夜晚天空球 |
    | Time of day        | 动态白天天空球 |
    | Time of night      | 动态夜晚天空球 |

* ## Tools文件夹
    * 与Ray-mmd相关的工具。详细情况请参考15.[HDR贴图处理工具&IES处理工具](tool.md)

    | 文件名          | 説明             |
    | :------------------ | :--------------- |
    | cmft_rgbt_x1024.zip | 将HDR贴图转换为Skybox的工具|
    | IES2HDR.zip         | 将IES转换为HDR的工具，可用于点光源和聚光灯 |

[下一页 4.入门使用](started.md)