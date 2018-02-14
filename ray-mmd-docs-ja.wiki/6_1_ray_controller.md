# 6.ray_controller

ray-mmd用のコントローラー(`ray_controller.pmx`)は大きく分けて、「ライトと影」、「ブルームと露出」、「DOF（被写界深度）」、「色調補正」があり、それぞれを調整することで絵作りが可能です。  

* Tips:  
　MMD全般の話ですが、コントローラーを調整する時は、「表示」メニューの「モデル編集時カメラ・照明追従」をオンにし、ボーン操作パネルの「選択」ボタンをオフ（ショートカット：Cキー）にしておくと調整がやりやすいと思います。  


表情操作パネル 左上
-----
* 主にライトと影の操作

    * ### SunLight+ / SunLight-  
        太陽光(MMDの照明操作パネルのライト)の強弱を調整します。

        | SunLight+ | SunLight ±0 | SunLight- |
        | :- | :- | :- |
        | [![6_1_SunLight_1](images/6_1_SunLight_1.png)](images/6_1_SunLight_1.png) | [![6_1_SunLight_0](images/6_1_SunLight_0.png)](images/6_1_SunLight_0.png) | [![6_1_SunLight_2](images/6_1_SunLight_2.png)](images/6_1_SunLight_2.png) |

    * ### SunShadowR+ / SunShadowG+ / SunShadowB+ / SunShadowV-
        SunLightによる影の色味を調整します。  
        R：赤、G：緑、B：青、V：明度  
        （VはRGBと違いマイナスであることに注意）

        | SunShadowR+ | SunShadowG+ | SunShadowB+ | SunShadowV- |
        | :- | :- | :- | :- |
        | [![6_1_SunShadow_1](images/6_1_SunShadow_1.png)](images/6_1_SunShadow_1.png) | [![6_1_SunShadow_2](images/6_1_SunShadow_2.png)](images/6_1_SunShadow_2.png) | [![6_1_SunShadow_3](images/6_1_SunShadow_3.png)](images/6_1_SunShadow_3.png) | [![6_1_SunShadow_4](images/6_1_SunShadow_4.png)](images/6_1_SunShadow_4.png) |

    * ### MultiLight+ / MultiLight-
        Lightingフォルダから追加したライトの明るさを一括して強弱を調整します。  
        ライトを追加していないと機能しません。

        | MultiLight+ | MultiLight ±0 | MultiLight+ |
        | :- | :- | :- |
        | [![6_1_MultiLight_1](images/6_1_MultiLight_1.png)](images/6_1_MultiLight_1.png) | [![6_1_MultiLight_0](images/6_1_MultiLight_0.png)](images/6_1_MultiLight_0.png) | [![6_1_MultiLight_2](images/6_1_MultiLight_2.png)](images/6_1_MultiLight_2.png) |

        ※ SunLight：緑、RectangleLight：青、SpotLight：赤

    * ### SSAO+ / SSAO-
        SSAOの濃さを調整します。

        | SSAO+ | SSAO ±0 | SSAO+ |
        | :- | :- | :- |
        | [![6_1_SSAO_1](images/6_1_SSAO_1.png)](images/6_1_SSAO_1.png) | [![6_1_SSAO_0](images/6_1_SSAO_0.png)](images/6_1_SSAO_0.png) | [![6_1_SSAO_2](images/6_1_SSAO_2.png)](images/6_1_SSAO_2.png) |

    * ### SSAORadius+ / SSAORadius-
        SSAOの半径の増減を調整します。

        | SSAORadius+ | SSAORadius ±0 | SSAORadius+ |
        | :- | :- | :- |
        | [![6_1_SSAORadius_1](images/6_1_SSAORadius_1.png)](images/6_1_SSAORadius_1.png) | [![6_1_SSAO_0](images/6_1_SSAO_0.png)](images/6_1_SSAO_0.png) | [![6_1_SSAORadius_2](images/6_1_SSAORadius_2.png)](images/6_1_SSAORadius_2.png) |

    * ### SSDO+ / SSDO-
        SSDOの濃さを調整します。

        | SSDO+ | SSDO ±0 | SSDO+ |
        | :- | :- | :- |
        | [![6_1_SSDO_1](images/6_1_SSDO_1.png)](images/6_1_SSDO_1.png) | [![6_1_SSAO_0](images/6_1_SSAO_0.png)](images/6_1_SSAO_0.png) | [![6_1_SSDO_2](images/6_1_SSDO_2.png)](images/6_1_SSDO_2.png) |

    * ### SSSS+ / SSSS-
        サブサーフェス効果の強弱を調整します。

        | SSSS+ | SSSS ±0 | SSSS+ |
        | :- | :- | :- |
        | [![6_1_SSSS_1](images/6_1_SSSS_1.png)](images/6_1_SSSS_1.png) | [![6_1_SSSS_0](images/6_1_SSSS_0.png)](images/6_1_SSSS_0.png) | [![6_1_SSSS_2](images/6_1_SSSS_2.png)](images/6_1_SSSS_2.png) |

        ※ material_jade_white.fxを使用

