# UOL Boas práticas em Javascript

## Identação

  - A unidade de identação universal é de quatro espaços, o uso de hard tabs deve ser evitado pois ainda não existe um padrão no tamanho dos mesmos, a principal diferença é na legibilidade do código, se as hard tabs são usadas, o código poderá ser exibido com a identação de tamanho diferente dependendo do editor que os desenvolvedores utilizarem.

  - Existe o argumento contra a identação de quatro espaços de que com isto são produzidos arquivos maiores, mas como por padrão o código só irá minificado para os ambientes de produção, esta diferença é eliminada.

  - E por que não dois espaços? Como se pode observar, o espaço da identação fica muito pequeno, algumas vezes fazendo com que o desenvolvedor force mais a sua vista, sendo assim, o código fica quase tão ilegível como se não tivesse sido identado.

## Nomes (Variáveis, métodos, tudo que precisa ser nomeado)

- Favor escrever nomes legíveis
- Seja explícito

## Variáveis

- Declare-as o mais cedo possível, o mais próximo possível de onde as utilizará
- Evite o uso de variáveis globais

## Comentários

  - Se o seu método precisa de um comentário para explicar o que ele faz, ele está errado, modifique o seu nome e os nomes das suas variáveis de forma que ele seja auto-explicativo.

  ### Ruim:
    ```javascript
    function cir (rd) {
        var d = 2 * Math.PI;
        return d * rd; // Retorna a circunferência de um círculo
    }
    ```

    ### Bom:
    ```javascript
    function getCircunference (radius) {
        var diameter = 2 * Math.PI;
        return diameter * radius;
    }
    ```

## Chaves, condições e métodos

  - Use chaves sempre que for criar blocos de múltiplas linhas, com o uso das mesmas você facilita o fluxo de leitura dos seus companheiros de equipe e evita a adição de bugs acidentais.

  ### Ruim:
    ```javascript
    if (count === 0)
        return false;
    ```
  ### Ruim:
     ```javascript
     if (count === 0) return false;
     ```

  - As chaves devem ficar na mesma linha da abertura de um bloco
  - Deixe um espaço antes da chave de abertura de bloco

  ### Ruim:
  ```javascript
  if (count === 0){
      return false;
  }
  ```

  ### Bom:
  ```javascript
  if (count === 0) {
      return false;
  }
  ```

  - Se for usar um condicional "else", o posicione na mesma linha em que a chave do condicional "if" é fechado, tal condicional deve ser separado por um espaço das chaves.

  ### Ruim:
  ```javascript
  if (count === 0); {
      return false;
  }else {
      return true;
  }
  ```

  ### Bom:
  ```javascript
  if (count === 0) {
      return false;
  } else {
      return true;
  }
  ```

  - Falando em condicionais, evitar o uso do "else" é sempre uma boa prática para se evitar aninhamentos.

  ## Strings

  - Use aspas simples `''` para strings.

  ```javascript
  // ruim
  var name = "Francisco Silva";

  // bom
  var name = 'Francisco Silva';
  ```

  - Strings maiores que 80 characteres devem ser escritas em múltiplas linhas usando concatenação de string.
  - Sim, elas devem ser evitadas, strings longas com concatenação podem impactar na performance(principalmente no IE) se forem usadas demais, mas lembre-se, você está escrevendo código e não um livro.

  ```javascript
  // ruim
  var message = 'Esta é uma mensagem muito grande que não fica legível e quebra o fluxo de leitura dos seus amigos.';

  // ruim
  var message = 'Esta é uma mensagem muito grande \
  que não fica legível e \
  quebra o fluxo de leitura dos seus amigos, \
  ler dessa forma fica é bem lento.';

  // bom
  var message = 'Apesar desta mensagem ser grande ' +
    'o uso do símbolo de concatenação "+" ' +
    'deixa claro para os seus amigos que a mensagem continua.' +
    'na linha seguinte.';
  ```

- Falando em performance, lembre-se sempre do IE, tente sempre usar Array#join no lugar da concatenação tradicional de uma string: [jsPerf](http://jsperf.com/string-vs-array-concat/2).

  ```javascript
  var items;
  var messages;
  var length;
  var i;

  messages = [{
    state: 'log',
    message: 'Tal coisa aconteceu.'
  }, {
    state: 'warn',
    message: 'Opa, algo não está normal…'
  }, {
    state: 'error',
    message: 'Eita, rolou uma coisa aqui!'
  }];

  length = messages.length;

  // ruim
  function inbox (messages) {
    items = '<ul>';

    for (i = 0; i < length; i++) {
      items += '<li>' + messages[i].message + '</li>';
    }

    return items + '</ul>';
  }

  // bom
  function showMessages (messages) {
      var itens = [];
      itens.push('<ul>');

      for (var i = 0, length = messages.length; i < length; i++) {

      }

      itens.push('</ul>');
      return itens;
  }

  // bom
  function inbox (messages) {
    items = [];

    for (i = 0; i < length; i++) {
      items[i] = '<li>' + messages[i].message + '</li>';
    }

    return '<ul>' + items.join('') + '</ul>';
  }
  ```

## Objetos

- Use a sintaxe literal para a criação de objetos
  ```javascript
  // ruim
  var myObject = new Object();

  // bom
  var myObject = {};
  ```
- Não use palavras reservadas como chaves
  ```javascript
  // ruim
  var myObject = {
    default: 'value'
  };

  // bom
  var myObject = {
    defaults:'value'
  };
  ```

## Array

- Use a sintaxe literal para a criação de arrays
  ```javascript
  // ruim
  var myList = new Array();

  // bom
  var myList = [];
  ```
