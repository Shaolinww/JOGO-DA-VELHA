#include <stdio.h>
#include <stdlib.h>

void imprimir_tabuleiro(char tabuleiro[3][3]) {
    printf(" %c | %c | %c\n", tabuleiro[0][0], tabuleiro[0][1], tabuleiro[0][2]);
    printf(" %c | %c | %c\n", tabuleiro[1][0], tabuleiro[1][1], tabuleiro[1][2]);
    printf(" %c | %c | %c\n", tabuleiro[2][0], tabuleiro[2][1], tabuleiro[2][2]);
}

int VerificarVitoriaX(char tabuleiro[3][3], char jogador) {
    for (int i = 0; i < 3; i++) {
        if (tabuleiro[i][0] == jogador && tabuleiro[i][1] == jogador && tabuleiro[i][2] == jogador) {
            return 1;
        }
        if (tabuleiro[0][i] == jogador && tabuleiro[1][i] == jogador && tabuleiro[2][i] == jogador) {
            return 1;
        }
    }

    if (tabuleiro[0][0] == jogador && tabuleiro[1][1] == jogador && tabuleiro[2][2] == jogador) {
        return 1;
    }
    if (tabuleiro[0][2] == jogador && tabuleiro[1][1] == jogador && tabuleiro[2][0] == jogador) {
        return 1;
    }

    return 0;
}

int main() {
    char tabuleiro[3][3], jogador;
    int i, j, linha, coluna, rodada, ganhou, jogar_novamente;

    do {
        for(i = 0; i < 3; i++) {
            for(j = 0; j < 3; j++) {
                tabuleiro[i][j] = ' ';
            }
        }

        ganhou = 0;
        jogar_novamente = 0;

        for (rodada = 1; rodada <= 9 && ganhou == 0; rodada++) {

            if(rodada % 2 == 1) {
                jogador = 'X';
            }
            else {
                jogador = 'O';
            }
            do {
                imprimir_tabuleiro(tabuleiro);
                printf("Digite as coordenadas (de 1 a 3) em que quer colocar o '%c': ", jogador);
                scanf("%d %d", &linha, &coluna);
            } while (linha < 1 || linha > 3 || coluna < 1 || coluna > 3 || tabuleiro[linha - 1][coluna - 1] != ' ');

            tabuleiro[linha - 1][coluna - 1] = jogador;

            ganhou = VerificarVitoriaX(tabuleiro, jogador);
        }

        imprimir_tabuleiro(tabuleiro);

        if (ganhou == 0) {
            printf("\nVelha!!\n");
        }
        else {
            printf("\nO jogador '%c' ganhou! :)\n", jogador);
        }

        printf("Deseja jogar novamente? (1 para Sim 0 para Não): ");
        scanf("%d", &jogar_novamente);

    } while (jogar_novamente);

    return 0;
}
