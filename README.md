# Conversor de Número Decimal para Binário e Outras Bases Numéricas

Este programa em C++ converte um número decimal para sua representação binária e também exibe suas representações em outras bases numéricas.

## Como Funciona

O algoritmo utiliza um loop `while` para dividir o número decimal `n` por 2 e armazenar o resto da divisão, que será 0 ou 1, em uma string que representa o número binário. O processo é repetido até que `n` seja igual a 0.

A cada iteração do loop:
1. O resto da divisão de `n` por 2 é calculado.
2. O resto é convertido para string e adicionado à frente da string binária.
3. O número `n` é dividido por 2.

Além disso, o programa utiliza manipuladores de fluxo para exibir o número em diferentes bases numéricas:
- `dec`: Exibe o número em base decimal.
- `hex`: Exibe o número em base hexadecimal.
- `oct`: Exibe o número em base octal.
- `bitset<8>`: Converte o número para um conjunto de bits e exibe em binário.

## Código

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    int decimal = 5; // Número decimal a ser convertido
    cout << dec << decimal << " em decimal é:\n";
    cout << hex << decimal << " em hexadecimal\n";
    cout << oct << decimal << " em octal\n";
    cout << bitset<8>(decimal) << " em binário\n"; // Representação binária usando bitset

    int resto = 0;
    string binario;
    while(decimal != 0){
        resto = decimal % 2; // Calcula o resto da divisão de decimal por 2
        binario = to_string(resto) + binario; // Adiciona o resto à frente da string binária
        decimal /= 2; // Divide decimal por 2
    }
    cout << "Representação binária calculada manualmente: " << binario << endl; // Exibe o resultado
    return 0;
}
