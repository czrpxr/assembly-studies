# Secoes

O codigo assembly e dividido em 3 secoes com as seguintes atribuicoes:

* .data:
Local onde sao declarados dados que serao utilizados no programa.

No Hello World temos dentro desta secao

```as
text db "Hello World!", 10
```

**text:** E o nome que estamos dando a variavel que ira conter o Hello Word.  
**db:** Significa "define bytes" e identifica que estamos definindo uma serie de bytes que serao representados por essa variavel  
**10:** Codigo de nova linha, em decimal, na tabela ASCII.

Ou seja, estamos definindo uma sequencia de bytes que compreende os caracteres do *Hello World!* (incluindo o espaco), e a operacao de *nova linha*

* .bss (nao obrigatorio):
Local onde sao declaradas variaveis sem valor atribuido. Os valores serao atribuidos no decorrer do programa.

* .text:
Local onde se encontra a logica do programa propriamente dita.  

Aqui definimos primeiro um label

```as
global _start:
```

Sempre que invocarmos um label, o ponteiro do codigo sera direcionado para ele. No assembly o *_start* e considerado sempre o inicio de um programa.  Logo apos:  

```as
  mov rax, 1
  mov rdi, 1
  mov rsi, text
  mov rdx, 14
  syscall
``` 
Aqui colocamos o valor 1 nos registradores rax e rdi, posteriormente o conteudo de text em rsi
