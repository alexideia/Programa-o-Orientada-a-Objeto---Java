package aplicacJdbAgenda;

import java.util.Scanner;


public class AplicacJdbAgenda {
  
        public static void main (String[] args){
            
            String [] nome = new String [20];
            String [] endereco = new String [20];
            String [] telefone = new String [20];
            String [] cep = new String [20];
            String [] idade = new String [20];
            
            for (int i = 0; i < 20; i++) {
                nome[i] = "";
                endereco[i] = "";
                telefone [i] = "";
                cep [i] = "";
                idade[i] = "";
                
            }
            
            
            String opcao = "";
            String continuar = "";
            int posicao = 0;
            String excluirNome = "";
            
            Scanner ler = new Scanner (System.in);
                 
            do{
                
                System.out.println("Escolha o numero da opcao desejada:\n 1- Incluir\n 2- Listar\n 3- Excluir\n 4- Sair ");
                opcao = ler.nextLine();
                
                switch (opcao) {
                    case "1":
                        //Codigo de insercao
                        do{
                            System.out.println("Digite o nome:");
                            nome[posicao] = ler.nextLine();
                            
                            System.out.println("Digite o endereco:");
                            endereco [posicao] = ler.nextLine();
                            
                            System.out.println("Digite o telefone:");
                            telefone [posicao] = ler.nextLine();
                            
                            System.out.println("Digite o cep:");
                            cep [posicao] = ler.nextLine();
                            
                            System.out.println("Digite a idade:");
                            idade [posicao] = ler.nextLine();
                            
                            System.out.println("Deseja cadastrar um novo usuario?");
                            continuar = ler.nextLine();
                            
                            posicao++;
                        }while(continuar.equals("Sim"));
                        
                        break;
                    
                    case "2":
                        //Codigo de listar
                        for (int i = 0; i < 19; i++) {
                            
                            if(!nome[i].equals("")){
                                
                                System.out.println(
                                    "Nome: " + nome[i] + " \n" +
                                    "Endereco: " + endereco [i] + " \n" +
                                    "Telefone: " + telefone[i] + " \n" +
                                    "cep: " + cep [i] + " \n" + 
                                    "idade: " + idade[i] + " \n");
                                
                            }    
                        }
                        break;
                        
                    case "3":
                        //Codigo  exluclusao
                        
                        System.out.println("Qual usuario deseja excluir?");
                        excluirNome = ler.nextLine();
                        
                        for (int i = 0; i < 20; i++) {
                           if(nome[i].equals(excluirNome)){
                               nome[i] = "";
                               endereco[i] = "";
                               telefone[i] = "";
                               cep[i] = "";
                               idade[i] = "";
                           }
                            
                        }
                        break;
                        
                    case "4":
                        //Codigo para sair
                        System.out.println("Finalizado.");
                        return;
                    
                    default:
                        //Invalido
                        System.out.println("Opcao invalida!Tente novamente.");
                        break;
                } 
            }while (!opcao.equals("Sair"));
        }
}
