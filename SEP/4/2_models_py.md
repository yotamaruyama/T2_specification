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

