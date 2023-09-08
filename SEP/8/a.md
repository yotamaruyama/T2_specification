from django.urls import path

from . import views

urlpatterns = [
    
    path('occupancy_rate/', views.MachineDataView.as_view(), name='occupancy_rate'),
]

