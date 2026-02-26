# OpenFOAM parallel processing on Fugaku
使い方 : 
+ 途中計算は `output...../0/1/stdout.1.0` に出力される
+ `run.sh`中の`hp123456`の部分と`u123456`の部分は自分のものに書き換える


### 注意点
+ gmshで作成したメッシュファイル用に
  `gmshToFoam foo.msh` および `transformPonits ` のコマンドがジョブスクリプト中に入っているので、ICEM CFDで作成したメッシュで解析したい場合はジョブスクリプトを書き換えてください
+ 富岳の計算ノードは1ノード当たり48コアある。しかし, 並列数(ジョブスクリプト中の`NP`)が多い方が速いとは限らない。例えば, `meshing_deformation_cfd_batch/data/` 程度のメッシュ数の場合, 並列数8~16が適当だと思われる.
+ `0/U` ファイルについて
