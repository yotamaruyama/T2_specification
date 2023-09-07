2. モデルの作成
稼働率を計算するための基本データを保存するモデルを作成します。

python
Copy code
# models.py

from django.db import models

class MachineData(models.Model):
    timestamp = models.DateTimeField(auto_now_add=True)
    is_operational = models.BooleanField(default=False)
このモデルでは、timestampは記録時点の時間、is_operationalはマシンが稼働中かどうか（True/False）を示します。

python3 manage.py makemigrations #マイグレーションファイルの作成

下のコマンドを実行した
python3 manage.py migrate　ocupancy_rate #個別のアプリケーションを指定する（トラブルの際のリスクを減らす
例））
root@bb27f0248fc4:/workspace/T2# python3 manage.py makemigrations occupancy_rate
Migrations for 'occupancy_rate':
  occupancy_rate/migrations/0001_initial.py
    - Create model MachineData

root@bb27f0248fc4:/workspace/T2# python3 manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, occupancy_rate, sessions
Running migrations:
  Applying occupancy_rate.0001_initial... OK



