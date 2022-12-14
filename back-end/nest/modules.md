# Modules

* Uma aplicação Nest.js é organizada em modules. Se você já é familiarizado com modules do Angular, então a sintaxe utilizada pelo Nest vai lhe parecer muito familiar;
* Toda aplicação Nest tem pelo menos um module, que é o root module. É o “starting-point” da aplicação;
* Modules são uma maneira efetiva para organizamos componentes com features e capacidades relacionadas;
* É uma boa prática ter um diretório por module, contendo seus componentes;
* Modules são singletons, portanto um module pode ser importado por outros modules;
* Um module é definido quando anotamos uma classe com o decorator @Module(). Este decorator recupera um objeto que descreve o module, usando as seguintes propriedades:
  * Providers: Array de providers que devem estar disponíveis dentro do module via injeção de dependência;
  * Controllers: Os controllers que devem ser instanciados dentro do module;
  * Exports: Providers que devem ser exportados para outros modules;
  * Imports: Lista de modules necessários para uso no module corrente

![](<../../.gitbook/assets/image (4).png>)

**nest g module nome-modulo** -> Cria um novo módulo
