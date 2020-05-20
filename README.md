# Javascript III

## Métodos de Array
- map / reduce / filter / foreach

## Protocolo HTTP
- [Uma visão geral do HTTP](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Overview);

HTTP é um protocolo que faz a conexão entre um receptor, normalmente o navegador (_browser_) e um servidor. Ela é a base da transferência de dados na Web.

Quando um site é acessado, seu navegador envia uma solicitação (_request_) para o servidor onde ele está hospedado. Este, por sua vez, envia uma resposta (_respose_) com o resultado dessa solicitação.

![Diagrama: à esquerda um computador com o texto "client" dentro dele e a direita, uma CPU com o texto "Server". Uma flecha sai do Cliente e vai para o Servidor, com o texto "HTTP Request" como legenda. Uma outra flecha sai do Servidor e vai para o Cliente, com a legenda "HTTP Response".](./img/client-server.png)

Por exemplo, ao chamar um script, uma folha de estilo ou uma imagem, é feita uma requisição para cada um desses recursos.

![Screenshot de DevTools do Firefox, com a aba Network aberta, mostrando uma tabela de requisições](./img/http-exemplo.png)

### Anatomia de uma Requisição HTTP
![Diagrama com informações sobre a resquição. GET é o método, / é o caminho, HTTP/1.1 é a versão do protocolo e Host:developer.mozilla.org faz parte do Headers/cabeçalho](./img/HTTP_Request.png)

- Método HTTP, verbo como GET, POST, PUT, DELETE. As requisições para pegar e mostrar dados normalmente são feitas através de GET. Os demais verbos podem ser usados para modificar dados do servidor ou banco de dados;
- Origem e porta da requisição e caminho do arquivo solicitado;
- Versão do protocolo HTTP;
- Cabeçalhos (_header_) com informações para os servidor;
- Corpo (_body_) que são necessários para algumas requisições POST.

### Anatomia de uma Resposta HTTP
![Diagrama com informações sobre a resposta. HTTP/1.1 é a versão do protocolo, 200 é o código de status, OK é a mensagem do status e Date:... faz parte do Headers/cabeçalho](./img/HTTP_Response.png)

- Versão do protocolo HTTP que o servidor segue;
- Código de status (veja referências abaixo);
- Cabeçalhos (_header_) com informações vindas do servidor;
- Corpo (_body_) com dados solicitados, se houver.


**Código de Status das Respostas**
- [HTTP Statuses](https://httpstatuses.com/)
- [HTTP Dogs](https://httpstatusdogs.com/)
- [HTTP Cats](https://http.cat/)

## JSON
JSON é a abreviação de JavaScript Object Notation ou Notação de Objeto Javascript. É uma sintaxe para armazenar e tranferir dados. Trata-se de uma **string** que se parece bastante com um **objeto** Javascript.

```json
[
  {
    "nome": "Mellina",
    "idade": 21,
    "profissão": "desenvolvedora"
  },
  {
    "nome": "Joana",
    "idade": 12,
    "profissão": "criança"
  }
]
```

Nota-se que as propriedades, no JSON, necessariamente tem que estar entre `""`.

### JSON.parse(data)
- Manipulando dados no formato json (conversão / navegação pela estrutura)


## API
- [Open APIs](https://github.com/public-apis/public-apis);
- [What is an API? [Vídeo em inglês]](https://www.youtube.com/watch?v=s7wmiS2mSXY);
- [O que significa API e como ela funciona](https://www.redhat.com/pt-br/topics/api/what-are-application-programming-interfaces)

API é a abreviação de _Application Programming Interface_, ou em português, Interface de Programação de Aplicativos. Trata-se de uma interface de comunicação e integração entre aplicações.

Por exemplo, para usar dados do Maps, o Google desenvolveu uma API para ser consumida entre desenvolvedoras.

Cada API possui uma documentação e modo de comunicação, quais informações (headers e body) enviar para a API para conseguir ter acesso a seus dados. Algumas delas permitem que seja feita alteração de dados e não somente consulta.

Alguns verbos, métodos, que são usados:

Método | O que faz        | Status de retorno |
-------|------------------|-------------------|
GET    | Traz informações | 200               |
POST   | Cria um novo item| 201               |
PUT    | Atualiza um item | 200               |
DELETE | Remove um item   | 200               |

- [O que é REST API](https://rockcontent.com/blog/rest-api/);
- [RESTful API (REST API) - inglês](https://searchapparchitecture.techtarget.com/definition/RESTful-API);

É possível também se deparar com a nomenclatura **REST API**. É uma abreviação para _Representational State Transfer_, ou em português, Transferência de Estado Representacional.

Trata-se de uma arquitetura em que uma API é construída, seguindo determinadas práticas, usando os verbos existentes do protocolo HTTP. É como se fosse um método BEM para APIs. É possível fazer um estilo CSS sem seguir o método, mas pode ser vire uma bagunça e não seja intuitivo. A arquitetura REST API faz com que o consumo das APIs sejam mais intutivos e organizados.


### Acessando dados de APIs
- [JSON Placeholder](https://jsonplaceholder.typicode.com/guide.html);

Para acessar uma API, via de regra, basta acessarmos sua URL em um navegador. Ela nos retorna o dado designado a esse caminho, normalmente um JSON.

Acessando a partir do navegador, estamos fazendo uma requisição `GET`. Para fazer requisição com outros verbos (`POST`, por exemplo), temos que usar outras ferramentas. Veja a seção Requisições.

### O que é CORS?

- [Cross-Origin Resource Sharing (CORS)](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Controle_Acesso_CORS);

Quando se faz uma requisição para um recurso externo, por padrão, o cliente (navegador) bloqueia se as origens são diferentes. O servidor deve, então, permitir o acesso de origens distintas. O CORS, ou Compartilhamento de Recursos de Origem Diferente, vem como mecanismo para permitir o acesso desses recursos.

Não são todos os recursos que necessitam de CORS. Alguns exemplos:
- Requisições com `XMLHttpRequest` e `fetch`;
- Fontes web.

É importante notar que é um problema que deve ser resolvido no lado do **servidor**.


## Requisições
- XMLHttpRequest

### Promises
Promise é um objeto que representa o sucesso ou fracasso de uma operação **assíncrona**. 

- Fetch
- async e await

## Autenticação