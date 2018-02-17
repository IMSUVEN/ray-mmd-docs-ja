# ·Ray的全局设置和MME效果分配
[返回目录](../ReadMe.md) 
</br>
[上一章 3.各文件夹说明](started.md)
## 说明
本章介绍了Ray.conf和ray_advanced.conf以及MME不同选项卡的不同用处。
## 全局设置

* 　ray-mmd的根目录中有两个设置文件，分别是 `ray.conf`和 `ray_advanced.conf`。其中 `ray.conf`是需要你自己根据自己的需求进行重新设置的。而 `ray_advanced.conf`基本不需要修改，除非你有这方面的开发经验，准备设置自己的渲染。  

    | 文件名         | 说明 |
    | :----------------- | :--- |
    | ray.conf           | ray-mmd的全局设置，根据自我需求进行设置。 |
    | ray_advanced.conf  | ray-mmd的另一个全局设置，基本不需要更改。 |

* 在你打开MMD并载入mmd后更改`ray.conf`，效果不会实时更新。你可以根据以下方法进行更新，都需要一段时间等待  
    * 先将当前MMD工程保存并关闭，修改`ray.conf`后再打开MMD重新载入工程。
    * 在MMEfect菜单中执行「全部更新」（「全て更新」）。

## ray.conf的设置

Sun light
-----
* MMD的「照明操作」面板上的灯光设置。用作充当阳光  

    ### `SUN_LIGHT_ENABLE`
    太阳光的设置

    `0` ：关闭  
    `1` ：开启　(默认选项)  
    `2` ：开启：根据角度计算光的强度  

    |  | SUN_LIGHT_ENABLE 0 | SUN_LIGHT_ENABLE 1 | SUN_LIGHT_ENABLE 2 |
    | :- | :- | :- | :- |
    | 光的位置 高 | [![5_SUN_LIGHT_ENABLE_0_1](../Pic/5_SUN_LIGHT_ENABLE_0_1s.png)](../Pic/5_SUN_LIGHT_ENABLE_0_1.png) | [![5_SUN_LIGHT_ENABLE_1_1](../Pic/5_SUN_LIGHT_ENABLE_1_1s.png)](../Pic/5_SUN_LIGHT_ENABLE_1_1.png) | [![5_SUN_LIGHT_ENABLE_2_1](../Pic/5_SUN_LIGHT_ENABLE_2_1s.png)](../Pic/5_SUN_LIGHT_ENABLE_2_1.png) |
    | 光的位置 低 |  | [![5_SUN_LIGHT_ENABLE_1_2](../Pic/5_SUN_LIGHT_ENABLE_1_2s.png)](../Pic/5_SUN_LIGHT_ENABLE_1_2.png) | [![5_SUN_LIGHT_ENABLE_2_2](../Pic/5_SUN_LIGHT_ENABLE_2_2s.png)](../Pic/5_SUN_LIGHT_ENABLE_2_2.png) |

    ※スクリーンショットはクリックで拡大表示されます。

    ### `SUN_SHADOW_QUALITY`
    太陽光が作る影のクォリティ設定。数値が大きいほど影のクォリティは高くなりますが、使用するVRAMも増え処理速度に影響します。スペックの低いPCではクォリティと引き換えに、設定を下げる検討をすると良いかもしれません。  

    `0` ：影なし  
    `1` ：Low    ( 512 * 4)  
    `2` ：Medium (1024 * 4)  
    `3` ：High   (2048 * 4)　(デフォルト)  
    `4` ：boom!  (4096 * 4)  
    `5` ：boom!! (8192 * 4)  

    | SUN_SHADOW_QUALITY 1 | SUN_SHADOW_QUALITY 2 | SUN_SHADOW_QUALITY 3 | SUN_SHADOW_QUALITY 4 | SUN_SHADOW_QUALITY 5 |
    | :- | :- | :- | :- | :- |
    | [![5_SUN_SHADOW_QUALITY_1](../Pic/5_SUN_SHADOW_QUALITY_1s.png)](../Pic/5_SUN_SHADOW_QUALITY_1.png) | [![5_SUN_SHADOW_QUALITY_2](../Pic/5_SUN_SHADOW_QUALITY_2s.png)](../Pic/5_SUN_SHADOW_QUALITY_2.png) | [![5_SUN_SHADOW_QUALITY_3](../Pic/5_SUN_SHADOW_QUALITY_3s.png)](../Pic/5_SUN_SHADOW_QUALITY_3.png) | [![5_SUN_SHADOW_QUALITY_4](../Pic/5_SUN_SHADOW_QUALITY_4s.png)](../Pic/5_SUN_SHADOW_QUALITY_4.png) | 残念ながらMacBook AirではOut of video memoryが出て、スクリーンショットを撮ることが出来ませんでした。 |

