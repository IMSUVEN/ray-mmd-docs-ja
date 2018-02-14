# 15.Tools

Toolsフォルダには、ray-mmd用のツールが２つ有ります。一つはイメージベースのスカイボックスを作るツール（cmft_rgbt_x1024）、もう一つは、ポイントライトやスポットライトで使用できる、IES(配光データ)ファイルをHDRに変換するツール（IES2HDR）です。  
　それぞれ、zip形式で圧縮されているので展開してから使いましょう。

cmft_rgbt_x1024
-----
　Radiance形式（拡張子.hdr）のハイダイナミックレンジイメージ（HDRI）から、イメージベースのスカイボックス用に必要な画像データを作成するツールです。  
　Radiance形式（拡張子.hdr）の画像(HDRI)は、ray-mmdのreadme.mdの[Resources](https://github.com/ray-cast/ray-mmd#resources-)に幾つかリンクが有りますし、他にもフリーで使えるHDRIは有ります。

* 参考：[ハイダイナミックレンジイメージ](https://ja.wikipedia.org/wiki/%E3%83%8F%E3%82%A4%E3%83%80%E3%82%A4%E3%83%8A%E3%83%9F%E3%83%83%E3%82%AF%E3%83%AC%E3%83%B3%E3%82%B8%E3%82%A4%E3%83%A1%E3%83%BC%E3%82%B8)

* ### ファイル一覧  

    | ファイル名               | 説明 |
    | :----------------------- | :- |
    | Template フォルダ        | テンプレート。作成した画像データを入れ、別名コピーして使用します。
    | cmft_x64_fast_rgbt.exe   | 精度低：64ビットOS用変換ツール
    | cmft_x64_high_rgbt.exe   | 精度高：64ビットOS用変換ツール
    | cmft_x64_medium_rgbt.exe | 精度中：64ビットOS用変換ツール
    | cmft_x86_fast_rgbt.exe   | 精度低：32ビットOS用変換ツール
    | cmft_x86_high_rgbt.exe   | 精度高：32ビットOS用変換ツール
    | cmft_x86_medium_rgbt.exe | 精度中：32ビットOS用変換ツール
    | LICENSE.txt              | ライセンスの書かれたテキストファイル
    | README.png               | 使い方の書かれた画像

* ### 使い方  
    1. Radiance形式（拡張子.hdr）の画像(HDRI)を用意します。  

    2. 用意したHDRIをツールのフォルダ（cmft_rgbt_x1024）にコピーし、 `skybox.hdr` にリネームします。

    3. `skybox.hdr` を任意のexeにドラッグ・アンド・ドロップします。  
        変換が始まり、`skybox.dds`、`skydiff_hdr.dds`、`skyspec_hdr.dds`の３つのファイルが作成されます。  
        （変換元のファイルと同じ所に変換後のファイルは作成されます。変換には結構時間がかかると思います。）
    
    4. 作成された３つのファイル（`skybox.dds`、`skydiff_hdr.dds`、`skyspec_hdr.dds`）を `Template\texture` フォルダに移動します。  
        作成に使用した `skybox.hdr` は不要なので削除してかまいません。

    5. `Template` フォルダをray-mmdの `Skybox` フォルダにコピーし、フォルダ名をわかりやすいようにリネームします。  
        （変換元のファイル名が良いかもしれません）

IES2HDR
-----
IES(配光データ)ファイル（拡張子.IES）ファイルをHDRI（拡張子.hdr）に変換するツールです。変換したファイルはポイントライトやスポットライトで使用することができます。  
（IES は [Illuminating Engineering Society](https://www.ies.org/) の略です）


* ### ファイル一覧  

    | ファイル名           | 説明 |
    | :------------------- | :- |
    | Source code フォルダ | ソースコードのフォルダ
    | IES2HDR.exe          | 変換ツール
    | README.jpg           | 使い方の書かれた画像

* ### 使い方  
    1. IES(配光データ)ファイル（拡張子.IES）を用意します。

    2. IES(配光データ)ファイル（拡張子.IES）を `IES2HDR.exe` にドラッグ・アンド・ドロップします。  
        （変換元のファイルと同じ所に変換後のファイルは作成されます。変換には結構時間がかかると思います。）

    3. 作成したHDRファイルをスポットライトで使う場合は、`ray-mmd\Lighting\SpotLightIES` を別名でコピーします。  
        ポイントライトで使う場合は、`ray-mmd\Lighting\PointLightIES` を別名でコピーします。
    
    4. 作成したHDRファイルを `IES.HDR` にリネームして、コピーしたフォルダの `Default` にある `IES.HDR` と入れ替えます。


