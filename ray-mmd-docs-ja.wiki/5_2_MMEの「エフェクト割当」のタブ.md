## 5-2.MMEの「エフェクト割当」のタブ

ray-mmdを導入すると、MMEの「エフェクト割当」にray-mmdで使用するタブが追加されます。`ray.conf`の設定によりタブが増減します。  
　タブに割り当てるfxファイルの詳細については、各章の説明を参照してください。


| タブ名      | タブ説明表記                     |    |
| :---------- | :------------------------------- | :- |
| Main        | Main Render Target               | 描画するモデルには「Main」フォルダのfxファイルを割り当てる<br>マテリアルのfxではないので注意
| FogMap      | Multi volumetric fog for ray     | 「Fog」フォルダのfxファイル、またはSkyboxのフォグ用のfxファイルを割り当てる<br>ray.confのFOG_ENABLEで非表示にできる
| LightMap    | Multi light source for ray       | 「Lighting」フォルダのfxファイルを割り当てる<br>ray.confのMULTI_LIGHT_ENABLEで非表示にできる
| EnvLightMap | Image-based-lighting map for ray | 「Skybox」フォルダのライティング用のfxファイルを割り当てる<br>割当を忘れるとライトが当たらない所が真っ黒になる
| MaterialMap | Material cache map for ray       | 「Material」フォルダのマテリアル、または自作のマテリアルのfxファイルを割り当てる。
| OutlineMap  | Outline shading for ray          | 「Outline」フォルダのfxファイルを割り当てる<br>ray.confのOUTLINE_QUALITYで有効にできる
| SSAOMap     | SSAO visibility for ray          | 「Shadow」フォルダのSSAO visibility～のfxファイルを割り当てる<br>デフォルトでは`SSAO visibility 1.0.fx`が割り当てられる
| PSSM1～4    | cascade shadow map for ray       | 「Shadow」フォルダのPSSM～のfxファイルが割り当てられる<br>特にユーザーが設定することはない

また、ライトのfxで影付きの物を選択すると、シャドウマップ用のタブが追加されていきます。