Image Based Lighting
-----
* SkyboxのUVを反転するかどうかの設定。  
    元々は`0`のライティングを使用しない設定が有りましたが、IBLは必須になったのでその設定は使われなくなりました。

    ### `IBL_QUALITY`

    `1` ：反転しない　(デフォルト)  
    `2` ：UVを反転する

    | IBL_QUALITY 1 | IBL_QUALITY 2 |
    | :- |:- |
    | [![5_IBL_QUALITY_1](../Pic/5_IBL_QUALITY_1s.png)](../Pic/5_IBL_QUALITY_1.png) | [![5_IBL_QUALITY_2](../Pic/5_IBL_QUALITY_2s.png)](../Pic/5_IBL_QUALITY_2.png) |
    | 元々OpenGL座標系のHDRIなので、Marriottホテルのロゴが反転している | Marriottホテルのロゴが正しく読める |

    ※ ライトはスカイボックスに合わせて方向を変えています

Fog Tab
-----
* MMEの「エフェクト割当」で表示されるタブに「FogMap」タブを追加するかどうか。追加しないとフォグが使えない。

    ### `FOG_ENABLE`

    `0` ：追加しない  
    `1` ：追加する　(デフォルト)  

Light Tab
-----
* MMEの「エフェクト割当」で表示されるタブに「LightMap」タブを追加するかどうか。追加しないと追加のライトが使えない。

    ### `MULTI_LIGHT_ENABLE`

    `0` ：追加しない  
    `1` ：追加する　(デフォルト)  

Outline Tab
-----
* MMEの「エフェクト割当」で表示されるタブに「OutlineMap」タブを追加するかどうか。追加する場合は、アンチエイリアスの種類が選択できる。

    ### `OUTLINE_QUALITY`

    `0` ：追加しない　(デフォルト)  
    `1` ：追加する AA無し  
    `2` ：追加する + SMAA  
    `3` ：追加する + SSAA  

    | OUTLINE_QUALITY 0 | OUTLINE_QUALITY 1 | OUTLINE_QUALITY 2 | OUTLINE_QUALITY 3 |
    | :- | :- | :- | :- |
    | [![5_OUTLINE_QUALITY_0](../Pic/5_OUTLINE_QUALITY_0s.png)](../Pic/5_OUTLINE_QUALITY_0.png) | [![5_OUTLINE_QUALITY_1](../Pic/5_OUTLINE_QUALITY_1s.png)](../Pic/5_OUTLINE_QUALITY_1.png) | [![5_OUTLINE_QUALITY_2](../Pic/5_OUTLINE_QUALITY_2s.png)](../Pic/5_OUTLINE_QUALITY_2.png) | [![5_OUTLINE_QUALITY_3](../Pic/5_OUTLINE_QUALITY_3s.png)](../Pic/5_OUTLINE_QUALITY_3.png) |

Toon-shading material
-----
* トゥーンシェーディングを有効にするかどうか。  
    マテリアルでトゥーンシェーディング（CUSTOM_ENABLE 8または9）を使う場合は有効にする必要があります。

    ### `TOON_ENABLE`

    `0` ：無効　(デフォルト)  
    `1` ：有効  
    `2` ：有効 + diffusion  

    | TOON_ENABLE 0 | TOON_ENABLE 1 | TOON_ENABLE 2 |
    | :- | :- | :- |
    | [![5_TOON_ENABLE_0](../Pic/5_TOON_ENABLE_0s.png)](../Pic/5_TOON_ENABLE_0.png) | [![5_TOON_ENABLE_1](../Pic/5_TOON_ENABLE_1s.png)](../Pic/5_TOON_ENABLE_1.png) | [![5_TOON_ENABLE_2](../Pic/5_TOON_ENABLE_2s.png)](../Pic/5_TOON_ENABLE_2.png) |

    ※ BOKEH_QUALITY 1、OUTLINE_QUALITY 3、マテリアルはCUSTOM_ENABLE 8でCELシェーディングを割り当てています。また、マテリアルは全てのモデルに同一マテリアルを割り当てていて、材質ごとの調整、最適化はしていません。

