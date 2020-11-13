# MakeDataset_NAMIC
MRIデータ(.nrrd)からpix2pixやCycleGAN用のデータセットを作成
クラス内を書き換えれば.nilとかも対応可

## データセット入手先
[NAMIC: Brain Mutlimodality](https://www.insight-journal.org/midas/collection/view/190/1)

※t1w.nrrdとt2w.nrrdをダウンロード

## 使い方
```python
dataset = MakeDataset(domainA path, domainB path, dataset_type='cyclegan' or 'pix2pix, img_res=(width, height), dataset_slice=(slice begin, slice end), is_16bit=False)
dataset.pack()
```

## ディレクトリ構成
### pix2pix
```
T1T2_pix2pix/
    ├ train/
    │    └ T1-T2 image
    └ test/
          └ T1-T2 image
```

### CycleGAN
```
T1T2_cyclegan/
    ├ trainA/
    │    └ T1 image
    ├ testA/
    │    └ T1 image
    ├ trainB/
    │    └ T2 image
    └ testB/
          └ T2 image
```
