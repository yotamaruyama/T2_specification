8/31の設定が終わっている前提の話です。

mkdir workspace #workspaceの作成

cd workspace #workspaceに移動

django-admin start project T2　#プロジェクトの作成では

cd T2　#T2に移動

python3 manage.py startapp occupancy_rate　#アプリの作成

#workspace/T2/T2/setting.py
from django.urls import path ,include #add include

#workspace/T2/T2/setting.py
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('occupancy_rate.urls')), #add this line
]


#workspace/T2/T2/setting.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'occupancy_rate.apps.OccupancyRateConfig', #プロジェクトにアプリを認識させる
]

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [BASE_DIR / 'templates'],#テンプレートファイルの場所を指定
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

touch urls.py #urls.pyの作成
#workspace/T2/occupancy_rate/urls.py 
urlpatterns = [] #add this line