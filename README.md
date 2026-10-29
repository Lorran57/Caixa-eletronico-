# Caixa-eletronico-
Caixa eletronico que valida se o valor solicitado pelo usuário é permitido (ou seja, se é múltiplo de 5 e se não excede o saldo disponível de 430) e, em seguida, calcula a quantidade exata de cada nota (100, 50, 20, 10 e 5) necessária para entregar o dinheiro usando o menor número de cédulas possível.


#include <stdio.h>



int main()

{



    int saldo = 430;

    int valor_saque;



    printf("Digite o valor do saque: "); // Escreve na tela

    scanf(" %d", &valor_saque); // Lê o que você digitou e guarda na caixinha "valor_saque" / O espaço em branco limpa o buffer da memória e impede bugs.



    // "valor_saque % 5 == 0" verifica se o resto da divisão por 5 é zero (múltiplo de 5).

    // "valor_saque <= saldo" verifica se o saque não ultrapassa o saldo.

    if (valor_saque % 5 == 0 && valor_saque <= saldo) {





        int notas100 = valor_saque / 100; // Calcula as notas

        valor_saque = valor_saque % 100;  // Atualiza o valor do saque apenas com o que sobrou



        int notas50 = valor_saque / 50;

        valor_saque = valor_saque % 50;



        int notas20 = valor_saque / 20;

        valor_saque = valor_saque % 20;



        int notas10 = valor_saque / 10;

        valor_saque = valor_saque % 10;



        int notas5 = valor_saque / 5;

     



        printf("\nNotas entregues:\n");

        // Os "ifs" abaixo garantem que o programa só imprima as notas que foram utilizadas.

        if (notas100 > 0) printf("%d nota(s) de 100\n", notas100);

        if (notas50 > 0)  printf("%d nota(s) de 50\n", notas50);

        if (notas20 > 0)  printf("%d nota(s) de 20\n", notas20);

        if (notas10 > 0)  printf("%d nota(s) de 10\n", notas10);

        if (notas5 > 0)   printf("%d nota(s) de 5\n", notas5);



    }

        else {

        printf("\nErro: Saque invalido. O valor deve ser multiplo de 5 e nao ultrapassar o seu saldo de %d.\n", saldo);
    }
    return 0;
}
