# Guia do Desenvolvedor 1.0

Este diretório tem por finalidade armazenar um guia do desenvolvedor voltado para boas praticas, levando como referencia o livro Clean Code. Onde o gui será dividido por tópicos apresentando exemplos.

## Sempre ao atribuir um nome, utilize nomes significativos
Ao criar uma variável, método ou classe é importante que o nome atribuido ao mesmo seja autoexplicativo. Pois o desenvolvedor que realizou a tarefa sabe o que a variavel x significa, mas o proximo a realizar manutenções no código pode não saber.
Exemplo: uma variavel que armazena o valor da idade do usuário:

***Forma errada*** int x <br>
***Forma correta*** int idadeUsuario

Onde, para os nomes atribuidos utilizar abreviações não é uma boa ideia, por conta de alguma ambiguidade que possa ser causada. Logo, os nomes devem ser objetivos e claros, para que a manutenção seja a mais efetiva possivel. 

## Seja objetivo nas nomeclaturas
Alem de atribuir nomes significativos e que não gerem ambiguidade é importante que os nomes não tenham informações desnecessárias também, portanto o exeço também atrapalha. Um exemplo de exeço é no nome da variavel colocar o seu tipo:

***Forma errada*** String idadeString

Portanto como ja foi dito, seja o mais objetivo possivel, pois dessa forma os nomes também não ficam muito extensos.

## Atenção aos nomes dos métodos
Variáveis são mais pontuais, pois armazenam valores. Logo uma variável pode apresentar um nome como 'idade' ou 'soma' porem métodos se remetem a ações, métodos resultam na execução de uma ação para a geração de um resultado. 
Portanto o nome do método deve ser significativo à ação que é realizada e para uma padronização melhor é importanto definir o nome dos métodos em verbos no infinitivo.
Exemplo:

***Forma correta*** private int adicionarNumero(){}

Onde é importante que estes nomes sejam claros e tenham compatibilidade com a regra de domínio do produto de software, pois nomes com piadas internas da equipe so dificultarão manutenções futuras.

## Ser objetivo não é importante apenas nas nomeclaturas, mas também no escopo das funções
Ao declarar uma função tenha em mente que ela precisa apenas atender a uma ação. Com isso é garantido que a função tenha um tamanho mínimo para atender a uma determinada ação.
Exemplo:

***Forma errada***

    private int somarOuDividir(String operador, int num1, int num2){
      int resultado = 0;
      if (operador.equals('+')) {
          resultado = num1 + num2;    
      } else if (operador.equals('/')) {
          resultado = num1 / num2;
      }

      return resultado;
    }

***Forma correta***

    private int somar(int num1, int num2) {
        return num1 + num2; 
    }

    private int dividir(int num1, int num2) {
        return num1 / num2; 
    }

## Atenção aos parâmetros
Os parâmetros passados às funções também são dignos de atenção pelo bom desenvolvedor. É interessante reduzir ao máximo o número de parâmetros passados para uma função. Pois com a ideia que a função faz apenas uma ação em específico, fica muito mais fácil definir apenas quais são os parâmetros realmente necessários para a função. O ideial era não passar nenhum parâmetro, porem isso pode ser inviável em um grande sistema e para certas ações (funções), portanto o 'aceitavel' é passar no máximo três parâmtros.
Um exemplo bom de analisar é o disponibilizado no tópico anterior. Quando a função não tinha uma responsabilidade muito definida ela necessitava de três parâmetros, porem ao realizar a separação das prioridades cada função resultante necessitou apenas de dois parâmtros. 
Portanto é interessante analisar as funções para avaliar a real necessidade de todos os parâmetros que estão sendo utilizados.
Exemplo:

***Forma errada***

    private int somarOuDividir(String operador, int num1, int num2){
      int resultado = 0;
      if (operador.equals('+')) {
          resultado = num1 + num2;    
      } else if (operador.equals('/')) {
          resultado = num1 / num2;
      }

      return resultado;
    }

***Forma correta***

    private int somar(int num1, int num2) {
        return num1 + num2; 
    }

    private int dividir(int num1, int num2) {
        return num1 / num2; 
    }
