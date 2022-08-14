# Notes

Javascript

* Comandos de entrada
  * prompt
* Funções
* Arrays
  * .indexOf();
  * .push();
  * .shift();
  * .pop();
  * .join();
* Loops
  * while
  * for
* Switch
* Datas
  * Date();
  * .parse();
  * .getDate();
  * .getMonth();
  * .getMinutes();
  * ...
* Temporizadores
  * setInterval()
    * Função anônima: () => { código... }
    * clearInterval()
  * setTimeout()
* Objetos let pessoa = {id: 1, nome: "Roberto"}; let pessoas = \[{id: 1, nome: "Roberto"}, {id: 2, nome: "Alberto"}]
* Template Strings `Aqui vai a ${variavel}`
* Desconstrução \*objetos const {nome, cargo} = pessoa; const {nome:nomePessoa, cargo} = pessoa; \*array let {0:matheus, 2:henrique} = nomes; let \[primeiro, segundo] = nomes;
*   Spread operator let primeiros = \[1, 2, 3];

    | let numeros = \[...primeiros, 4, 5, 10];      |
    | --------------------------------------------- |
    | let pessoa = {nome: "Alberto"}                |
    | let novaPessoa = {...pessoa, status: "ativo"} |
* Rest operator function convidados(...nomes) { console.log(nomes) } convidades("Roberto", "Alceu", "Irineu")
* Operações em uma lista Map; let list = \["matheus", "jose", "maria"] list.map((item, index) => {}) Reduce; Reduzir um array let numeros = \[5, 3, 2] numeros.reduce((acumulador, numero, indice, original) => {}) Find; let listagem = \[5, 3, "Jose", 2, "Matheus"]; let busca = listagem.find((item) => {return item === "Jose"}); Filter; let palavras = \["Matheus", "Ana", "Jose"] let resultado = palavras.filter((item)=>{return item.length >= 4})
* Funções anônimas (Arrow function) () => {} () - É por onde a função recebe os argumentos; => - arrrow {} - bloco de código
* includes, startsWith, endsWith íncludes; let nomes = \["Ana", "Roberto"]; nomes.includes("Ana"); // true startsWith; let nome = "Roberto" nome.startsWith("Rob"); // true endsWith let nome = "Roberto" nome.endsWith("to"); //true
* fetch
* async
* await
* localStorage
* some

\-> typeof -> Number .toFixed(2); -> document document.write(); document.getElementById(""); \* innerHTML(); \* innerText(); \* appendChild(); \* onclick; \* value; document.createElement() -> event event.preventDefault(); -> Math

\-> ponto e virgula no javascript não é necessário? -> Qual a diferença entre javascript e typescript?
