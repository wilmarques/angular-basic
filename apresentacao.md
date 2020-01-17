# Angular

## O que é Angular

Angular é um framework javascript utlizado para o desenvolvimento web. Com ele podemos construir aplicações interativas do tipo Sigle-page application.

## Configuração do ambiente

Node 10.9.0+\
https://nodejs.org

> Recomendamos a utilização do NVS (Node Version Switcher)
https://github.com/jasongin/nvs

Angular CLI\
npm install -g @angular/cli\
https://angular.io/cli

## Iniciando uma aplicação

ng new wolters-kluwer\
cd wolters-kluwer\
ng serve

https://angular.io/cli/new

## ng generate

ng generate `option`

https://angular.io/cli/generate

## Binding

Interpolation: {{ value }}
- associa informação do componente para o template HTML

Property Binding: [property]="value"
- associa informação do componente para o template HTML

Event Binding: (event)="handler"
- associa informação do template HTML para o componente

Two-Way Data Binding: [(ngModel)]="property"
- associa informação entre ambos, ou seja, mantém ambos atualizados (componente e template HTML)

## Routing

## Services

## Forms

## dependencies vs devDependencies

As dependencies são pacotes necessários para executar a aplicação em ambiente de produção
As devDependencies são pacotes necessários para o ambiente de desenvolvimento

Exemplo de dependencie

- @angular/core

Exemplo de devDependencie

- @angular/cli

## Styles

Cada componente deverá ter sua própria estilização.

Os estilos globais da aplicação serão implementados no arquivo `src/styles.css`.

## Deployment

ng build --prod

https://angular.io/cli/build

## Boas práticas

### Lazy Loading

Carregamento de módulos por demanda

- Redução do tamanho do aplicativo
- Melhora o tempo de inicialização da aplicação
- Não carrega módulos que não são usados

https://angular.io/guide/lazy-loading-ngmodules

### Unsubscribe

Não cancelar a inscrição de um `Obsevable` levará a vazamentos indesejados de memória.

Imagem1
Imagem2

### Type any

Evite o type any ao declarar as variáveis. Isso pode causar problemas indesejados.

Sem tipagem

```javascript
const x = 1;
const y = 'a';
const z = x + y;

console.log(`Value of z is: ${z}`

// Output
Value of z is 1a
```

Com tipagem correta das variáveis

```javascript
const x: number = 1;
const y: number = 'a';
const z: number = x + y;

// This will give a compile error saying:

Type '"a"' is not assignable to type 'number'.
```

### Módulos reaproveitáveis

Módulo `core` contém componentes que serão compatilhados em toda a aplicação (header, menu, footer).

Módulo `shared` pode conter componentes, diretivas, pipes que serão compartilhados entre vários módulos e componentes, mas não necessariamente em toda a aplicação.