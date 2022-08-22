# Controllers

* Responsáveis por lidar com as requisições recebidas e retornar responses para o cliente;
* Encaminham as requisições para um path específico. Exemplo: “/jogadores” para o resource jogadores;
* São definidos quando anotamos uma classe com o decorator @Controller;
* O decorator aceita uma string, que é o path a ser controlado pelo controller:

![](<../../.gitbook/assets/image (2).png>)

* Pussuem handlers, que lidam diretamente com métodos HTTP, tais como: GET, POST, DELETE, etc.:
  * Handlers são métodos implementados dentro classe controller, que são anotados com os decorators @Get, @Post, @Delete, etc.

![](<../../.gitbook/assets/image (3).png>)

![](../../.gitbook/assets/image.png)

**nest g controller nome-controller** -> Cria um novo controller;
