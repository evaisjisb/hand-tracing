#include <stdio.h>

int main() {
    // Data dari tabel (Credit & Weight)
    int credit[7] = {2, 4, 2, 2, 4, 2, 2};
    float weight[7] = {4.00, 3.33, 3.00, 2.00, 3.67, 4.00, 4.00};

    float totalBobot = 0;
    int totalSKS = 0;
    float gpa;
    int i;

    printf("=== Hand Tracing GPA (7 Mata Kuliah) ===\n\n");
    printf("Iterasi | SKS | Bobot | SKS*Bobot | TotalBobot | TotalSKS\n");
    printf("----------------------------------------------------------\n");

    // Perhitungan step by step
    for(i = 0; i < 7; i++) {
        float hasil = credit[i] * weight[i];
        totalBobot += hasil;
        totalSKS += credit[i];

        printf("%7d | %3d | %5.2f | %9.2f | %10.2f | %8d\n",
               i+1, credit[i], weight[i], hasil, totalBobot, totalSKS);
    }

    // Hitung GPA
    gpa = totalBobot / totalSKS;

    printf("\nTotal SKS = %d\n", totalSKS);
    printf("Total (SKS * Bobot) = %.2f\n", totalBobot);
    printf("IPK = %.2f\n", gpa);

    // Tentukan predikat
    if(gpa >= 3.50) {
        printf("Predikat = Cumlaude\n");
    } else if(gpa >= 3.00) {
        printf("Predikat = Sangat Memuaskan\n");
    } else if(gpa >= 2.50) {
        printf("Predikat = Memuaskan\n");
    } else {
        printf("Predikat = Cukup\n");
    }

    return 0;
}
