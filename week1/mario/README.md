# Mario
## Make mario pyramides
```sh
include <cs50.h>
include <stdio.h>

int main(void)
{
    int height;
    do
    {
        height = get_int("height : ");
    }
    // True or False loop
    while ((height < 1) || (height > 8));

    for (int i = 0; i < height; i++)
    {
        // Left half Pyramid spaces
        for (int j = height - 1; j > i; j--)
        {
            printf(" ");
        }
        // Left half Pyramid hashes
        for (int k = 0; k <= i; k++)
        {
            printf("#");
        }

        printf("  ");


        // Right half pyramid
        for (int k = 0; k <= i; k++)
        {
            printf("#");
        }
        printf("\n");
    }
}
```