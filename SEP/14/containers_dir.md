❯ tree
.
├── containers
│   ├── django
│   │   ├──  Dockerfile
│   │   └──  entrypoint.sh
│   ├── postgres
│   │   └── Dockerfile
│   └── nginx
│       ├── Dockerfile
│       └── conf.d
│           └── default.conf
├── .gitignore
├── .env
├── .env.prod
├── docker-compose.prod.yml
├── docker-compose.yml
└── requirements.txt


❯ tree
.
├── containers
│   ├── django
│   │   ├── Dockerfile
│   │   └── dev
│   │       └── Dockerfile
│   ├── postgres
│   │   └── Dockerfile
│   └── nginx
│       ├── Dockerfile
│       └── conf.d
│           └── default.conf
│── T2/
│   │── __init__.py
│   │── asgi.py
│   │── settings.py
│   │── urls.py
│   │── wsgi.py
│
│── ocuupancy_rate/
│   │── templates/occupancy_rate
│   │   │──occupancy_rate.html
│   │
│   │── __init__.py
│   │── admin.py
│   │── apps.py
│   │── migrations/
│   │   │── __init__.py
│   │
│   │── models.py
│   │── tests.py
│   │── views.py
│   │── urls.py
│
│── manage.py
│── db.sqlite3  (SQLiteを使用する場合)
│── requirements.txt
│── .gitignore
├── .env
├── .env.prod
├── .gitignore
├── docker-compose.prod.yml
├── docker-compose.yml
├── entrypoint.sh
├── manage.py
├── requirements.txt
└── static
│   │── templates/occupancy_rate