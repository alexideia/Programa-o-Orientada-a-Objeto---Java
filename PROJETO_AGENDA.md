package agenda;

import java.util.Scanner;

public class Agenda {
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
                
                System.out.println("Escolha Uma Opcao:\n 1- Incluir\n 2- Pesquisar\n 3- Excluir\n 4- Sair ");
                opcao = ler.nextLine();
                
                switch (opcao) {
                    case "1":
                        
                        do{
                            System.out.println("Qual Nome:");
                            nome[posicao] = ler.nextLine();
                            
                            System.out.println("Qual Endereco:");
                            endereco [posicao] = ler.nextLine();
                            
                            System.out.println("Qual Telefone:");
                            telefone [posicao] = ler.nextLine();
                            
                            System.out.println("Qual Cep:");
                            cep [posicao] = ler.nextLine();
                            
                            System.out.println("Qual Idade:");
                            idade [posicao] = ler.nextLine();
                            
                            System.out.println("Cadastrar Usuario?");
                            continuar = ler.nextLine();
                            
                            posicao++;
                        }while(continuar.equals("Sim"));
                        
                        break;
                    
                    case "2":
                        
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
                        
                        System.out.println("Qual usuario excluir");
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
                        
                        System.out.println("Final.");
                        return;
                    
                    default:
                        
                        System.out.println("Opcao invalida.");
                        break;
                }
                
            }while (!opcao.equals("Sair"));
        }
}
