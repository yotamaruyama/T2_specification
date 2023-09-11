from django.urls import path

from . import views

urlpatterns = [
    
    path('occupancy_rate/', views.MachineDataView.as_view(), name='occupancy_rate'),
]

https://chat.openai.com/share/ddd9e3a9-b41d-40b7-b5f0-21c745e9c4e1

上記を参考にしてdjangoのプログラムを作成しました。
