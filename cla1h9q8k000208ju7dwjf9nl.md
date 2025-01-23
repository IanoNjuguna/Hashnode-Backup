---
title: "Input && Output, Part2."
seoTitle: "getchar() and getc()"
seoDescription: "Learn how `getchar()` and `getc()` functions work in C for reading characters from input and display ASCII values effectively"
datePublished: Thu Nov 03 2022 19:45:42 GMT+0000 (Coordinated Universal Time)
cuid: cla1h9q8k000208ju7dwjf9nl
slug: input-output-part2
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/raLeFIxXgDY/upload/8135623a6d5a20482c549cf18dcd4fcb.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1737654775918/3b9fb59b-b87b-41f5-86c9-29ca4e3af950.jpeg
tags: c, input-output, getchar

---

The `getchar()` function gets a character from the standard input. It does not have arguments hence, the parentheses are always empty.

It is defined this way:

```C
#include <stdio.h>

int getchar();
```

Technically, `getchar()` is not a function. It is a macro. A macro is a shortcut based on another function, as defined in the `<stdio.h>` header file. This is why the `<stdio.h>` header file is to be included within your source code.

The real function to get characters from standard input is `getc();` and it is defined in this way:

```C
#include <stdio.h>

int c;

c = getc(stdin);
```

In the above example, `getc();` reads from the `stdin` as defined in the header file. The function returns an integer value, which is stored in variable `c`.

#### NB: `getchar();` returns an integer value and not a character value.

### Sample Code:

```C
#include <stdio.h>

int main(void)
{
int i;

printf(" The character is: ");
i=getchar();
printf("%c. \n", i);
return(0);
}
```

When the `getchar()` function is invoked, the character returned is stored in the `i` integer variable. The second `printf()` function will display the character stored in the variable. It is important to note that the `%c` placeholder is used to display single characters. This is because the integer variable, `i`, contains a character value.

### How To Create a Program That Displays a Character’s ASCII Code Value In Decimal.

When the `%d` placeholder is used instead of `%c`, whatever will be displayed when the code is run is the variable's ASCII code value. This is because `%d` displays that value instead of a character value. To understand this, you have to consider that a computing device will treat all information as ones and zeros under the hood and the ASCII code is a value of the information that will be presented to you. It is only when information is displayed as a character, `%c`, does it look like text. This is how I created an [ASCII-Program](https://github.com/IanoNjuguna/ASCII-Program)