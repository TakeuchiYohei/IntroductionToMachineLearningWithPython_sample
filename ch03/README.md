# 教師なし学習

### [前処理とスケール変換](https://github.com/kajyuuen/IntroductionToMachineLearningWithPython/blob/master/ch03/applying_data_transformations.ipynb)

- StanderdScaler
    - 特徴: 個々の特徴量を平均0分散が1になるように変換する
    - 問題点: Min, Maxが一定の範囲に入ることを保証するわけではない
- RobustScaler
    - 特徴: 分散の代わりに中央値と四分位数を用いる -> 外れ値を無視
- MinMaxScaler
    - 特徴: データが全て0~1の範囲に定まるように変換する
- Normalizer
    - 特徴: 特徴量ベクトルがユークリッド長1になるようにする -> ベクトルの長さではなく角度が問題になる場合に用いられる
    
    
### [次元削減](https://github.com/kajyuuen/IntroductionToMachineLearningWithPython/blob/master/ch03/dimensionality_reduction.ipynb)

教師無し学習を用いたデータ変換には，可視化，データの圧縮，表現の発見が挙げられる．
それらを目的として最も用いられるアルゴリズム

- 主成分分析(Principal Component Analysis: PCA)
    - PCAはデータセットの特徴量を相互に統計的に関連しないように回転させる手法
- 非負値行列因子分解(Non-Negative Matriz Factorization: NMF)
    - 組み合わされたデータを作りあげている元の成分を特定することが出来る
    - PCAよりわかりやすい成分に分解出来る
- t-SNE
    - 二次元散布図を用いたデータの可視化によく用いられるアルゴリズム
    - 殆どの場合3以上の新しい特徴量を生成するように利用することはない
    
### [クラスタリング](https://github.com/kajyuuen/IntroductionToMachineLearningWithPython/blob/master/ch03/clustering.ipynb)

#### アルゴリズム

- k-means
    - クラスタセンタを用いてクラスタの特徴を表すことが出来る
    - 個々のデータポイントがクラスタセンタによって表現された成分分解手法
- DBSCAN
    - ノイズを検出可能
    - 自動的にクラスタの数を決められる
    - 複雑な形状のクラスタを発見出来る
- 凝集型クラスタリング
    - データの階層的な分割の候補を提示出来る

#### クラスタリングアルゴリズムの評価

- 正解アルゴリズムを用いたクラスタリングの評価
    - 調整ランド指数(ARI)
    - 正規化相互情報量(NMI)
- 正解データを用いないクラスタリングの評価
    - シルエット係数
