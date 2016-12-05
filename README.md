# Routing

Em vez de preencher uma única view com mais código do que o necessário, as rotas nos permitem mapear URLs por meio de controllers e templates.

## app.js

código         | funcionalidade
---------------|-------
$routeProvider | variável que definirá as rotas da aplicação
.when( '/',    | mapeia a URL / para o controlador ***HomeController*** e o template ***home.html***
HomeController | usa o ***js/services/photos.js*** para obter fotos e as mantém no ***$scope.photos***
home.html      | usa o loop ***ng-repeat*** para mostrar as fotos
.otherwise()   | caso haja algum problema, essa função redicionará o usuário para a URL ***"/"***
PhotoController | ***$routeParams*** recupera o ***id*** para URL usando ***$routeParams.id***

Quando o usuário visitar "/", uma view será construída pela ***home.html*** dentro da ***div ng-view*** no arquivo ***index.html***.

Para obter as fotos individuais, primeiro usamos o serviço ***photos.js*** para pegar o array de fotos do servidor, e depois usamos o ***$routeParams.id*** para acessar a foto pelo index.

Ao clicar nos links, o app não recarrega toda a página, mas apenas a parte da view abrangida pela ***div ng-view*** é alterada.
