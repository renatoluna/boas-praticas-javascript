# UOL Boas práticas em Javascript

## Identação

  - A unidade de identação universal é de quatro espaços, o uso de hard tabs deve ser evitado pois ainda não existe um padrão no tamanho dos mesmos, a principal diferença é na legibilidade do código, se as hard tabs são usadas, o código poderá ser exibido com a identação de tamanho diferente dependendo do editor que os desenvolvedores utilizarem.

  - Existe o argumento contra a identação de quatro espaços de que com isto são produzidos arquivos maiores, mas como por padrão o código só irá minificado para os ambientes de produção, esta diferença é eliminada.

  - E por que não dois espaços? Como se pode observar, o espaço da identação fica muito pequeno, algumas vezes fazendo com que o desenvolvedor force mais a sua vista, sendo assim, o código fica quase tão ilegível como se não tivesse sido identado.

## Nomes (Variáveis, métodos, tudo que precisa ser nomeado)

- Favor escrever nomes legíveis
- Seja explícito

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

## Chaves

  - Use-as sempre que for criar blocos de múltiplas linhas, com o uso das mesmas você facilita o fluxo de leitura dos seus companheiros de equipe e evita a adição de bugs acidentais.

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

  - Se for usar um condicional "else", o posicione na mesma linha em que a chave do condicional "if" é fechado, tal condicional deve ser separado por um espaço da chave anterior ao mesmo.

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
