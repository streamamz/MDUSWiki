# Welcome to MDUS


## ダウンロード
[Github](https://github.com/streamamz/MDUS)もしくはPyPIからダウンロード可能です

PyPIを利用する場合は以下の通りです
```python
$ pip install MDUS
```

## 利用可能データ
MDUSで利用可能なMESSENGERでの観測データは
PDSにてダウンロード可能です

* [Planetary Data System](https://pds-ppi.igpp.ucla.edu/search/target?t=Mercury)

現在対応しているデータは以下の通りです

* [MESSENGER MAG Time-Averaged Calibrated MSO Coordinates Science Data Collection](https://pds-ppi.igpp.ucla.edu/collection/urn:nasa:pds:mess-mag-calibrated:data-mso-avg)
* [MESSENGER EPPS EPS Calibrate Scan Rate Data Collection](https://pds-ppi.igpp.ucla.edu/collection/urn:nasa:pds:mess-epps-eps-calibrated:data-scan-spec)

## 動作環境
**対応OS**

* Ubuntu 22.04
* Rocky Linux 9.5

> 上記以外のOSでの動作確認は行っていませんが、利用可能な可能性があります

**対応Pythonバージョン**

* Python 3.9以上

**依存ライブラリ**

* matplotlib
* numpy
* pandas
* requests
* spiceypy