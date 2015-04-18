# UOL Boas práticas em Javascript

## Identação

  - A unidade de identação universal é de quatro espaços, o uso de hard tabs deve ser evitado pois ainda não existe um padrão no tamanho dos mesmos, a principal diferença é na legibilidade do código, se as hard tabs são usadas, o código poderá ser exibido com a identação de tamanho diferente dependendo do editor que os desenvolvedores utilizarem.

  - Existe o argumento contra a identação de quatro espaços de que com isto são produzidos arquivos maiores, mas como por padrão o código só irá minificado para os ambientes de produção, esta diferença é eliminada.

  - E por que não dois espaços? Como se pode observar, o espaço da identação fica muito pequeno, algumas vezes fazendo com que o desenvolvedor force mais a sua vista, sendo assim, o código fica quase tão ilegível como se não tivesse sido identado.

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

## Nomes

  - Favor escrever nomes legíveis
