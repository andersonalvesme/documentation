# Inversion of Control

O pattern injeção de dependência é utilizado no Nest quando injetamos uma instância do nosso Service Provider em nosso Controller, fazendo uso da Injeção de dependência baseada no Construtor. Exemplo:

```javascript
import { Body, Controller, Post } from "@nestjs/common";
import JogadorDto from "./dtos/jogador.dto";
import { JogadoresService } from "./jogadores.service";

@Controller("jogadores")
export class JogadoresController {

    constructor(private readonly jogadoresService: JogadoresService) {}

    @Post()
    async create(@Body() jogadorDto: JogadorDto) {
        const { nome } = jogadorDto;
        this.jogadoresService.create(jogadorDto);
    }

}
```

Injeção de dependência é uma técnica de Inversão de Controle (IoC), na qual delegamos a instanciação de dependências para o IoC Container (em nosso caso, o runtime do NestJS), ao invés de fazermos em nosso próprio código de forma imperativa.

#### Passo a passo

Primeiro nós definimos um Provider utilizando o decorator @Injectable. Exemplo:

```javascript
import { Injectable, Logger } from "@nestjs/common";
import JogadorDto from "./dtos/jogador.dto";
import Jogador from "./interfaces/jogador.interface";
import { randomUUID } from "crypto";

@Injectable() // Decorator Injectable
export class JogadoresService {

    private readonly logger = new Logger(JogadoresService.name);

    private jogadores: Jogador[] = [];

    async create(jogadorDto: JogadorDto): Promise<void> {
```

Em seguida, solicitamos ao Nest que faça a injeção do provider dentro da classe controller. Exemplo:

```javascript
import { Body, Controller, Post } from "@nestjs/common";
import JogadorDto from "./dtos/jogador.dto";
import { JogadoresService } from "./jogadores.service";

@Controller("jogadores")
export class JogadoresController {

    constructor(private readonly jogadoresService: JogadoresService) {}

    @Post()
    async create(@Body() jogadorDto: JogadorDto) {
```

O nosso provider também é registrado no Nest IoC Container. Exemplo:

```javascript
import { Module } from '@nestjs/common';
import { JogadoresController } from './jogadores.controller';
import { JogadoresService } from './jogadores.service';

@Module({
  controllers: [JogadoresController],
  providers: [JogadoresService]
})
export class JogadoresModule {}
```

Existem três etapas principais nesse processo:

1 - Em jogadores.service.ts, o decorator @Injectable declara a classe JogadoresService como uma classe que pode ser gerenciada pelo Nest IoC Container

2 - Em jogadores.controller.ts, JogadoresController declara uma dependência do token JogadoresService com a injeção de dependência baseada no construtor:

```javascript
constructor(private readonly jogadoresService: JogadoresService) {}
```

3- Em app.module.ts, nós associamos o token JogadoresService com a classe JogadoresService do arquivo jogadores.service.ts

```javascript
@Module({
  controllers: [JogadoresController],
  providers: [JogadoresService]
})
```

_**E como essa associação, também chamada de registro acontece?**_

1 - Quando o Nest IoC Container instancia um JogadoresController, ele primeiro procura por quaisquer dependências

2 - Quando o container encontra a dependência de JogadoresService, realiza uma pesquisa pelo token JogadoresService, que retorna a classe JogadoresService, utilizando a etapa de registro mencionada anteriormente

3 - Assumindo o escopo SINGLETON (comportamento padrão), o Nest criará uma instância de JogadoresService, armazenará em cache e retornará, ou, se já estiver em cache, retornará a instância existente!
