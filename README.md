
                             
                        
  O CalculadoraLista é uma aplicação em Java que funciona no console e permite realizar operações básicas de matemática: adição, subtração, multiplicação e divisão.
Ele também mantém um histórico das operações realizadas, para que você possa consultar todos os cálculos feitos anteriormente.

O projeto é ideal para quem está aprendendo:

Java básico e console applications;

Estruturas de repetição (while);

Estruturas de decisão (switch-case);

Tratamento de exceções (try-catch);

Estruturas de dados (ArrayList, List).




Como Usar
1.clonar o código fonte


2. Abrir o projeto



Abra o projeto no seu editor de Java favorito (IntelliJ, Eclipse, VS Code, etc.).


3. Compilar e executar No terminal, dentro da pasta do projeto:



javac CalculadoraLista.java
java CalculadoraLista



Funcionalidades

Após executar, você verá o menu no console:

====================================
|           CALCULADORA            |
====================================
|   [1]   SOMAR                    |
|   [2]   SUBTRAIR                 |
|   [3]   MULTIPLICAR              |
|   [4]   DIVISÃO                  |
|   [5]   HISTÓRICO                |
====================================
Digite sua opção e clique em ENTER para continuar..

[1] SOMAR: realiza a adição de dois números.

[2] SUBTRAIR: realiza a subtração de dois números.

[3] MULTIPLICAR: realiza a multiplicação de dois números.

[4] DIVISÃO: realiza a divisão de dois números (não permite divisão por zero).

[5] HISTÓRICO: exibe todos os cálculos realizados até o momento.




Exemplo de Uso

Opção selecionada: SOMAR
Digite o primeiro número: 10
Digite o segundo número: 5
RESULTADO: 15.0

Opção selecionada: HISTÓRICO
10.0 + 5.0 = 15.0



Tratamento de Erros

O programa impede entradas inválidas (como letras) usando InputMismatchException.

Evita divisão por zero solicitando ao usuário um novo valor caso seja digitado 0.