表情操作パネル 左下
-----
* ブルームと露出の設定  
    ブルーム(Bloom)はライトブルーム(light bloom)またはグロウ(glow)とも呼ばれ、強い光が隣接するくらい部分へ滲み出す効果です。

    * ### BloomThreshold
        ブルームが発生するしきい値。

        | BloomThreshold 0.0 | BloomThreshold 0.2 | BloomThreshold 0.4 | BloomThreshold 0.6 | BloomThreshold 0.8 | BloomThreshold 1.0 |
        | :- | :- | :- | :- | :- | :- |
        | [![6_2_BloomThreshold_00](images/6_2_BloomThreshold_00.png)](images/6_2_BloomThreshold_00.png) | [![6_2_BloomThreshold_02](images/6_2_BloomThreshold_02.png)](images/6_2_BloomThreshold_02.png) | [![6_2_BloomThreshold_04](images/6_2_BloomThreshold_04.png)](images/6_2_BloomThreshold_04.png) | [![6_2_BloomThreshold_06](images/6_2_BloomThreshold_06.png)](images/6_2_BloomThreshold_06.png) | [![6_2_BloomThreshold_08](images/6_2_BloomThreshold_08.png)](images/6_2_BloomThreshold_08.png) | [![6_2_BloomThreshold_10](images/6_2_BloomThreshold_10.png)](images/6_2_BloomThreshold_10.png) |

    * ### BloomRadius+ / BloomRadius-
        ブルームの半径の増減。

        | BloomRadius+ | BloomRadius ±0 | BloomRadius- |
        | :- | :- | :- |
        | [![6_2_BloomRadius_1](images/6_2_BloomRadius_1.png)](images/6_2_BloomRadius_1.png) | [![6_2_BloomRadius_0](images/6_2_BloomRadius_0.png)](images/6_2_BloomRadius_0.png) | [![6_2_BloomRadius_2](images/6_2_BloomRadius_2.png)](images/6_2_BloomRadius_2.png) |

    * ### BloomColorAllH+ / BloomColorAllS+ / BloomColorAllV+ / BloomColorAllV-
        ブルームのH(色相)S(彩度)V(明度)の調整。  
        BloomColorAllS+を上げないと効果がわかりにくいかもしれません。

        | BloomColorAll 0.0 | BloomColorAllS+ 1.0 | BloomColorAllS+ 1.0<br>BloomColorAllH+ 0.8 | BloomColorAllS+ 1.0<br>BloomColorAllH+ 0.8<br>BloomColorAllV+ 1.0 | BloomColorAllS+ 1.0<br>BloomColorAllH+ 0.8<br>BloomColorAllV- 1.0 |
        | :- | :- | :- | :- | :- |
        | [![6_2_BloomColorAll_0](images/6_2_BloomColorAll_0.png)](images/6_2_BloomColorAll_0.png) | [![6_2_BloomColorAll_1_S10](images/6_2_BloomColorAll_1_S10.png)](images/6_2_BloomColorAll_1_S10.png) | [![6_2_BloomColorAll_2_S10_H08](images/6_2_BloomColorAll_2_S10_H08.png)](images/6_2_BloomColorAll_2_S10_H08.png) | [![6_2_BloomColorAll_2_S10_H08_Vp10](images/6_2_BloomColorAll_2_S10_H08_Vp10.png)](images/6_2_BloomColorAll_2_S10_H08_Vp10.png) | [![6_2_BloomColorAll_2_S10_H08_Vm10](images/6_2_BloomColorAll_2_S10_H08_Vm10.png)](images/6_2_BloomColorAll_2_S10_H08_Vm10.png) |

    * ### BloomStarFade
        ブルームによって発生するゴーストを抑えます。  
        (`ray.conf`の`HDR_FLARE_MODE`、`HDR_STAR_MODE`を有効にした場合)

        | BloomStarFade 0.0 |BloomStarFade 0.1 |BloomStarFade 0.2 |BloomStarFade 0.3 |BloomStarFade 0.4 |
        | :- | :- | :- | :- | :- |
        | [![6_2_BloomStarFade_00](images/6_2_BloomStarFade_00.png)](images/6_2_BloomStarFade_00.png) | [![6_2_BloomStarFade_01](images/6_2_BloomStarFade_01.png)](images/6_2_BloomStarFade_01.png) | [![6_2_BloomStarFade_02](images/6_2_BloomStarFade_02.png)](images/6_2_BloomStarFade_02.png) | [![6_2_BloomStarFade_03](images/6_2_BloomStarFade_03.png)](images/6_2_BloomStarFade_03.png) | [![6_2_BloomStarFade_04](images/6_2_BloomStarFade_04.png)](images/6_2_BloomStarFade_04.png) |

    * ### Exposure+ / Exposure-
        露出の上げ下げ。

        | Exposure+ | Exposure ±0 |Exposure- |
        | :- | :- | :- |
        | [![6_2_Exposure_1](images/6_2_Exposure_1.png)](images/6_2_Exposure_1.png) | [![6_2_Exposure_0](images/6_2_Exposure_0.png)](images/6_2_Exposure_0.png) | [![6_2_Exposure_2](images/6_2_Exposure_2.png)](images/6_2_Exposure_2.png) |


