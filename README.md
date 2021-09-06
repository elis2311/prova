#include <stdio.h>
#include <stdlib.h>
#define j 12
/*Desenvolva um programa em C para ser utilizado pelo gerente de um Banco para o controle das contas de seus 12 clientes Premium.

 Ø  Ao acessar o programa, deverá ser apresentado na tela um Menu conforme modelo abaixo:



++++++++++++++++++++++++++++++++++++++++++++++++

                              BANCO CEFET



 1 – Cadastrar novo cliente

 2 – Consultar todos os clientes

 3 – Mostrar dados do cliente com menor saldo em conta corrente

 4 – Sair

Informe o número da opção desejada:



Ø  Observações:

 1.Os dados dos clientes deverão ser armazenados em um Vetor de Estrutura que deverá ter os seguintes campos:

a)      número da conta corrente;

b)      nome completo do cliente;

c)      saldo atual da conta corrente;

 2.A opção 3 do Menu (Mostrar dados do cliente com maior saldo em conta corrente) deverá ser feita em uma Função ou Procedure.*/


typedef struct{
int conta;
char nome[900];
float saldo;
 } cliente;
 void cadastrar(cliente cliente[], int posicao){
 fflush(stdin);
 printf("\n\n============================================================================");
 printf("\n\t CADASTRO DE NOVOS CLIENTES");
 printf("\n informe número da conta corrente");
 printf("\n informe o nome completo do cliente");
 printf("\n informe o saldo atual da conta corrente");
 scanf("%f", &cliente[posicao].saldo);
 system("pause");
 system("cls");
        }
void consulta(cliente cliente[]){
 int posicao,indice=-1;
    char nome[100];
    fflush(stdin);
    printf("\nINFORME O NOME PARA A CONSULTA: ");
    gets(nome);
    system("pause");
    system("cls");
    for(posicao=0;posicao<j;posicao++){
     if(strcmp(nome,cliente[posicao].nome)==0){
        indice=posicao;
        break;
      }
  }
  if(indice != -1){
    printf("------------------INFORMAÇÕES ENCONTRADAS------------------\n\nNOME: %s",cliente[posicao].nome);
    printf("\nINFORME O NÚMERO DA CONTA CORRENTE: %d\n\n",cliente[posicao].conta);
    printf("\nINFORME O SALDO ATUAL: %.2f\n\n",cliente[posicao].saldo);
    system("pause");
    system("cls");
}
  else{
    printf("\nCliente não encontrado\n\n");
     system("pause");
   system("cls");
   }
}
int main()
{
    cliente cli[j];
    int loop=1, opc, aux=0;
    while(loop){
        system("cls");
        printf("\n\n============================================================================");
        printf("\n\t MENU PRINCIPAL");
        printf("\n aperte 1 para cadastrar novo cliente");
        printf("\n aperte 2 para consutar todos os clientes");
        printf("\n aperte 3 para Mostrar dados do cliente com menor saldo em conta corrente");
        printf("\n aperte 4 para sair");
        printf("\n\n============================================================================");
        scanf("%d", &opc);
        switch(opc){
            case 1: cadastrar(cli, aux);
            aux++;
            break;
            case 2: consulta(cli);
            break;
            case 4: loop=0;
            break;
            default:
                printf("\n opcao invalida");
            }
        }
        printf("\n\n============================================================================");
        printf("\n AGRADECO POR ULTILIZAR NOSSO PROGRAMA");
        printf("\n\n============================================================================");
    return 0;
}
