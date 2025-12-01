# Tutorial
## インポート
以下のようにインポートを行います
```python
import MDUS
```
## 初回
初回利用時には以下のようなメッセージが表示されます
```shell
Some spkernel files are missing
You cannnot use some following functions:
Missing files:
	msgr_040803_150430_150430_od431sc_2.bsp
	msgr_dyn_v600.tf
	naif0012.tls
	pck00010_msgr_v23.tpc
datapath.json file is missing
create a new datapath.json file
```
それぞれの設定・対応をすることでMDUSを利用可能になります

### Spiceの設定
MDUSではMESSENGER衛星の軌道データをSpiceから取得します

初回起動時には軌道データ取得のために必要なファイルをダウンロードする必要があります

ダウンロードには`DownloadSPK`関数を利用します

```python
MDUS.DownloadSPK()
```
ダウンロード完了後は再度MDUSを読み込む必要があります

一度ダウンロードが完了すれば、以降ダウンロードを行う必要はありません

### データパスの設定
初回起動時には、MDUSが読み込むデータファイルのパスを指定する`datapath.json`が作成されます

初期設定では以下のようになっています
```shell
{
    "MAG": {
        "pfile_path": "/data/messenger/mag/pfile",
        "ofile_path": "/data/messenger/mag/ofile"
    },
    "FIPS_CDR_SCAN": {
        "pfile_path": "/data/messenger/scan/pfile",
        "ofile_path": "/data/messenger/scan/ofile"
    }
}
```
それぞれ以下に対応しています

* `MAG`：MESSENGER MAG Time-Averaged Calibrated MSO Coordinates Science Data Collectionのファイルのパス。それ以外も同様に各データ形式に対応しています
* `ofile`：PDSからダウンロードしてきたASCII形式のファイルのパス
* `pfile`：MDUSによって変換されたバイナリ形式のファイルのパス。適当なディレクトリを用意する必要があります 

これらの設定後、再度MDUSを読み込む必要があります

また、`datapath.json`はMDUSを利用する各ディレクトリごとに毎回設定をする必要があります