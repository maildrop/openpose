# 0. 目次

 1. Visual Studio 2017 のインストール  
 2. CUDA のインストール (nVidia製のGPUを持っている場合)   
 3. OpenPose のダウンロード  
 4. OpenPose のビルド  

# 1. Visual Studio 2017 のインストール  

[https://docs.microsoft.com/ja-jp/visualstudio/releasenotes/vs2017-relnotes](https://docs.microsoft.com/ja-jp/visualstudio/releasenotes/vs2017-relnotes)
 より  
`Visual Studio Community 2017` をダウンロードします。  

ダウンロードした `Visual Studio Installer` を起動し、  
`Visual Studio Community 2017` の `インストール` を押します。  
( 既にインストールしている場合は `Visual Studio Community 2017` の `変更` を押します )  

 - ワークロード > C++によるデスクトップ開発  
 - 個別のコンポーネント > コンパイラ、ビルドツール、およびランタイム > CMakeのVisual C++ツール  
 - 個別のコンポーネント > コードツール > Git for Windows  

 にチェックを入れ、右下の `インストール` を押します。

# 2. CUDA のインストール (nVidia製のGPUを持っている場合)  

## 2.1 CUDA 10.1 のインストール

**CUDA 10.1 より前のバージョンのCUDAがインストールされている場合は**  
**先にCUDAとNsightをアンインストールしてください**  

[https://developer.nvidia.com/cuda-downloads](https://developer.nvidia.com/cuda-downloads)
 より  
`Operating System` と `Architecture` と `Version` を各自適切なものを選択し、  
インストーラーをダウンロード、実行します。  

インストーラーを読み進め、インストール項目が現れたら  

 - CUDA  
 - Driver components  
 - Other components  

にチェックを入れ `次へ` を押します。  
`インストール場所の選択` も変更せずに `次へ` を押し、インストールを始めます。  

## 2.2 cuDNN のインストール
**アカウントの作成が必要になります**  

[https://developer.nvidia.com/rdp/cudnn-download](https://developer.nvidia.com/rdp/cudnn-download)
 より  
`Download cuDNN v7.5.0 (Feb 25, 2019), for CUDA 10.1` をダウンロードします。  
(OSは各自適切なものを選択)  

ダウンロードしたzipファイルを展開し、cudaフォルダ以下にある全てのファイル、フォルダを  
`C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\` 以下に上書きコピーします。  

# 3. OpenPose のダウンロード  

## 3.1 OpenPoseフォルダの作成

OpenPoseのプロジェクトファイルを保存するフォルダを適当に作成してください。  
ここでは `C:\openpose\` というフォルダを作成したものとして話を進めます。  

## 3.2 OpenPoseのダウンロード

ファイル エクスプローラーで `C:\openpose\` へ移動し、  
上部の `C:\openpose` と表示されているアドレスバーに `cmd` と入力しEnterを押します。  
そうするとコマンドプロンプトが立ち上がるので、  

```
git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose
```  

と入力しEnterを押します。(OpenPoseのダウンロードが始まります)  
この処理にはしばらく時間がかかります。  

**( 注意 : WSLのgitを使用するとVisual Studioでプロジェクトが正常に開けなくなります )**  

## 3.3 CMakeの修正

そのうち書く

# 4. OpenPose のビルド  

`Visual Studio 2017` を起動します。  
上部の `ファイル` > `開く` > `CMake` より `C:\openpose\openpose\CMakeLists.txt` を開きます。  
上部の `スタートアップアイテムの選択` より、実行したいプロジェクトを選択します。  
F5キーで、選択したプロジェクトの実行ができます。  