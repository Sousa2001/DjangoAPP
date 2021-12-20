# djangoP1

##How To Clone Project:

  1)  wget https://github.com/Sousa2001/DjangoApp
  2)  $ python3 -m venv env
  3)  source env/bin/activate
  4)  (env) $ pip install django
  5)  (env) $ pip install django-environ
  6)  pip install uwsgi
  7)  Add to setting.py 

	 STATIC_ROOT = 'static/'
	 STATIC_URL = '/static/'

  8) (env) $ ./manage.py collectstatic
  9) Now create a file called mysite_nginx.conf in the /etc/nginx/sites-available/ and copy the content from
	https://uwsgi-docs.readthedocs.io/en/latest/tutorials/Django_and_nginx.html#configure-nginx-for-your-site
  10) sudo ln -s /etc/nginx/sites-available/mysite_nginx.conf /etc/nginx/sites-enabled/
  11) (env) $ uwsgi --socket :8001 --module mysite.wsgi 
