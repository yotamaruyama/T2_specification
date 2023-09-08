T2/
|-- T2/
|   |-- __init__.py
|   |-- asgi.py
|   |-- settings.py
|   |-- urls.py
|   |-- wsgi.py
|
|-- ocuupancy_rate/
|   |-- templates/occupancy_rate
|   |   |--occupancy_rate.html
|   |
|   |-- __init__.py
|   |-- admin.py
|   |-- apps.py
|   |-- migrations/
|   |   |-- __init__.py
|   |
|   |-- models.py
|   |-- tests.py
|   |-- views.py
|   |-- urls.py
|
|-- manage.py
|-- db.sqlite3  (SQLiteを使用する場合)
|-- requirements.txt
|-- .gitignore




$.get('/occupancy_rate/', {time_scale: timeScale},null,'json')
,null,'json'を追加したらなおった