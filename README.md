#include <stdio.h>

int main() {
    int i, j;
    int centro = 2; // centro da matriz 5x5
    int habilidade[5][5];

    // CONE

    printf("Habilidade: CONE\n");
    for (i = 0; i < 5; i++) {
        for (j = 0; j < 5; j++) {
            if (i >= (centro - j) && i >= (j - centro))
                habilidade[i][j] = 1;
            else
                habilidade[i][j] = 0;

            printf("%d ", habilidade[i][j]);
        }
        printf("\n");
    }

    
    // CRUZ

    printf("\nHabilidade: CRUZ\n");
    for (i = 0; i < 5; i++) {
        for (j = 0; j < 5; j++) {
            if (i == centro || j == centro)
                habilidade[i][j] = 1;
            else
                habilidade[i][j] = 0;

            printf("%d ", habilidade[i][j]);
        }
        printf("\n");
    }

    
    // OCTAEDRO (LOSANGO)
    
    printf("\nHabilidade: OCTAEDRO\n");
    for (i = 0; i < 5; i++) {
        for (j = 0; j < 5; j++) {
            // cálculo simples de distância sem usar abs()
            int di, dj;
            if (i > centro) di = i - centro; else di = centro - i;
            if (j > centro) dj = j - centro; else dj = centro - j;

            if (di + dj <= centro)
                habilidade[i][j] = 1;
            else
                habilidade[i][j] = 0;

            printf("%d ", habilidade[i][j]);
        }
        printf("\n");
    }

    return 0;
}
