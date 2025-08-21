package tarefa02;

import java.util.Scanner;

// Exceção 1
class NomeInvalidoException extends Exception {
    public NomeInvalidoException(String msg) {
        super(msg);
    }
}

// Exceção 2
class IdadeNegativaException extends Exception {
    public IdadeNegativaException(String msg) {
        super(msg);
    }
}

// Exceção 3
class ValorMuitoAltoException extends Exception {
    public ValorMuitoAltoException(String msg) {
        super(msg);
    }
}

public class Tarefa02 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Digite seu nome: ");
            String nome = sc.nextLine();
            if (nome.isEmpty()) {
                throw new NomeInvalidoException("O nome não pode ser vazio!");
            }
            System.out.println("Nome válido: " + nome);

            System.out.print("Digite sua idade: ");
            int idade = sc.nextInt();
            if (idade < 0) {
                throw new IdadeNegativaException("A idade não pode ser negativa!");
            }
            System.out.println("Idade válida: " + idade);

            System.out.print("Digite um valor (até 1000): ");
            int valor = sc.nextInt();
            if (valor > 1000) {
                throw new ValorMuitoAltoException("Valor acima do limite permitido!");
            }
            System.out.println("Valor aceito: " + valor);

        } catch (NomeInvalidoException e) {
            System.out.println("Erro: " + e.getMessage());
        } catch (IdadeNegativaException e) {
            System.out.println("Erro: " + e.getMessage());
        } catch (ValorMuitoAltoException e) {
            System.out.println("Erro: " + e.getMessage());
        }

        sc.close();
    }
}
