# C, uma linguagem não segura

1. Exemplo de acesso a memória não pertencente a variável (array.c) :
    
    ```c
   #include <stdio.h>

    int main() {

    int arr[3] = {1, 2, 3};
    int i;

    for (i = 0; i <= 8; i++) {
        printf("%d\n", arr[i]);
    }

    return 0;
    }
    ```

    Neste exemplo, o programador tenta imprimir os elementos do array "arr" usando um loop "for" que vai até "i <= 8". No entanto, o array "arr" só tem três elementos (índices 0, 1 e 2), portanto, quando "i" atinge o valor 8, o código tenta acessar um elemento fora dos limites do array, o que pode levar a falhas de segurança.
