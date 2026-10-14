release: python manage.py migrate --noinput && python manage.py createcachetable django_cache_table
web: bin/start-nginx gunicorn -c gunicorn.conf pydotorg.wsgi
worker: celery -A pydotorg worker -l INFO
worker-beat: celery -A pydotorg beat -l INFO --scheduler django_celery_beat.schedulers:DatabaseScheduler
