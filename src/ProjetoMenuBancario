import java.util.ArrayList;
import java.util.InputMismatchException;
import java.util.Scanner;
public class ProjetoBancario {
    public static void main(String[] args) {
        ArrayList<String> lista = new ArrayList<>();
        String banco = "Banco Santander";
        String tipoConta = "Conta Corrente";
        double saldo = 15000.00;
        System.out.println("***************");
        System.out.println("\n" + banco);
        System.out.println(tipoConta);
        System.out.println("Saldo: R$ " + String.format("%.2f", saldo));
        System.out.println("\n***************");

        Scanner main = new Scanner(System.in);
        String nomeUsuario;
        System.out.print("Digite seu nome de usuario: ");
        nomeUsuario = main.nextLine();
        String senha;
        System.out.println("Digite sua senha: ");
        senha = main.nextLine();
        System.out.println("💰 Bem-vindo, " + nomeUsuario + "! 💰");

        int opcao = 0;
        while (opcao != 5) {
            System.out.println("""
                    Operações disponíveis:
                    1 - Consultar saldo
                    2 - Transferir valor
                    3 - Receber valor
                    4 - Extrato da conta
                    5 - Sair
                    """);

            System.out.print("Escolha uma opção: ");
            try {
                opcao = main.nextInt();
            } catch (InputMismatchException e) {
                System.out.println("Digite apenas numeros!");
                main.next();
                continue;
            }

            switch (opcao) {
                case 1:
                    System.out.println("Seu saldo é: R$ "+ String.format("%.2f",saldo));
                    break;
                case 2:
                    try {
                        System.out.println("Digite o valor a ser transferido");
                        double valorTransferencia = main.nextDouble();
                        if (valorTransferencia <= 0) {
                            System.out.println("Digite um valor positivo!");
                            break;
                        }
                        if (valorTransferencia > saldo) {
                            System.out.println("Saldo insuficiente para a transferencia!");
                        } else {
                            saldo -= valorTransferencia;
                            System.out.println("Transferencia de R$ " + String.format("%.2f", valorTransferencia) + " realizada com sucesso!");
                            System.out.println("Seu novo saldo é: R$ " + String.format("%.2f",saldo));
                            lista.add("Transferencia de R$ " + String.format("%.2f",valorTransferencia));
                        }

                    } catch (InputMismatchException e) {
                        System.out.println("Digite apenas numeros!");
                        main.next();
                    }
                    break;
                case 3:
                    try {
                        System.out.println("Digite o valor a ser depositado");
                        double valorRecebido = main.nextDouble();
                        if (valorRecebido <= 0) {
                            System.out.println("Digite um valor positivo!");
                            break;
                        }
                        saldo += valorRecebido;
                        System.out.println("Deposito de R$ " + String.format("%.2f", valorRecebido) + " realizado com sucesso!");
                        System.out.println("Seu novo saldo é: R$ " + String.format("%.2f",saldo));
                        lista.add("Deposito de R$ " + String.format("%.2f", valorRecebido));
                    } catch (InputMismatchException e) {
                        System.out.println("Digite apenas numeros!");
                        main.next();
                    }
                    break;
                case 4:
                    if (lista.isEmpty()) {
                        System.out.println("Nenhuma operação realizada ainda.");
                    } else {
                        for (int i =0; i < lista.size(); i++){
                            System.out.println("Extrato: " + lista.get(i));}
                    }
                    break;
                case 5:
                    System.out.println("Encerrar");
                    break;
                default:
                    System.out.println("Opção inválida. Tente novamente.");
                    break;}
        }
        main.close();
    }
}

