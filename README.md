# Simulando-Uma-Conta-Banc-ria-Atrav-s-Do-Terminal-Console

Vou começar esse desafio, com um exemplo de código Java que simula uma conta bancária simples. Podemos usar este código como ponto de partida e expandi-lo conforme necessário para o desafio em questão.

```java
import java.util.Scanner;

public class ContaBancaria {
    private double saldo;

    public ContaBancaria(double saldoInicial) {
        this.saldo = saldoInicial;
    }

    public void depositar(double valor) {
        if (valor > 0) {
            saldo += valor;
            System.out.println("Depósito realizado com sucesso!");
        } else {
            System.out.println("Valor de depósito inválido.");
        }
    }

    public void sacar(double valor) {
        if (valor > 0 && valor <= saldo) {
            saldo -= valor;
            System.out.println("Saque realizado com sucesso!");
        } else {
            System.out.println("Valor de saque inválido ou saldo insuficiente.");
        }
    }

    public void consultarSaldo() {
        System.out.println("Saldo atual: R$" + saldo);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        ContaBancaria conta = new ContaBancaria(0); // Inicia com saldo zero

        System.out.println("Bem-vindo ao seu banco virtual!");
        System.out.println("Escolha uma opção:");
        System.out.println("1 - Depositar");
        System.out.println("2 - Sacar");
        System.out.println("3 - Consultar Saldo");
        System.out.println("0 - Sair");

        int opcao;
        do {
            System.out.print("Opção: ");
            opcao = sc.nextInt();
            switch (opcao) {
                case 1:
                    System.out.print("Valor para depósito: R$");
                    double valorDeposito = sc.nextDouble();
                    conta.depositar(valorDeposito);
                    break;
                case 2:
                    System.out.print("Valor para saque: R$");
                    double valorSaque = sc.nextDouble();
                    conta.sacar(valorSaque);
                    break;
                case 3:
                    conta.consultarSaldo();
                    break;
                case 0:
                    System.out.println("Obrigado por usar o banco virtual.");
                    break;
                default:
                    System.out.println("Opção inválida.");
            }
        } while (opcao != 0);

        sc.close();
    }
}
```

Este código cria uma classe `ContaBancaria` com métodos para depositar, sacar e consultar o saldo. O método `main` oferece um menu simples para interagir com a conta através do terminal/console.

Para compilar e executar o código Java que você tem, você precisará seguir alguns passos simples. Aqui está um guia passo a passo:

1. **Salvar o código**: Primeiro, salve o código em um arquivo com a extensão `.java`. O nome do arquivo deve ser exatamente o mesmo que o nome da classe pública. Por exemplo, se a sua classe pública é `ContaBancaria`, o arquivo deve ser chamado `ContaBancaria.java`.

2. **Compilar o código**:
   - Abra o terminal ou prompt de comando no seu computador.
   - Navegue até o diretório onde o arquivo `ContaBancaria.java` está salvo.
   - Digite o seguinte comando para compilar o arquivo:
     ```shell
     javac ContaBancaria.java
     ```
   - Se não houver erros, esse comando criará um arquivo `ContaBancaria.class`, que é o bytecode Java.

3. **Executar o programa**:
   - Após a compilação bem-sucedida, você executará o programa com o comando:
     ```shell
     java ContaBancaria
     ```
   - Isso iniciará o programa e você poderá interagir com ele através do terminal.

Lembre-se de que você precisa ter o **JDK (Java Development Kit)** instalado no seu computador para compilar e executar programas Java. Se você encontrar algum erro durante a compilação, verifique se o código está correto e se todos os comandos foram digitados corretamente.

https://docs.google.com/presentation/d/1kt8Qcrkcv0S0aph4vNcDHeo8G2ek6uyQ/edit?usp=sharing&ouid=105300330738120646134&rtpof=true&sd=true

https://github.com/digitalinnovationone/trilha-java-basico/tree/main/desafios/sintaxe
