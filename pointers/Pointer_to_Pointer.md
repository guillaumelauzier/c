A pointer in C programming language is a variable that holds the address of another variable. This concept is fundamental to understanding how variables are accessed and manipulated within memory, which is critical to efficient and effective programming.

A pointer to a pointer is, as the term implies, a pointer that holds the address of another pointer. This leads to what is known as "multiple indirection" or a "chain of pointers".

Here's an explanation using an analogy: Imagine a treasure hunt where each clue (a pointer) leads you to the next clue. A "pointer to a pointer" is like a clue that doesn't lead directly to the treasure, but instead leads to another clue (the second pointer), which then leads to the treasure (the variable).

Here's a simple example in C:

```c
int **pp; // declare a pointer to a pointer to int
```

In this example, `pp` is a pointer that points to another pointer that points to an integer. We can use this in practice like so:

```c
int value = 5000;
int *p = &value; // pointer to an integer
int **pp = &p; // pointer to a pointer to an integer
```

Now, `pp` points to `p`, which in turn points to `value`.

We can access `value` through `pp` by dereferencing it twice:

```c
printf("Value of **pp: %d\n", **pp); // Outputs: Value of **pp: 5000
```

In this line, the first dereference (`*pp`) gives us the pointer `p`, and the second dereference (`**pp`) gives us the integer value `value` that `p` points to. This is why we say that `pp` is a pointer to a pointer – it points to another pointer (`p`), which in turn points to an integer (`value`).
