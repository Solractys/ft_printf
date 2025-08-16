# ft_printf

<div align="center">
  <img src="https://img.shields.io/badge/42-School-black?style=flat-square&logo=42" alt="42 School"/>
  <img src="https://img.shields.io/badge/Language-C-blue?style=flat-square&logo=c" alt="Language: C"/>
  <img src="https://img.shields.io/badge/Grade-100%2F100-success?style=flat-square" alt="Grade"/>
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square" alt="Status"/>
</div>

##  Descrição

O **ft_printf** é um projeto da 42 School que consiste em recriar a função `printf` da biblioteca padrão do C. Este projeto tem como objetivo aprofundar o conhecimento sobre:

- **Funções variádicas** (`va_list`, `va_start`, `va_arg`, `va_end`)
- **Manipulação de strings** e formatação
- **Conversões** de tipos de dados
- **Flags** e especificadores de formato
- **Gerenciamento de memória**

##  Objetivos do Projeto

- Implementar uma versão funcional do `printf`
- Gerenciar diferentes tipos de conversão
- Implementar flags de formatação
- Retornar o número de caracteres impressos
- Seguir a norma de código da 42 (Norminette)

## ⚙ Especificações Técnicas

### Conversões Obrigatórias
A função deve implementar as seguintes conversões:

| Especificador | Tipo | Descrição |
|---------------|------|-----------|
| `%c` | `char` | Imprime um único caractere |
| `%s` | `char *` | Imprime uma string |
| `%p` | `void *` | Imprime um endereço de ponteiro em hexadecimal |
| `%d` | `int` | Imprime um número decimal (base 10) |
| `%i` | `int` | Imprime um inteiro em base 10 |
| `%u` | `unsigned int` | Imprime um decimal sem sinal |
| `%x` | `unsigned int` | Imprime um número em hexadecimal (a-f minúsculo) |
| `%X` | `unsigned int` | Imprime um número em hexadecimal (A-F maiúsculo) |
| `%%` | - | Imprime o símbolo percentual |

##  Compilação e Uso

### Compilação
```bash
# Compilar a biblioteca
make
https://github.com/Solractys/ft_printf
# Compilar com flags de debug
make debug

# Limpar arquivos objeto
make clean

# Limpar tudo (incluindo biblioteca)
make fclean

# Recompilar tudo
make re
```

### Exemplo de Uso
```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Hello %s!\n", "World");
    ft_printf("Number: %d\n", 42);
    ft_printf("Hex: %x\n", 255);
    ft_printf("Pointer: %p\n", &main);
    
    return (0);
}
```

### Compilação com seu projeto
```bash
gcc -Wall -Wextra -Werror main.c libftprintf.a
```

##  Testes

### Testadores Recomendados
1. **[pft](https://github.com/gavinfielder/pft)** - Testes básicos unitários
2. **[42TESTERS-PRINTF](https://github.com/Mazoise/42TESTERS-PRINTF)** - Múltiplas flags
3. **[ft_printf_test](https://github.com/cacharle/ft_printf_test)** - Testes gerados aleatoriamente

### Casos de Teste Importantes
- `INT_MIN` e `INT_MAX` para `%d` e `%i`
- Casos com múltiplos zeros na precisão
- Combinações de diferentes flags
- Strings NULL e ponteiros NULL
- Larguras e precisões extremas

##  Conceitos Importantes

### Funções Variádicas
```c
#include <stdarg.h>

int ft_printf(const char *format, ...)
{
    va_list args;
    
    va_start(args, format);    // Inicializar
    // ... processar argumentos
    char c = va_arg(args, int); // Próximo argumento
    va_end(args);              // Finalizar
    
    return (chars_printed);
}
```

### Estrutura de Dados
```c
typedef struct s_print
{
    va_list args;     // Lista de argumentos
    int     width;    // Largura mínima
    int     precision; // Precisão
    int     zero_pad; // Flag '0'
    int     left_align; // Flag '-'
    int     total_len; // Comprimento total impresso
} t_print;
```

##  Critérios de Avaliação

- ✅ **Norminette**: Código deve seguir a norma da 42
- ✅ **Makefile**: Regras obrigatórias implementadas
- ✅ **Funcionalidade**: Todas as conversões funcionando
- ✅ **Valor de Retorno**: Número correto de caracteres
- ✅ **Gestão de Memória**: Sem vazamentos (leaks)

##  Skills Desenvolvidas

- **Programação em C** avançada
- **Funções variádicas** e `stdarg.h`
- **Parsing** de strings complexas
- **Manipulação de bits** e conversões numéricas
- **Debugging** e **testing**
- **Gestão de projeto** e estruturação de código

##  Recursos Úteis

- `man 3 printf` - Manual da função printf
- [Variadic Functions in C](https://www.geeksforgeeks.org/variadic-functions-in-c/)
- [Printf Format Specifiers](https://www.cplusplus.com/reference/cstdio/printf/)

##  Autor

**[Solractys (csilva-s)]** - [@Solractys](https://github.com/Solractys)

---

<div align="center">
  <i>Projeto desenvolvido como parte do currículo da 42 School</i>
</div>

##  Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

---

*Feito com ❤️ na 42 School*
