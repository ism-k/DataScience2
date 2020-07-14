# DataScience2

データサイエンス演習Ⅱの課題処理環境．

## メモ

### keras-CenterNet
そのままのモデルだと全然精度が出ないはず．
`inference.py` の `prediction_model.load_weights()` の引数を `by_name=False, skip_mismatch=False` とするとワーニングが消えてちゃんと推論してくれる

### chainer_nic
 `cocoapi` のインストールで 「/Wno-cpp は無効です」 とかいうエラーが出て進まなかったので，
[CornerNet-LiteのWindows 10での学習（ようやくトレーニング）](https://qiita.com/sounansu/items/6836e5a4d81e157941c2#1-ms-coco-apis%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB)
 って記事を参考に
 
 `extra_compile_args=['-Wno-cpp', '-Wno-unused-function', '-std=c99'],` を `extra_compile_args={'gcc': ['/Qstd=c99']},` にして
 `cocoapi/PythonAPI/` 内で `python setup.py build_ext install` したらうまく行ったような気がする．とりあえずエラーは消えた．
