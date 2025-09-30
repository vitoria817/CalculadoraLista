
import java.util.InputMismatchException;
import java.util.Scanner;
import java.util.ArrayList; // armazenar os cálculos
import java.util.List;// Interface, para declarar o histórico de cálculos

public class CalculadoraLista {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int opcaoDigitada;
        List<String> historico = new ArrayList<>(); // Lista para armazenar histórico

        while (true) { //loop
            try {
                System.out.println("====================================");
                System.out.println("|           CALCULADORA            |");
                System.out.println("====================================");
                System.out.println("|   [1]   SOMAR                    |");
                System.out.println("|   [2]   SUBTRAIR                 |");
                System.out.println("|   [3]   MULTIPLICAR              |");
                System.out.println("|   [4]   DIVISÃO                  |");
                System.out.println("|   [5]   HISTÓRICO                |");
                System.out.println("====================================");
                System.out.print("Digite sua opção e clique em ENTER para continuar..\n");

                opcaoDigitada = scanner.nextInt();
                if (opcaoDigitada < 1 || opcaoDigitada > 5) {
                    System.out.println("------------------------------");
                    System.out.println("INVÁLIDO DIGITE OPÇÃO DE 1 A 5");
                    System.out.println("------------------------------");
                    System.out.println("\n\n"); //espaço para antes do menu
                    continue; // Volta para o início se digitar errado
                }

                if (opcaoDigitada == 5) { // Exibir histórico
                    System.out.println("===== HISTÓRICO DE CÁLCULOS =====");
                    if (historico.isEmpty()) {
                        System.out.println("Nenhum cálculo realizado ainda.");
                    } else {
                        for (String registro : historico) {//percorre todos os cálculos feitos
                            System.out.println(registro);
                        }
                    }
                    System.out.println("\n\n");
                    continue;//após mostrar histórico volta para o menu
                }

                double num1, num2, resultado;
                String operador = "";//armazena o símbolo que será escolhido
                switch (opcaoDigitada) {
                    case 1: {
                        operador = "+";
                        System.out.println("opção selecionada: SOMAR");
                        System.out.println("digite o primeiro numero e clique em ENTER para continuar..");
                        num1 = scanner.nextDouble();
                        System.out.println("digite o segundo numero e clique em ENTER para continuar..");
                        num2 = scanner.nextDouble();
                        resultado = num1 + num2;
                        System.out.println("RESULTADO: " + resultado);
                        historico.add(num1 + " + " + num2 + " = " + resultado); // Adiciona ao histórico
                        System.out.println("\n\n");
                        break;
                    }
                    case 2: {
                        operador = "-";
                        System.out.println("opção selecionada: SUBTRAIR");
                        System.out.println("digite o primeiro numero e clique em ENTER para continuar..");
                        num1 = scanner.nextDouble();
                        System.out.println("digite o segundo numero e clique em ENTER para continuar..");
                        num2 = scanner.nextDouble();
                        resultado = num1 - num2;
                        System.out.println("RESULTADO: " + resultado);
                        historico.add(num1 + " - " + num2 + " = " + resultado); // Adiciona ao histórico
                        System.out.println("\n\n");
                        break;
                    }
                    case 3: {
                        operador = "*";
                        System.out.println("opção selecionada: MULTIPLICAÇÃO");
                        System.out.println("digite o primeiro numero e clique em ENTER para continuar..");
                        num1 = scanner.nextDouble();
                        System.out.println("digite o segundo numero e clique em ENTER para continuar..");
                        num2 = scanner.nextDouble();
                        resultado = num1 * num2;
                        System.out.println("RESULTADO: " + resultado);
                        historico.add(num1 + " * " + num2 + " = " + resultado); // Adiciona ao histórico
                        System.out.println("\n\n");
                        break;
                    }
                    case 4: {
                        boolean valido = false; // Loop para A divisão controla
                        while (!valido) {
                            operador = "/";
                            System.out.println("opção selecionada: DIVISÃO");
                            System.out.println("digite o primeiro numero e clique em ENTER para continuar..");
                            num1 = scanner.nextDouble();
                            System.out.println("digite o segundo numero e clique em ENTER para continuar..");
                            num2 = scanner.nextDouble();

                            if (num1 != 0 && num2 != 0) {
                                resultado = num1 / num2;
                                System.out.println("RESULTADO: " + resultado);
                                historico.add(num1 + " / " + num2 + " = " + resultado); // Adiciona ao histórico
                                System.out.println("\n\n");
                                valido = true; //loop parar
                            } else {
                                System.out.println("divisão por zero não é permitido, tente novamente.\n");
                                System.out.println("OPÇÃO INVÁLIDA TENTE NOVAMENTE");
                                System.out.println("\n\n");
                            }
                        }
                        break;
                    }
                }

            } catch (InputMismatchException e) {
                System.out.println("-----------------------------");
                System.out.println("    DIGITE APENAS NÚMEROS    ");
                System.out.println("-----------------------------");
                scanner.next();
            }
        }
    }
}
