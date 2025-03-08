#include <stdio.h>
int main () {
//variáveis mercadinho
  int item[3], removeitem, itemremovido;
  float valoritem[3], valorleite = 3.50, valoragua = 2.50, valorpao = 0.50, valorqueijo = 69.99, totalcompra;
  int continuar[2];
//variáveis banquinho
  char nome;
  int senha, senhac, senhap, tela[5], dia, mes, ano, cpf, cpfc, sair, pagar;
  float saldo = 100, saque, sacado, depositado, deposito, pagamento;

//boas vindas e login ou cadastro. (BANQUINHO)
        printf("*****************************************\n");
        printf("Bem Vindo ao Banquinhöœwn Virtual!!\n");
        printf("(1) Login\n(2) Cadastro\n");
        printf("-----------------------------------------\n");
        scanf("%d", &tela[1]);
        printf("-----------------------------------------\n");
//opção cadastro. (BANQUINHO)
            if (tela[1] == 2) {
                printf("Informe seu Nome:\n");
                scanf("%s", &nome);
                printf("-----------------------------------------\n");
                printf("Informe sua data de nascimento(xx/xx/xxxx):\n");
                scanf("%d %d %d", &dia, &mes, &ano);
                printf("-----------------------------------------\n");
                printf("Informe seu CPF:\n");
                scanf("%d", &cpfc);
                printf("-----------------------------------------\n");
                printf("Informe a Senha que será usada:\n");
                scanf("%d", &senhac);
            }

//tela inicial (MERCADINHO)
    printf("informe abaixo o que você deseja comprar, conforme os números: \n");
    printf("(1) leite: R$3.50 \n");
    printf("(2) água: R$2.50 \n");
    printf("(3) pão: R$0.50 \n");
    printf("(4) queijo: R$69.99 \n");
  printf("*************************************\n");
    printf("digite o primeiro item: \n");
    scanf("%d", &item[0]);
  printf("*************************************\n");

//questionamento compra (MERCADINHO)
    if (item[0] == 1) {
      printf("o leite foi adicionado ao seu carrinho:\n");
      valoritem[0] = valorleite;
    }
    else if (item[0] == 2) {
      printf("a água foi adicionada ao seu carrinho:\n");
      valoritem[0] = valoragua;
    }
    else if (item[0] == 3) {
      printf("o pão foi adicionado ao seu carrinho:\n");
      valoritem[0] = valorpao;
    }
    else if (item[0] == 4) {
      printf("o queijo foi adicionado ao seu carrinho:\n");
      valoritem[0] = valorqueijo;
    }
    else {
      printf("o item não foi encontrado:\n");
    }
  
//opção remoção item (MERCADINHO)
  printf("*************************************\n");
                          do {
                          printf("deseja remover algum item? Se sim digite seu respectivo número (1,2,3,4) se não digite (0)\n");
                          scanf("%d", &itemremovido);
                            if (itemremovido == 1) {
                              printf("o leite foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 3.50;
                            }
                            if (itemremovido == 2) {
                              printf("a água foi removida do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 2.50;
                            }
                            if (itemremovido == 3) {
                              printf("o pão foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 0.50;
                            }
                            if (itemremovido == 4) {
                              printf("o queijo foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 69.99;
                            }
                          }
                          while (itemremovido !=0);

//questionamento compra (1) (MERCADINHO)
    printf("você deseja comprar outro item? Se sim digite (1) se não digite (0)\n");
    scanf("%d", &continuar[0]);
    if (continuar[0] == 1) {
  printf("*************************************\n");
    printf("(1) leite: R$3.50 \n");
    printf("(2) água: R$2.50 \n");
    printf("(3) pão: R$0.50 \n");
    printf("(4) queijo: R$69.99 \n");
      printf("digite o segundo item: \n");
      scanf("%d", &item[1]);
      if (item[1] == 1) {
        printf("o leite foi adicionado ao seu carrinho:\n");
        valoritem[1] = valorleite;
      }
      else if (item[1] == 2) {
        printf("a água foi adicionada ao seu carrinho:\n");
        valoritem[1] = valoragua;
      }
      else if (item[1] == 3) {
        printf("o pão foi adicionado ao seu carrinho:\n");
        valoritem[1] = valorpao;
      }
      else if (item[1] == 4) {
        printf("o queijo foi adicionado ao seu carrinho:\n");
        valoritem[1] = valorqueijo;
      }
      else {
        printf("o item não foi encontrado:\n");
      }
    }
    else if (continuar[0] == 0) {
      totalcompra = valoritem[0];
      printf("*************************************\n");
    printf("o valor total da sua compra é de R$%.2f\n, deseja fazer o pagamento? se sim (1), se não (0).", totalcompra);
      scanf("%d", &pagar);
      if (pagar == 1) {
      //tela login pós-cadastro. (BANQUINHO)
                printf("\n");
                printf("*****************************************\n");
                printf("\n");
                printf("ACESSE SUA CONTA BANCÁRIA:\n");
                printf("\n");
                printf("Informe seu CPF:\n");
                scanf("%d", &cpf);
                printf("-----------------------------------------\n");
                printf("Informe sua Senha:\n");
                scanf("%d", &senha);
                printf("*****************************************\n");
                    if (cpf == cpfc && senha == senhac) {
                        do {
                                printf("MENU do Banquinhöœwn:\n");
                                printf("\n");
                                printf("(1) Saldo.\n(2) Sacar.\n(3) Depositar.\n(4) Extrato.\n(5) Transferir.\n(6) Sair.\n");
                                printf("-----------------------------------------\n");
                                scanf("%d", &tela[0]);
                                printf("*****************************************\n");
                                    if (tela[0] == 1) {
                                        printf("Saldo atual: R$%.2f\n", saldo);
                                        printf("*****************************************\n");
                                    }
                                    else if (tela[0] == 2) {
                                        printf("Informe o valor do saque:\n");
                                        scanf("%f", &saque);
                                          if (saque <= saldo) {
                                            saldo = saldo - saque;
                                            sacado = sacado + saque;
                                            printf("-----------------------------------------\n");
                                          printf("Saque de R$%.2f confirmado.\n", saque);
                                          printf("\n");
                                          }
                                          else if (saque > saldo) {
                                            printf("Você não tem R$%f na sua conta para sacar.\n", saque);
                                          }
                                        printf("*****************************************\n");
                                    }
                                    else if (tela[0] == 3) {
                                        printf("Informe o valor do deposito:\n");
                                        scanf("%f", &deposito);
                                          if (deposito <= sacado) {
                                            sacado = sacado - deposito;
                                            saldo = saldo + deposito;
                                            printf("-----------------------------------------\n");
                                            printf("Deposito de R$%.2f confirmado.\n", deposito);
                                            printf("\n");
                                          }
                                          else if ( deposito > sacado) {
                                            printf("Você não tem R$%f para depositar.", deposito);
                                          }
                                        printf("*****************************************\n");
                                    }
                                    else if (tela[0] == 4) {
                                        printf("Aqui está o extrato da sua conta:\n");
                                        printf("Em processo\n");
                                    }
                                    else if (tela[0] == 5) {
                                        printf("Digite sua senha:\n");
                                        scanf("%f", &senhap);
                                          if (senha == senhac) {
                                            if (sacado >= totalcompra) {
                                            sacado = sacado - totalcompra;
                                            printf("-----------------------------------------\n");
                                            printf("Pagamento de R$%.2f confirmado.\n", totalcompra);
                                            printf("\n");
                                            }
                                            else if (sacado < totalcompra) {
                                              ("Você não tem o dinheiro suficiente para realizar o pagamento.");
                                            }
                                        }
                                        printf("*****************************************\n");
                                    }
                            }
                            while (tela[0] != 6);
                                    printf("\n");
                                    printf("*****************************************\n");
                    }
                    else if (cpf == cpfc && senha != senhac){
                        printf("Senha não encontrada!\n");
                    }
                    else if (cpf != cpfc && senha == senhac) {
                        printf("CPF não encontrado!\n");
                    }
      return;
    }
    else if (pagar != 1) {
      printf("Ok, sua compra foi cancelada, até mais!");
    }
    }
//opção remoção item (1) MERCADINHO
  printf("*************************************\n");
                          do {
                          printf("deseja remover algum item? Se sim digite seu respectivo número (1,2,3,4) se não digite (0)\n");
                          scanf("%d", &itemremovido);
                            if (itemremovido == 1) {
                              printf("o leite foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 3.50;
                            }
                            if (itemremovido == 2) {
                              printf("a água foi removida do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 2.50;
                            }
                            if (itemremovido == 3) {
                              printf("o pão foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 0.50;
                            }
                            if (itemremovido == 4) {
                              printf("o queijo foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 69.99;
                            }
                          }
                          while (itemremovido !=0);

//questionamento compra (2) (MERCADINHO)
    printf("você deseja comprar outro item? Se sim digite (1) se não digite (0)\n");
    scanf("%d", &continuar[1]);
    if (continuar[1] == 1) {
  printf("*************************************\n");
    printf("(1) leite: R$3.50 \n");
    printf("(2) água: R$2.50 \n");
    printf("(3) pão: R$0.50 \n");
    printf("(4) queijo: R$69.99 \n");
      printf("digite o terceiro item: \n");
      scanf("%d", &item[2]);
      if (item[2] == 1) {
        printf("o leite foi adicionado ao seu carrinho:\n");
        valoritem[2] = valorleite;
      }
      else if (item[2] == 2) {
        printf("a água foi adicionada ao seu carrinho:\n");
        valoritem[2] = valoragua;
      }
      else if (item[2] == 3) {
        printf("o pão foi adicionado ao seu carrinho:\n");
        valoritem[2] = valorpao;
      }
      else if (item[2] == 4) {
        printf("o queijo foi adicionado ao seu carrinho:\n");
        valoritem[2] = valorqueijo;
      }
      else {
        printf("*************************************\n");
        printf("o item não foi encontrado:\n");
      }
    }
  else if (continuar[1] == 0) {
    totalcompra = valoritem[0] + valoritem[1];
    printf("*************************************\n");
    printf("o valor total da sua compra é de R$%.2f\n, deseja fazer o pagamento? se sim (1), se não (0).", totalcompra);
      scanf("%d", &pagar);
      if (pagar == 1) {
      //tela login pós-cadastro. (BANQUINHO)
      printf("\n");
      printf("*****************************************\n");
      printf("\n");
      printf("ACESSE SUA CONTA BANCÁRIA:\n");
      printf("\n");
      printf("Informe seu CPF:\n");
      scanf("%d", &cpf);
      printf("-----------------------------------------\n");
      printf("Informe sua Senha:\n");
      scanf("%d", &senha);
      printf("*****************************************\n");
          if (cpf == cpfc && senha == senhac) {
              do {
                      printf("MENU do Banquinhöœwn:\n");
                      printf("\n");
                      printf("(1) Saldo.\n(2) Sacar.\n(3) Depositar.\n(4) Extrato.\n(5) Transferir.\n(6) Sair.\n");
                      printf("-----------------------------------------\n");
                      scanf("%d", &tela[0]);
                      printf("*****************************************\n");
                          if (tela[0] == 1) {
                              printf("Saldo atual: R$%.2f\n", saldo);
                              printf("*****************************************\n");
                          }
                          else if (tela[0] == 2) {
                              printf("Informe o valor do saque:\n");
                              scanf("%f", &saque);
                                if (saque <= saldo) {
                                  saldo = saldo - saque;
                                  sacado = sacado + saque;
                                  printf("-----------------------------------------\n");
                                printf("Saque de R$%.2f confirmado.\n", saque);
                                printf("\n");
                                }
                                else if (saque > saldo) {
                                  printf("Você não tem R$%f na sua conta para sacar.\n", saque);
                                }
                              printf("*****************************************\n");
                          }
                          else if (tela[0] == 3) {
                              printf("Informe o valor do deposito:\n");
                              scanf("%f", &deposito);
                                if (deposito <= sacado) {
                                  sacado = sacado - deposito;
                                  saldo = saldo + deposito;
                                  printf("-----------------------------------------\n");
                                  printf("Deposito de R$%.2f confirmado.\n", deposito);
                                  printf("\n");
                                }
                                else if ( deposito > sacado) {
                                  printf("Você não tem R$%f para depositar.", deposito);
                                }
                              printf("*****************************************\n");
                          }
                          else if (tela[0] == 4) {
                              printf("Aqui está o extrato da sua conta:\n");
                              printf("Em processo\n");
                          }
                          else if (tela[0] == 5) {
                              printf("Digite sua senha:\n");
                              scanf("%f", &senhap);
                                if (senha == senhac) {
                                  if (sacado >= totalcompra) {
                                  sacado = sacado - totalcompra;
                                  printf("-----------------------------------------\n");
                                  printf("Pagamento de R$%.2f confirmado.\n", totalcompra);
                                  printf("\n");
                                  }
                                  else if (sacado < totalcompra) {
                                    ("Você não tem o dinheiro suficiente para realizar o pagamento.");
                                  }
                              }
                              printf("*****************************************\n");
                          }
                  }
                  while (tela[0] != 6);
                          printf("\n");
                          printf("*****************************************\n");
          }
          else if (cpf == cpfc && senha != senhac){
              printf("Senha não encontrada!\n");
          }
          else if (cpf != cpfc && senha == senhac) {
              printf("CPF não encontrado!\n");
          }
return;
  }
  }

  printf("*************************************\n");
  //opção remoção item (2) (MERCADINHO)
                          do {
                          printf("deseja remover algum item? Se sim digite seu respectivo número (1,2,3,4) se não digite (0)\n");
                          scanf("%d", &itemremovido);
                            if (itemremovido == 1) {
                              printf("o leite foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 3.50;
                            }
                            if (itemremovido == 2) {
                              printf("a água foi removida do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 2.50;
                            }
                            if (itemremovido == 3) {
                              printf("o pão foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 0.50;
                            }
                            if (itemremovido == 4) {
                              printf("o queijo foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 69.99;
                            }
                          }
                          while (itemremovido !=0);

  //questionamento compra (3) (MERCADINHO)
    printf("você deseja comprar outro item? Se sim digite (1) se não digite (0)\n");
    scanf("%d", &continuar[2]);
    if (continuar[2] == 1) {
  printf("*************************************\n");
    printf("(1) leite: R$3.50 \n");
    printf("(2) água: R$2.50 \n");
    printf("(3) pão: R$0.50 \n");
    printf("(4) queijo: R$69.99 \n");
      printf("digite o quarto item: \n");
      scanf("%d", &item[3]);
      if (item[3] == 1) {
        printf("o leite foi adicionado ao seu carrinho:\n");
        valoritem[3] = valorleite;
        printf("*************************************\n");
        totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3];
      }
      else if (item[3] == 2) {
        printf("a água foi adicionada ao seu carrinho:\n");
        valoritem[3] = valoragua;
        printf("*************************************\n");
        totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3];
      }
      else if (item[3] == 3) {
        printf("o pão foi adicionado ao seu carrinho:\n");
        valoritem[3] = valorpao;
        printf("*************************************\n");
        totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3];
      }
      else if (item[3] == 4) {
        printf("o queijo foi adicionado ao seu carrinho:\n");
        valoritem[3] = valorqueijo;
        printf("*************************************\n");
        totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3];
      }
      else {
        printf("*************************************\n");
        printf("o item não foi encontrado:\n");
        printf("*************************************\n");
        totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3];
      }
    }
  else if (continuar[2] == 0) {
    totalcompra = valoritem[0] + valoritem[1] + valoritem[2];
    printf("*************************************\n");
    printf("o valor total da sua compra é de R$%.2f\n, deseja fazer o pagamento? se sim (1), se não (0).", totalcompra);
      scanf("%d", &pagar);
      if (pagar == 1) {
      //tela login pós-cadastro. (BANQUINHO)
      printf("\n");
      printf("*****************************************\n");
      printf("\n");
      printf("ACESSE SUA CONTA BANCÁRIA:\n");
      printf("\n");
      printf("Informe seu CPF:\n");
      scanf("%d", &cpf);
      printf("-----------------------------------------\n");
      printf("Informe sua Senha:\n");
      scanf("%d", &senha);
      printf("*****************************************\n");
          if (cpf == cpfc && senha == senhac) {
              do {
                      printf("MENU do Banquinhöœwn:\n");
                      printf("\n");
                      printf("(1) Saldo.\n(2) Sacar.\n(3) Depositar.\n(4) Extrato.\n(5) Transferir.\n(6) Sair.\n");
                      printf("-----------------------------------------\n");
                      scanf("%d", &tela[0]);
                      printf("*****************************************\n");
                          if (tela[0] == 1) {
                              printf("Saldo atual: R$%.2f\n", saldo);
                              printf("*****************************************\n");
                          }
                          else if (tela[0] == 2) {
                              printf("Informe o valor do saque:\n");
                              scanf("%f", &saque);
                                if (saque <= saldo) {
                                  saldo = saldo - saque;
                                  sacado = sacado + saque;
                                  printf("-----------------------------------------\n");
                                printf("Saque de R$%.2f confirmado.\n", saque);
                                printf("\n");
                                }
                                else if (saque > saldo) {
                                  printf("Você não tem R$%f na sua conta para sacar.\n", saque);
                                }
                              printf("*****************************************\n");
                          }
                          else if (tela[0] == 3) {
                              printf("Informe o valor do deposito:\n");
                              scanf("%f", &deposito);
                                if (deposito <= sacado) {
                                  sacado = sacado - deposito;
                                  saldo = saldo + deposito;
                                  printf("-----------------------------------------\n");
                                  printf("Deposito de R$%.2f confirmado.\n", deposito);
                                  printf("\n");
                                }
                                else if ( deposito > sacado) {
                                  printf("Você não tem R$%f para depositar.", deposito);
                                }
                              printf("*****************************************\n");
                          }
                          else if (tela[0] == 4) {
                              printf("Aqui está o extrato da sua conta:\n");
                              printf("Em processo\n");
                          }
                          else if (tela[0] == 5) {
                              printf("Digite sua senha:\n");
                              scanf("%f", &senhap);
                                if (senha == senhac) {
                                  if (sacado >= totalcompra) {
                                  sacado = sacado - totalcompra;
                                  printf("-----------------------------------------\n");
                                  printf("Pagamento de R$%.2f confirmado.\n", totalcompra);
                                  printf("\n");
                                  }
                                  else if (sacado < totalcompra) {
                                    ("Você não tem o dinheiro suficiente para realizar o pagamento.");
                                  }
                              }
                              printf("*****************************************\n");
                          }
                  }
                  while (tela[0] != 6);
                          printf("\n");
                          printf("*****************************************\n");
          }
          else if (cpf == cpfc && senha != senhac){
              printf("Senha não encontrada!\n");
          }
          else if (cpf != cpfc && senha == senhac) {
              printf("CPF não encontrado!\n");
          }
return;
  }
  }
    
                        do {
                          printf("deseja remover algum item? Se sim digite seu respectivo número (1,2,3,4) se não digite (0)\n");
                          scanf("%d", &itemremovido);
                            if (itemremovido == 1) {
                              printf("o leite foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 3.50;
                            }
                            if (itemremovido == 2) {
                              printf("a água foi removida do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 2.50;
                            }
                            if (itemremovido == 3) {
                              printf("o pão foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 0.50;
                            }
                            if (itemremovido == 4) {
                              printf("o queijo foi removido do seu carrinho:\n");
                              totalcompra = valoritem[0] + valoritem[1] + valoritem[2] + valoritem[3] - 69.99;
                            }
                          }
                          while (itemremovido !=0);
                          

//tela login pós-cadastro. (BANQUINHO)
printf("\n");
printf("*****************************************\n");
printf("\n");
printf("ACESSE SUA CONTA BANCÁRIA:\n");
printf("\n");
printf("Informe seu CPF:\n");
scanf("%d", &cpf);
printf("-----------------------------------------\n");
printf("Informe sua Senha:\n");
scanf("%d", &senha);
printf("*****************************************\n");
    if (cpf == cpfc && senha == senhac) {
        do {
                printf("MENU do Banquinhöœwn:\n");
                printf("\n");
                printf("(1) Saldo.\n(2) Sacar.\n(3) Depositar.\n(4) Extrato.\n(5) Transferir.\n(6) Sair.\n");
                printf("-----------------------------------------\n");
                scanf("%d", &tela[0]);
                printf("*****************************************\n");
                    if (tela[0] == 1) {
                        printf("Saldo atual: R$%.2f\n", saldo);
                        printf("*****************************************\n");
                    }
                    else if (tela[0] == 2) {
                        printf("Informe o valor do saque:\n");
                        scanf("%f", &saque);
                          if (saque <= saldo) {
                            saldo = saldo - saque;
                            sacado = sacado + saque;
                            printf("-----------------------------------------\n");
                          printf("Saque de R$%.2f confirmado.\n", saque);
                          printf("\n");
                          }
                          else if (saque > saldo) {
                            printf("Você não tem R$%f na sua conta para sacar.\n", saque);
                          }
                        printf("*****************************************\n");
                    }
                    else if (tela[0] == 3) {
                        printf("Informe o valor do deposito:\n");
                        scanf("%f", &deposito);
                          if (deposito <= sacado) {
                            sacado = sacado - deposito;
                            saldo = saldo + deposito;
                            printf("-----------------------------------------\n");
                            printf("Deposito de R$%.2f confirmado.\n", deposito);
                            printf("\n");
                          }
                          else if ( deposito > sacado) {
                            printf("Você não tem R$%f para depositar.", deposito);
                          }
                        printf("*****************************************\n");
                    }
                    else if (tela[0] == 4) {
                        printf("Aqui está o extrato da sua conta:\n");
                        printf("Em processo\n");
                    }
                    else if (tela[0] == 5) {
                        printf("Digite sua senha:\n");
                        scanf("%f", &senhap);
                          if (senha == senhac) {
                            if (sacado >= totalcompra) {
                            sacado = sacado - totalcompra;
                            printf("-----------------------------------------\n");
                            printf("Pagamento de R$%.2f confirmado.\n", totalcompra);
                            printf("\n");
                            }
                            else if (sacado < totalcompra) {
                              ("Você não tem o dinheiro suficiente para realizar o pagamento.");
                            }
                        }
                        printf("*****************************************\n");
                    }
            }
            while (tela[0] != 6);
                    printf("\n");
                    printf("*****************************************\n");
    }
    else if (cpf == cpfc && senha != senhac){
        printf("Senha não encontrada!\n");
    }
    else if (cpf != cpfc && senha == senhac) {
        printf("CPF não encontrado!\n");
    }
return;
}

