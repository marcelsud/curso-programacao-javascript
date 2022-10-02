
# Aula 1 - Começando com JavaScript

Material de apoio:
- [Slides](https://docs.google.com/presentation/d/1BKhzvznM5zCcBfiT-xAIrTUB77ZQSkj26jPnuNh2hvI/edit?usp=sharing)
- [Exercícios](https://curso.devcodando.com/aula-1-exercicios)

## Sintaxe básica

JavaScript pega emprestado a maior parte de sua sintaxe do Java, mas também é influenciado por Awk, Perl e Python.

JavaScript é **case-sensitive** e usa o conjunto de caracteres **Unicode.** Por exemplo, a palavra Früh (que significa "cedo" em Alemão) pode ser usada como nome de variável.

```javascript
    var Preço = "foobar";
```

Mas a variável `preço` não é a mesma que `Preço` porque JavaScript é case-sensitive.

No JavaScript, instruções são chamadas de declaração e são separadas por um ponto e vírgula (;)

## Comentários

A sintaxe dos comentários em JavaScript é semelhante como em C++ e em muitas outras linguagens:

```javascript
// comentário de uma linha

/* isto é um comentário longo
   de múltiplas linhas.
 */
```

## Declarações

Existem três tipos de declarações em JavaScript:

| Tipo | Descrição |
|--|--|
| **var** | Declara uma variável, opcionalmente, inicializando-a com um valor. |
| **let** | Declara uma variável local de escopo do bloco, opcionalmente, inicializando-a com um valor. |
| **const** | Declara uma constante de escopo de bloco, apenas de leitura. Obrigatório inicializar com um valor. |

### Variáveis

Você usa variáveis como nomes simbólicos para os valores em sua aplicação. O nome das variáveis, chamados de identificadores, obedecem determinadas regras.

Um identificador JavaScript deve começar com uma letra, underline (`_`), ou cifrão (`$`); os caracteres subsequentes podem também ser números (0-9). Devido JavaScript ser case-sensitive, letras incluem caracteres de "A" a "Z" (maiúsculos) e caracteres de "a" a "z" (minúsculos).

Alguns exemplos de nomes legais são `numeros_visitas`, `temp99`, e `_nome`.

### Constantes

Você pode criar uma constante apenas de leitura por meio da palavra-chave **const**. A sintaxe de um identificador de uma constante é semelhante ao identificador de uma variável: deve começar com uma letra, sublinhado ou cifrão e pode conter caractere alfabético, numérico ou sublinhado.

```javascript
const PI = 3.14;
``` 

Uma constante não pode alterar seu valor por meio de uma atribuição ou ser declarada novamente enquanto o script está em execução. Deve ser inicializada com um valor.

As regras de escopo para as constantes são as mesmas para as váriaveis `let` de escopo de bloco. Se a palavra-chave `const` for omitida, presume-se que o identificador represente uma variável (var).

## Estrutura de dados e tipos

### Tipos de dados (primitivos)

| Tipo | Descrição |
|--|--|
| [Boolean](https://developer.mozilla.org/pt-BR/docs/Glossary/Boolean) | `true` e `false`. |
| [null](https://developer.mozilla.org/pt-BR/docs/Glossary/Null) | Uma palavra-chave que indica valor nulo. Devido JavaScript ser case-sensitive,  |`null` não é o mesmo que `Null`, `NULL`, ou ainda outra variação.
| [undefined](https://developer.mozilla.org/pt-BR/docs/Glossary/undefined) | Uma propriedade superior cujo valor é indefinido. |
| [Number](https://developer.mozilla.org/pt-BR/docs/Glossary/Number) | `42` ou `3.14159`. |
| [String](https://developer.mozilla.org/pt-BR/docs/Glossary/String) | "Olá!" |
| [Symbol](https://developer.mozilla.org/pt-BR/docs/conflicting/Web/JavaScript/Reference/Global_Objects/Symbol) (novo em ECMAScript 6) | Um tipo de dado cuja as instâncias são únicas e imutáveis. |
| [Object](https://developer.mozilla.org/pt-BR/docs/Glossary/Object) | Você pode pensar em objetos como recipientes para os valores. |

### Conversão de tipos de dados

JavaScript é uma linguagem dinamicamente tipada. Isso significa que você não precisa especificar o tipo de dado de uma variável quando declará-la, e tipos de dados são convertidos automaticamente conforme a necessidade durante a execução do script. Então, por exemplo, você pode definir uma variável da seguinte forma:

```javascript
var resposta = 42;
```

E depois, você pode atribuir uma string para a mesma variável, por exemplo:

```javascript
resposta = "Obrigado pelos peixes...";
```

Devido JavaScript ser dinamicamente tipado, essa declaração não gera uma mensagem de erro.

Em expressões envolvendo valores numérico e string com o operador +, JavaScript converte valores numérico para strings. Por exemplo, considere a seguinte declaração:

```javascript
x = "A resposta é " + 42 // "A resposta é 42"
y = 42 + " é a resposta" // "42 é a resposta"
```

Nas declarações envolvendo outros operadores, JavaScript não converte valores numérico para strings. Por exemplo:

```javascript
"37" - 7 // 30
"37" + 7 // "377"
```

### Convertendo strings para números

No caso de um valor que representa um número está armazenado na memória como uma string, existem métodos para a conversão.

```javascript
parseInt()
parseFloat()
```

parseInt irá retornar apenas números inteiros, então seu uso é restrito para a casa dos decimais. Além disso, é uma boa prática ao usar parseInt incluir o parâmetro da base. O parâmetro da base é usado para especificar qual sistema númerico deve ser usado.

Uma método alternativo de conversão de um número em forma de string é com o operador + (operador soma):

```javascript
"1.1" + "1.1" = "1.11.1"
(+"1.1") + (+"1.1") = 2.2

// Nota: Os parênteses foram usados para deixar mais legível o código, eles não são requiridos.
```


