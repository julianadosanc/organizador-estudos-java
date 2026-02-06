import java.util.ArrayList;
import java.util.Scanner;

public class OrganizadorEstudos {

    static ArrayList<String> materias = new ArrayList<>();
    static ArrayList<Integer> horas = new ArrayList<>();

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int opcao;

        do {
            System.out.println("\n📚 ORGANIZADOR DE ESTUDOS");
            System.out.println("1 - Cadastrar matéria");
            System.out.println("2 - Listar matérias");
            System.out.println("3 - Registrar horas de estudo");
            System.out.println("0 - Sair");
            System.out.print("Escolha uma opção: ");
            opcao = scanner.nextInt();
            scanner.nextLine();

            switch (opcao) {
                case 1:
                    System.out.print("Nome da matéria: ");
                    String materia = scanner.nextLine();
                    materias.add(materia);
                    horas.add(0);
                    System.out.println("Matéria cadastrada!");
                    break;

                case 2:
                    System.out.println("\n📋 Matérias cadastradas:");
                    for (int i = 0; i < materias.size(); i++) {
                        System.out.println(materias.get(i) + " - " + horas.get(i) + "h");
                    }
                    break;

                case 3:
                    System.out.print("Informe o número da matéria: ");
                    int index = scanner.nextInt();
                    System.out.print("Horas estudadas: ");
                    int h = scanner.nextInt();
                    horas.set(index, horas.get(index) + h);
                    System.out.println("Horas registradas!");
                    break;

                case 0:
                    System.out.println("Encerrando...");
                    break;

                default:
                    System.out.println("Opção inválida.");
            }
        } while (opcao != 0);

        scanner.close();
    }
}
