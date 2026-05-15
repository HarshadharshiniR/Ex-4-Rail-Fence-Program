# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE



# PROGRAM

```
#include <stdio.h>
#include <string.h>

int main()
{
    char plaintext[100];
    char rail[10][100];
    int i, j, row = 0, dir = 1;
    int rails, len;

    printf("Enter the plain text: ");
    fgets(plaintext, sizeof(plaintext), stdin);

    
    plaintext[strcspn(plaintext, "\n")] = '\0';

    printf("Enter the number of rails: ");
    scanf("%d", &rails);

    len = strlen(plaintext);

    
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            rail[i][j] = '\n';

    
    for (i = 0; i < len; i++)
    {
        rail[row][i] = plaintext[i];

        if (row == 0)
            dir = 1;
        else if (row == rails - 1)
            dir = -1;

        row += dir;
    }

   
    printf("Cipher Text: ");
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            if (rail[i][j] != '\n')
                printf("%c", rail[i][j]);

    return 0;
}
```


# OUTPUT
<img width="1919" height="909" alt="image" src="https://github.com/user-attachments/assets/acab5c3d-fba7-4025-b57f-2732433d2771" />








# RESULT
The code has been successfully executed.