Screen Space Directional Occlusion
-----
* Screen Space Directional Occlusion(SSDO:ライトの方向を考慮したAO)のクォリティを設定します。  
    サンプル数が多くなればクオリティは上がりますが、重くなります。

    ### `SSDO_QUALITY`

    `0` ：SSDO無し  
    `1` ： 8 samples  
    `2` ：12 samples　(デフォルト)  
    `3` ：16 samples  
    `4` ：20 samples  
    `5` ：24 samples  
    `6` ：28 samples  

    | SSDO_QUALITY 0 | SSDO_QUALITY 1 | SSDO_QUALITY 2 | SSDO_QUALITY 3 | SSDO_QUALITY 4 | SSDO_QUALITY 5 | SSDO_QUALITY 6 |
    | :- | :- | :- | :- | :- | :- | :- |
    | [![5_SSDO_QUALITY_0](../Pic/5_SSDO_QUALITY_0s.png)](../Pic/5_SSDO_QUALITY_0.png) | [![5_SSDO_QUALITY_1](../Pic/5_SSDO_QUALITY_1s.png)](../Pic/5_SSDO_QUALITY_1.png) | [![5_SSDO_QUALITY_2](../Pic/5_SSDO_QUALITY_2s.png)](../Pic/5_SSDO_QUALITY_2.png) | [![5_SSDO_QUALITY_3](../Pic/5_SSDO_QUALITY_3s.png)](../Pic/5_SSDO_QUALITY_3.png) | [![5_SSDO_QUALITY_4](../Pic/5_SSDO_QUALITY_4s.png)](../Pic/5_SSDO_QUALITY_4.png) | [![5_SSDO_QUALITY_5](../Pic/5_SSDO_QUALITY_5s.png)](../Pic/5_SSDO_QUALITY_5.png) | [![5_SSDO_QUALITY_6](../Pic/5_SSDO_QUALITY_6s.png)](../Pic/5_SSDO_QUALITY_6.png) |


    ※ 効果がわかりやすいように、SUN_SHADOW_QUALITY 0、コントローラーのSSAO- 1、SSDO+ 3に設定しています。

Screen Space Reflection
-----
* Screen Space Reflection(SSR)のクォリティを設定します。  
    サンプル数が多くなればクオリティは上がりますが、重くなります。
    ### `SSR_QUALITY`

    `0` ：SSR無し　(デフォルト)  
    `1` ： 32 samples  
    `2` ： 64 samples  
    `3` ：128 samples  

    | SSR_QUALITY 0 | SSR_QUALITY 1 | SSR_QUALITY 2 | SSR_QUALITY 3 |
    | :- | :- | :- | :- |
    | [![5_SSR_QUALITY_0](../Pic/5_SSR_QUALITY_0s.png)](../Pic/5_SSR_QUALITY_0.png) | [![5_SSR_QUALITY_1](../Pic/5_SSR_QUALITY_1s.png)](../Pic/5_SSR_QUALITY_1.png) | [![5_SSR_QUALITY_2](../Pic/5_SSR_QUALITY_2s.png)](../Pic/5_SSR_QUALITY_2.png) | [![5_SSR_QUALITY_3](../Pic/5_SSR_QUALITY_3s.png)](../Pic/5_SSR_QUALITY_3.png) |

Screen Space Subsurface Scattering
-----
* Screen Space Subsurface Scattering(SSSSS)を使うかどうか。  
    サブサーフェススキャッタリングは肌のマテリアルなどに使われます。

    ### `SSSS_QUALITY`

    `0` ：無効  
    `1` ：有効　(デフォルト)  