表情操作パネル 右上
-----
* DOF (Depth of Field:被写界深度)調整  
    この機能を使うには、`ray.conf`の`BOKEH_QUALITY`に`1`を設定する必要があります。  

    * ### TestMode  
        焦点位置やボケ味を色で確認できます。  
        　黒：焦点が合っている所  
        　青：焦点より奥  
        　黄：焦点より手前

        | TestMode 0 | TestMode 1 |
        | :- | :- |
        | [![6_3_Testmode_0](images/6_3_Testmode_0.png)](images/6_3_Testmode_0.png) | [![6_3_Testmode_1](images/6_3_Testmode_1.png)](images/6_3_Testmode_1.png) |

    * ### MeasureMode  
        焦点位置の調整  
        TestModeを有効にした時に、中央のサークル位置で確認できます。  
        また、MeasureModeで調整後、`ray.x`の位置でさらに調整することが可能です。

        | MeasureMode 0 | MeasureMode調整 | MeasureMode調整 + ray.x位置調整 |
        | :- | :- | :- |
        | [![6_3_MeasureMode_0](images/6_3_MeasureMode_0.png)](images/6_3_MeasureMode_0.png) | [![6_3_MeasureMode_1](images/6_3_MeasureMode_1.png)](images/6_3_MeasureMode_1.png) | [![6_3_MeasureMode_2](images/6_3_MeasureMode_2.png)](images/6_3_MeasureMode_2.png) |

    * ### Fstop+ / Fstop-
        絞りの増減  
        ＋にすると被写界深度は深く(ピントの合っている前後の幅は広く)なりボケは小さくなります。  
        ーにすると被写界深度は浅くなりボケは大きくなります。

        |  | Fstop+ 1 | Fstop ±0 | Fsstop- 1 |
        | :- | :- | :- | :- |
        | TestMode 0 | [![6_3_Fstop_1_0](images/6_3_Fstop_1_0.png)](images/6_3_Fstop_1_0.png) | [![6_3_Testmode_0](images/6_3_Testmode_0.png)](images/6_3_Testmode_0.png) | [![6_3_Fstop_2_0](images/6_3_Fstop_2_0.png)](images/6_3_Fstop_2_0.png) |
        | TestMode 1 | [![6_3_Fstop_1_1](images/6_3_Fstop_1_1.png)](images/6_3_Fstop_1_1.png) | [![6_3_Testmode_1](images/6_3_Testmode_1.png)](images/6_3_Testmode_1.png) | [![6_3_Fstop_2_1](images/6_3_Fstop_2_1.png)](images/6_3_Fstop_2_1.png) |

    * ### FocalLength+ / FocalLength-
        焦点距離の増減  
        ＋にするとボケが大きくなり、ーにすると小さくなります。

        |  | FocalLength+ 1 | FocalLength ±0 | FocalLength- 1 |
        | :- | :- | :- | :- |
        | TestMode 0 | [![6_3_FocalLength_1_0](images/6_3_FocalLength_1_0.png)](images/6_3_FocalLength_1_0.png) | [![6_3_Testmode_0](images/6_3_Testmode_0.png)](images/6_3_Testmode_0.png) | [![6_3_FocalLength_2_0](images/6_3_FocalLength_2_0.png)](images/6_3_FocalLength_2_0.png) |
        | TestMode 1 | [![6_3_FocalLength_1_1](images/6_3_FocalLength_1_1.png)](images/6_3_FocalLength_1_1.png) | [![6_3_Testmode_1](images/6_3_Testmode_1.png)](images/6_3_Testmode_1.png) | [![6_3_FocalLength_2_1](images/6_3_FocalLength_2_1.png)](images/6_3_FocalLength_2_1.png) |

    * ### FocalRegion+ / FocalRegion-
        ピントが合う領域（被写界深度）の増減  
        ＋にするとピントが合う範囲が広くなり、ーにすると狭くなります。

        |  | FocalRegion+ 1 | FocalRegion ±0 | FocalRegion- 1 |
        | :- | :- | :- | :- |
        | TestMode 0 | [![6_3_FocalRegion_1_0](images/6_3_FocalRegion_1_0.png)](images/6_3_FocalRegion_1_0.png) | [![6_3_Testmode_0](images/6_3_Testmode_0.png)](images/6_3_Testmode_0.png) | [![6_3_FocalRegion_2_0](images/6_3_FocalRegion_2_0.png)](images/6_3_FocalRegion_2_0.png) |
        | TestMode 1 | [![6_3_FocalRegion_1_1](images/6_3_FocalRegion_1_1.png)](images/6_3_FocalRegion_1_1.png) | [![6_3_Testmode_1](images/6_3_Testmode_1.png)](images/6_3_Testmode_1.png) | [![6_3_FocalRegion_2_1](images/6_3_FocalRegion_2_1.png)](images/6_3_FocalRegion_2_1.png) |

    * ### FocalDistance+ / FocalDistance-
        カメラから焦点位置までの距離の増減  
        ＋にすると焦点位置は奥へ、ーにすると手前になります。  
        また、FocalDistanceで調整後、ray.xの位置でさらに調整することが可能です。

        |  | FocalDistance+ 1 | FocalDistance ±0 | FocalDistance- 1 |
        | :- | :- | :- | :- |
        | TestMode 0 | [![6_3_FocalDistance_1_0](images/6_3_FocalDistance_1_0.png)](images/6_3_FocalDistance_1_0.png) | [![6_3_Testmode_0](images/6_3_Testmode_0.png)](images/6_3_Testmode_0.png) | [![6_3_FocalDistance_2_0](images/6_3_FocalDistance_2_0.png)](images/6_3_FocalDistance_2_0.png) |
        | TestMode 1 | [![6_3_FocalDistance_1_1](images/6_3_FocalDistance_1_1.png)](images/6_3_FocalDistance_1_1.png) | [![6_3_Testmode_1](images/6_3_Testmode_1.png)](images/6_3_Testmode_1.png) | [![6_3_FocalDistance_2_1](images/6_3_FocalDistance_2_1.png)](images/6_3_FocalDistance_2_1.png) |



