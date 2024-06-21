pip freeze > requirements.txt 
django-admin startproject chaiheadq
py manage.py makemigrations
py manage.py migrate
py manage.py createsuperuser


MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')

STATIC_URL='static/'
STATICFILES_DIRS=[os.path.join(BASE_DIR,'static')]

from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    #...
    #...
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

py manage.py startapp tweet

py -m  pip install pillow