Bokeh
-----
* DOF (Depth of Field:被写界深度)を有効にするかどうか。  
    調整は`ray_controller.pmx`で行います。

    ### `BOKEH_QUALITY`

    `0` ：無効　(デフォルト)  
    `1` ：有効  

    | BOKEH_QUALITY 0 | BOKEH_QUALITY 1 |
    | :- | :- |
    | [![5_BOKEH_QUALITY_0](../Pic/5_BOKEH_QUALITY_0s.png)](../Pic/5_BOKEH_QUALITY_0.png) | [![5_BOKEH_QUALITY_1](../Pic/5_BOKEH_QUALITY_1s.png)](../Pic/5_BOKEH_QUALITY_1.png) |
    |  | ボケ具合はray_controllerで調整しています |

Eye Adaptation
-----
* Eye Adaptation (Auto-Exposure・自動露光・明暗順応)を有効にするかどうか。  
    Eye Adaptationは、明るい場所から暗い場所、またはその逆において、人間の目やカメラが明るさに時間経過とともに順応する時の効果です。  

    ### `HDR_EYE_ADAPTATION`

    `0` ：無効　(デフォルト)  
    `1` ：有効　ISO 100 中間グレイを12.7%とする  
    `2` ：有効　ISO 100 中間グレイを18.0%とする（標準反射率
）  

Bloom
-----
* ブルームのモード

    ### `HDR_BLOOM_MODE`

    `0` ：無効  
    `1` ：inf                                 : 1.0.0より前のバージョンと同等  
    `2` ：saturate                            : 1.0.0と同等  
    `3` ：luminance & exposure                : 1.2.0と同等  
    `4` ：saturate & exposure　(デフォルト)   : 1.3.0以降  

    | HDR_BLOOM_MODE 0 | HDR_BLOOM_MODE 1 | HDR_BLOOM_MODE 2 | HDR_BLOOM_MODE 3 | HDR_BLOOM_MODE 4 |
    | :- | :- | :- | :- | :- |
    | [![5_HDR_BLOOM_MODE_0](../Pic/5_HDR_BLOOM_MODE_0s.png)](../Pic/5_HDR_BLOOM_MODE_0.png) | [![5_HDR_BLOOM_MODE_1](../Pic/5_HDR_BLOOM_MODE_1s.png)](../Pic/5_HDR_BLOOM_MODE_1.png) | [![5_HDR_BLOOM_MODE_2](../Pic/5_HDR_BLOOM_MODE_2s.png)](../Pic/5_HDR_BLOOM_MODE_2.png) | [![5_HDR_BLOOM_MODE_3](../Pic/5_HDR_BLOOM_MODE_3s.png)](../Pic/5_HDR_BLOOM_MODE_3.png) | [![5_HDR_BLOOM_MODE_4](../Pic/5_HDR_BLOOM_MODE_4s.png)](../Pic/5_HDR_BLOOM_MODE_4.png) |

Simple lensflare
-----
* レンズフレアのモード。１～３はレンズフレアONで、発生するフレアの色味が異なる。

    ### `HDR_FLARE_MODE`

    `0` ：無効　(デフォルト)  
    `1` ：Blue （フレアが青みがかる）  
    `2` ：Orange （フレアがオレンジがかる）  
    `3` ：Auto （光源と同じ色のフレア）  

    | HDR_FLARE_MODE 0 | HDR_FLARE_MODE 1 | HDR_FLARE_MODE 2 | HDR_FLARE_MODE 3 |
    | :- | :- | :- | :- |
    | [![5_HDR_FLARE_MODE_0](../Pic/5_HDR_FLARE_MODE_0s.png)](../Pic/5_HDR_FLARE_MODE_0.png) | [![5_HDR_FLARE_MODE_1](../Pic/5_HDR_FLARE_MODE_1s.png)](../Pic/5_HDR_FLARE_MODE_1.png) | [![5_HDR_FLARE_MODE_2](../Pic/5_HDR_FLARE_MODE_2s.png)](../Pic/5_HDR_FLARE_MODE_2.png) | [![5_HDR_FLARE_MODE_3](../Pic/5_HDR_FLARE_MODE_3s.png)](../Pic/5_HDR_FLARE_MODE_3.png) |


