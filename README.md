# desafio_loja_virtual
O desafio de fazer um CRUD com VueJs e uma API Rest de Python/Django

Obs: Para evitar o erro de "No 'Access-Control-Allow-Origin' header is present on the requested resource." foi utilizado a extensao 
"Moesif CORS" do google chrome. Ela ativada evita o erro citado acima 

Extensao Chrome
https://chrome.google.com/webstore/detail/moesif-origin-cors-change/digfbfaphojjndkpccljibejjbppifbc/related?hl=en-US

- Baixe o repositorio

- Entre na pasta "desafio_loja_virtual\loja_virtual\venv"

- $ .\Scripts\activate
O comando acima ira aticar o venv

- Entre na pasta "\desafio_loja_virtual\loja_virtual\loja_virtual"

- $ python manage.py runserver

- Abra outro terminal

- Entre na pasta "\desafio_loja_virtual\loja_virtual\loja_virtual_vue"

- $ npm install

- $ npm run serve

Abra o link do terminal do Vuejs em seu navegador, caso nao apareca os produtos de inicio, abra a extensao do chrome e ative, recarregue a pagina.

Dependencias do Django: 

pip install django
pip install django-rest-framework
pip install django-cors-headers 
pip install djoser 
pip install pillow 
pip install stripe

Dependencias do Vue:

npm install -g @vue/cli
npm install bulma-toast