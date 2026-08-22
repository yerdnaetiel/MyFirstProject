import java.util.Scanner;

public class App {
    public static void main(String[] args) throws Exception {

        Scanner teclado = new Scanner(System.in);
        double saldo = 1000;        
        int opcao = 0;

        System.out.println("==== LOGIN ==== ");
        System.out.println(" USUÁRIO: ");
        String usuario = teclado.next();
        System.out.println("PASSWORD:");
        int password = teclado.nextInt();

    
       if (usuario.equals("admin") && password == 1234) {
         System.out.println(" LOGIN REALIZADO ! ");

        while (opcao != 4) {
            System.out.println("==== MENU ====");
            System.out.println("1 - CONSULTAR SALDO");
            System.out.println("2 - DEPOSITAR");
            System.out.println("3 - SACAR");
            System.out.println("4 - SAIR");
            
            opcao = teclado.nextInt();

         switch (opcao) {
            case 1:
                System.out.println("SEU SALDO É : " + saldo);
                break;

            case 2:
                System.out.println("QUANTO DESEJA DEPOSITAR?");
                int deposito = teclado.nextInt();
                saldo = deposito + saldo;
                break;

            case 3:
                System.out.println("QUAL O VALOR DO SAQUE?");
                int saque = teclado.nextInt();
                if(saque <= saldo){
                    System.out.println("SAQUE AUTORIZADO ! ");
                    saldo = saldo - saque;
                 }
                else{
                    System.out.println("TRANSAÇÃO NÃO AUTORIZADA POR FALTA DE SALDO !");
                }
                break;
            
            case 4:
                System.out.println("ATÉ LOGO!!");    

                break;
            default:
                System.out.println("COMANDO INVALIDO !!");
                break;
         }
       } 

       }
       else{
        System.out.println(" ACESSO NEGADO ! ");
       }

        teclado.close();
        }
    }