Simple glare star
-----
* レンズフレアで発生する光芒（光条）のタイプ

    ### `HDR_STAR_MODE`

    `0` ：無効　(デフォルト)  
    `1` ：Anamorphic Lens Flares // blue  
    `2` ：Anamorphic Lens Flares // auto  
    `3` ：Glare star // orange  
    `4` ：Glare star // auto  

    | HDR_STAR_MODE 0 | HDR_STAR_MODE 1 | HDR_STAR_MODE 2 | HDR_STAR_MODE 3 | HDR_STAR_MODE 4 |
    | :- | :- | :- | :- |:- |
    | [![5_HDR_STAR_MODE_0](../Pic/5_HDR_STAR_MODE_0s.png)](../Pic/5_HDR_STAR_MODE_0.png) | [![5_HDR_STAR_MODE_1](../Pic/5_HDR_STAR_MODE_1s.png)](../Pic/5_HDR_STAR_MODE_1.png) | [![5_HDR_STAR_MODE_2](../Pic/5_HDR_STAR_MODE_2s.png)](../Pic/5_HDR_STAR_MODE_2.png) | [![5_HDR_STAR_MODE_3](../Pic/5_HDR_STAR_MODE_3s.png)](../Pic/5_HDR_STAR_MODE_3.png) | [![5_HDR_STAR_MODE_4](../Pic/5_HDR_STAR_MODE_4s.png)](../Pic/5_HDR_STAR_MODE_4.png) |


Tonemapping
-----
* トーンマッピングのモード。  
    ray-mmd内部でHDR処理された画像データはトーンマッピングを経てLDRに変換されモニタで確認することが出来ます。そのトーンマッピングのタイプを選択します。

    ### `HDR_TONEMAP_OPERATOR`

    `0` ：Linear  
    `1` ：Reinhard  
    `2` ：Hable  
    `3` ：Uncharted2  
    `4` ：Hejl2015　(デフォルト)  
    `5` ：ACES-sRGB  
    `6` ：NaughtyDog  

    | HDR_TONEMAP_OPERATOR 0 |HDR_TONEMAP_OPERATOR 1 |HDR_TONEMAP_OPERATOR 2 |HDR_TONEMAP_OPERATOR 3 |HDR_TONEMAP_OPERATOR 4 |HDR_TONEMAP_OPERATOR 5 |HDR_TONEMAP_OPERATOR 6 |
    | :- | :- | :- | :- | :- | :- | :- |
    | [![5_HDR_TONEMAP_OPERATOR_0](../Pic/5_HDR_TONEMAP_OPERATOR_0s.png)](../Pic/5_HDR_TONEMAP_OPERATOR_0.png) | [![5_HDR_TONEMAP_OPERATOR_1](../Pic/5_HDR_TONEMAP_OPERATOR_1s.png)](../Pic/5_HDR_TONEMAP_OPERATOR_1.png) | [![5_HDR_TONEMAP_OPERATOR_2](../Pic/5_HDR_TONEMAP_OPERATOR_2s.png)](../Pic/5_HDR_TONEMAP_OPERATOR_2.png) | [![5_HDR_TONEMAP_OPERATOR_3](../Pic/5_HDR_TONEMAP_OPERATOR_3s.png)](../Pic/5_HDR_TONEMAP_OPERATOR_3.png) | [![5_HDR_TONEMAP_OPERATOR_4](../Pic/5_HDR_TONEMAP_OPERATOR_4s.png)](../Pic/5_HDR_TONEMAP_OPERATOR_4.png) | [![5_HDR_TONEMAP_OPERATOR_5](../Pic/5_HDR_TONEMAP_OPERATOR_5s.png)](../Pic/5_HDR_TONEMAP_OPERATOR_5.png) | [![5_HDR_TONEMAP_OPERATOR_6](../Pic/5_HDR_TONEMAP_OPERATOR_6s.png)](../Pic/5_HDR_TONEMAP_OPERATOR_6.png) |

