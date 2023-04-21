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

2. Referência Nula (null-reference.c) :

    ```c
    #include <stdio.h>
    
    int main() {
    
        int *ptr = NULL;
        *ptr = 5;
        
        return 0;
    }
    ```

    Neste exemplo, o programador declara um ponteiro "ptr" e o inicializa com um valor nulo. No entanto, o código tenta atribuir o valor 5 ao endereço de memória apontado por "ptr", que é nulo. Isso pode levar a falhas de segurança, como falhas de segmentação.

3. Declaração vazia de variável :

    ```c
    #include <stdio.h>

    int main() {

        int x;
        if (x == 0) {
            printf("x é zero\n");
        } else {
            printf("x não é zero\n");
        }
    
        return 0;
    }
    ```


    Neste exemplo, o programador declara uma variável "x" sem inicializá-la. Em seguida, o código verifica se "x" é igual a zero, mas como "x" não foi inicializado com nenhum valor, ele pode conter qualquer valor na memória, o que pode levar a comportamentos inesperados e vulnerabilidades de segurança

Estes são apenas alguns exemplos de código em C que podem apresentar vulnerabilidades de memória. É importante que os programadores estejam cientes dessas vulnerabilidades e tomem medidas para garantir que seus códigos estejam seguros e livres de falhas de segurança.