表情操作パネル 右下
-----
* 色調補正  
    * ### Contrast+ / Contrast-
        コントラストの上げ下げ

        | Contrast+ | Contrast ±0 | Contrast- |
        | :- | :- | :- |
        | [![6_4_Contrast_1](images/6_4_Contrast_1.png)](images/6_4_Contrast_1.png) |[![6_4_original](images/6_4_original.png)](images/6_4_original.png) | [![6_4_Contrast_2](images/6_4_Contrast_2.png)](images/6_4_Contrast_2.png) |

    * ### Saturation+ / Saturation-
        彩度の上げ下げ

        | Saturation+ | Saturation ±0 | Saturation- |
        | :- | :- | :- |
        | [![6_4_Saturation_1](images/6_4_Saturation_1.png)](images/6_4_Saturation.png) |[![6_4_original](images/6_4_original.png)](images/6_4_original.png) | [![6_4_Saturation_2](images/6_4_Saturation_2.png)](images/6_4_Saturation_2.png) |

    * ### Gamma+ / Gamma-
        ガンマ補正の上げ下げ

        | Gamma+ | Gamma ±0 | Gamma- |
        | :- | :- | :- |
        | [![6_4_Gamma_1](images/6_4_Gamma_1.png)](images/6_4_Gamma.png) |[![6_4_original](images/6_4_original.png)](images/6_4_original.png) | [![6_4_Gamma_2](images/6_4_Gamma_2.png)](images/6_4_Gamma_2.png) |

    * ### Temperature+ / Temperature-
        色温度の上げ下げ  
        上げると赤みがかり、下げると青みがかる。

        | Temperature+ | Temperature ±0 | Temperature- |
        | :- | :- | :- |
        | [![6_4_Temperature_1](images/6_4_Temperature_1.png)](images/6_4_Temperature.png) |[![6_4_original](images/6_4_original.png)](images/6_4_original.png) | [![6_4_Temperature_2](images/6_4_Temperature_2.png)](images/6_4_Temperature_2.png) |

    * ### BalanceR- / BalanceG- / BalanceB-
        R,G,B減算

    * ### BalanceR+ / BalanceG+ / BalanceB+
        R,G,B加算

        | Balance+ | Balance ±0 | Balance- |
        | :- | :- | :- |
        | [![6_4_RGBp_10](images/6_4_RGBp_10.png)](images/6_4_RGBp_10.png) |[![6_4_original](images/6_4_original.png)](images/6_4_original.png) | [![6_4_RGBm_09](images/6_4_RGBm_09.png)](images/6_4_RGBm_09.png) |

-----

<small> Model : Hatsune Miku V4X Model by Digitrevx / トレーニングステージ by 名無し / ロビーステージ by NOB / 初音ミクzeze式 ver1.420140906 , おまけステージモデル by zeze </small>