Anti-Aliasing
-----
* アンチエイリアスのタイプを選択します。  
    FXAAとSMAAの違いはざっくりと言えば、FXAA：軽いが精度はイマイチ、SMAA:FXAAに対して重くなるが精度は上がる、という感じです。  
    参考：[SMAA: Enhanced Subpixel Morphological Antialiasing](http://www.iryoku.com/smaa/)に有る動画で概ねどんな感じかはわかると思います。

    ### `AA_QUALITY`

    `0` ：無効  
    `1` ：FXAA　(デフォルト)  
    `2` ：SMAAx1-medium // maybe, AMD graphics card does not support  
    `3` ：SMAAx1-high  
    `4` ：SMAAx2-medium  
    `5` ：SMAAx2-high  

    | AA_QUALITY 0 | AA_QUALITY 1 | AA_QUALITY 2 | AA_QUALITY 3 | AA_QUALITY 4 | AA_QUALITY 5 |
    | :- | :- | :- | :- | :- | :- |
    | [![5_AA_QUALITY_0](../Pic/5_AA_QUALITY_0s.png)](../Pic/5_AA_QUALITY_0.png) | [![5_AA_QUALITY_1](../Pic/5_AA_QUALITY_1s.png)](../Pic/5_AA_QUALITY_1.png) | [![5_AA_QUALITY_2](../Pic/5_AA_QUALITY_2s.png)](../Pic/5_AA_QUALITY_2.png) | [![5_AA_QUALITY_3](../Pic/5_AA_QUALITY_3s.png)](../Pic/5_AA_QUALITY_3.png) | [![5_AA_QUALITY_4](../Pic/5_AA_QUALITY_4s.png)](../Pic/5_AA_QUALITY_4.png) | [![5_AA_QUALITY_5](../Pic/5_AA_QUALITY_5s.png)](../Pic/5_AA_QUALITY_5.png) |



# ray_advanced.confの設定
    static const float mLightIntensityMin = 1.0;
    static const float mLightIntensityMax = 10.0;
    static const float mLightDistance = 1000;
    static const float mLightPlaneNear = 0.1;
    static const float mLightPlaneFar = 400.0;
    static const float mTemperature = 6600.0; // range 1000 ~ 40000 // Default value used D66 for pure wihte
    static const float mEnvLightIntensityMin = 1.0;
    static const float mEnvLightIntensityMax = 6.2831852;
    static const float mBloomIntensityMin = 1.0;
    static const float mBloomIntensityMax = 20.0;
    static const float mBloomGhostThresholdMax = 10.0;
    static const float mExposureMin = 2.0;
    static const float mExposureMax = 8.0;
    static const float mExposureEyeAdapationMin = 0.0;
    static const float mExposureEyeAdapationMax = 8.0;
    static const float mVignetteInner = 1.0;
    static const float mVignetteOuter = 3.5;
    static const float mPointLightNear = 1.0;
    static const float mPointLightFar  = 400.0;
    static const float mPSSMCascadeZMin = 5;
    static const float mPSSMCascadeZMax = 1500;
    static const float mPSSMCascadeLambda = 0.5;
    static const float mPSSMDepthZMin = 0;
    static const float mPSSMDepthZMax = 4000.0;
    static const float mSSRRangeMax = 1000.0;
    static const float mSSRRangeScale = 0.75;
    static const float mSSRThreshold = 1.0;
    static const float mSSRFadeStart = 0.8;
    static const float mSSSSIntensityMin = 0.04;
    static const float mSSSSIntensityMax = 0.02;
    static const float mSSDOParams[4] = {2.0, 2.0, 0.03, 0.15};
    static const float mSSDOBiasNear = 0.125;
    static const float mSSDOBiasFar = 0.0005;
    static const float mSSDOBiasFalloffNear = 20.0;
    static const float mSSDOIntensityMin = 2.4;
    static const float mSSDOIntensityMax = 10.0;
    static const float mSSDOBlurFalloff = 200.0;
    static const float mSSDOBlurSharpnessMin = 1.0;
    static const float mSSDOBlurSharpnessMax = 8.0;
    static const float mFXAAQualitySubpix = 0.5;
    static const float mFXAAQualityEdgeThreshold = 0.166;
    static const float mFXAAQualityEdgeThresholdMin = 0.0333;

-----

<small> Model : Hatsune Miku V4X Model by Digitrevx / Japanese Otaku City by ZENRIN / S_N_Fes ステージ by cubp / トレーニングステージ by 名無し </small>