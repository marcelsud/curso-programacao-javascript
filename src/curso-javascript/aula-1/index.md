
# Aula 1 - Começando com JavaScript

Material de apoio:
- [Slides](https://docs.google.com/presentation/d/1BKhzvznM5zCcBfiT-xAIrTUB77ZQSkj26jPnuNh2hvI/edit?usp=sharing)
- [Exercícios](https://curso.devcodando.com/aula-1/exercicios)

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
let subtracao = "37" - 7;
console.log(subtracao); // 30

let soma = "37" + 7;
console.log(soma); // "377"
```

### Convertendo strings para números

No caso de um valor que representa um número está armazenado na memória como uma string, existem métodos para a conversão.

```javascript
let idade = parseInt("43");
console.log(idade); // 43

let altura = parseFloat("1.77");
console.log(altura); // 1.77
```

parseInt irá retornar apenas números inteiros, então seu uso é restrito para a casa dos decimais. Além disso, é uma boa prática ao usar parseInt incluir o parâmetro da base. O parâmetro da base é usado para especificar qual sistema númerico deve ser usado.

```javascript
let temperatura = parseInt("37.3");
console.log(temperatura); // 37
```

Utilizando `parseInt` podemos fazer a soma entre uma string e um número sem realizar a concatenação:

```javascript
let soma = parseInt("37") + 7;
console.log(soma); // 44
```

### Convertendo números para strings

```javascript
let idade = String(43);
console.log(idade); //43
console.log(typeof idade); // string

let temperatura = String(37.3);
console.log(temperatura); // 37.3
console.log(typeof temperatura); // string
```


## Array (Vetores)

O objeto `Array` do JavaScript é um objeto global usado na construção de 'arrays' (ou vetores): objetos de alto nível semelhantes a listas

### Criando um Array

```javascript
let frutas = ['Maçã', 'Banana'];
```

### Contando quantos items existem em um Array

```javascript
console.log(frutas.length); // 2
```

### Acessar um item (index) do Array

```javascript
let primeiro = frutas[0];
console.log(primeiro); // Maçã

let ultimo = frutas[frutas.length - 1];
console.log(ultimo); // Banana
```

### Adicionar um item ao final do Array

```javascript
frutas.push('Laranja');
console.log(frutas); //['Maçã', 'Banana', 'Laranja']
```

### Remover um item do final do Array

```javascript
var ultimo = frutas.pop(); // remove Laranja (do final)
console.log(ultimo); // 'Laranja'
console.log(frutas); // ['Maçã', 'Banana']
```

### Remover do início do Array

```javascript
var primeiro = frutas.shift(); // remove Maçã do início
console.log(frutas); // ['Banana']
```

### Adicionar ao início do Array

```javascript
var adicionar = frutas.unshift('Morango') // adiciona ao início
console.log(frutas); // ['Morango', 'Banana']
```

### Procurar o índice de um item na Array

```javascript
frutas.push('Manga');
// ['Morango', 'Banana', 'Manga']

var pos = frutas.indexOf('Banana');
console.log(pos); // 1
```

### Remover um item pela posição do índice

```javascript
var removedItem = frutas.splice(pos, 1); // é assim que se remove um item
console.log(frutas); // ['Morango', 'Manga']
```

### Remover itens de uma posição de índice

```javascript
var vegetais = ['Repolho', 'Nabo', 'Rabanete', 'Cenoura'];
console.log(vegetais);
// ['Repolho', 'Nabo', 'Rabanete', 'Cenoura']

var pos = 1, n = 2;

var itensRemovidos = vegetais.splice(pos, n);
// Isso é como se faz para remover itens, n define o número de itens a se remover,
// a partir da posição (pos) em direção ao fim da array.

console.log(vegetais);
// ['Repolho', 'Cenoura'] (o array original é alterado)

console.log(itensRemovidos);
// ['Nabo', 'Rabanete']

Copiar um Array

var copia = frutas.slice(); // é assim que se copia
// ['Morango', 'Manga']
```

---

Este material faz parte do material de apoio do Curso de Introdução à Programação, ministrado gratuitamente por [@marcelsud](https://linkedin.com/in/marcelsud/).

![CC BY-NC-SA](https://licensebuttons.net/l/by-nc-sa/3.0/88x31.png "CC BY-NC-SA | Attribution-NonCommercial-ShareAlike ")

---