# CineNews
 - [ ] Alterar o idioma do projeto para `pt-br`

localizar o arquivo settings.py na pasta do projeto
 mudar para pt-br  ---  linha 106

- [ ] Alterar o timezone do projeto para `America/Sao_Paulo`
localizar o arquivo settings.py na pasta do projeto
 mudar para America/Sao_Paulo  ---  linha 108

Criar o app receitas
Criar um novo terminal de uso
cd PersonalCheffproj
python manage.py startapp receitas

- [ ] Registar o app receitas

abrir o arquivo settings.py que está dentro da pasta PersonalCheffProj
acrescetar em INSTALLED_APPS (linha 33) o seguinte item:
'receitas',

- [ ] Criar a view para a rota inicial



criar dentro da pasta receitas um arquivo chamado urls.py contendo:

from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index')
]


abrir o arquivo view.py

from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return HttpResponse("Seja bem Vindo")



- [ ] Registar a rota inicial
Modificar o arquivo urls.py da pasta PersonalCheffProj

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('receitas.urls')),
]

