# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
*a) A saída será undefined seguido de erro*
 
A saída será undefined seguido de erro porque a variável x foi declarada com var, o que significa que ela sofre hoisting, sendo movida para o topo do escopo, mas sem inicialização, resultando em undefined. Já a variável y, declarada com let, também é içada, mas fica em um estado chamado "zona temporal morta", o que impede seu uso antes da declaração, causando um erro de referência (ReferenceError).

______
**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

*b) Substituir if (a || b === 0) por if (a === 0 && b === 0)*

O erro no código ocorre porque a condição if (a || b === 0) não funciona como esperado. Como o operador || retorna verdadeiro se qualquer um dos valores for truthy, isso significa que qualquer número diferente de zero passará na condição errada. A correção adequada é substituir por if (a === 0 && b === 0), garantindo que a mensagem de erro só seja exibida quando ambos os números forem zero.
______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

*b) O código imprime 200.*

O código imprime 200 porque dentro do switch, após o caso "eletrônico", não há um break. Isso faz com que o fluxo continue para o próximo caso, "vestuário", atribuindo 200 à variável preco antes de encontrar o break, o que interrompe a execução e define o valor final retornado.
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```

*d) 24*

O código primeiro multiplica todos os números da lista por 2, gerando [2, 4, 6, 8, 10]. Em seguida, ele filtra os valores maiores que 5, resultando em [6, 8, 10]. Por fim, soma todos esses valores (6 + 8 + 10), retornando 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

*c) ["banana", "abacaxi", "manga", "laranja"]*

O método splice(1, 2, "abacaxi", "manga") remove dois elementos a partir do índice 1, ou seja, remove "maçã" e "uva", e insere "abacaxi" e "manga" no lugar. O array resultante será ["banana", "abacaxi", "manga", "laranja"].
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

As duas afirmações são verdadeiras, mas a segunda não justifica a primeira. De fato, a herança permite compartilhar métodos e propriedades entre classes, reduzindo a repetição de código. Em JavaScript, o extends é uma forma de implementar herança, mas não é a única, já que a linguagem também permite herança baseada em protótipos.II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.

*b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.*

Embora a herança em JavaScript seja feita com extends, essa não é a única forma de implementar herança. O uso de protótipos também permite compartilhamento de métodos entre objetos.
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

*a) I e II são verdadeiras.*

A classe Funcionario herda de Pessoa e pode acessar diretamente os atributos nome e idade. Além disso, o método apresentar() na classe Funcionario sobrescreve o método da classe pai, mas chama a implementação original usando super.apresentar(), mantendo a exibição do nome e idade antes de adicionar a informação sobre o salário. A afirmação III está errada porque JavaScript suporta herança de classes.
______
**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

b) A asserção é verdadeira e a razão é falsa.

A asserção é verdadeira porque o polimorfismo permite que objetos diferentes respondam a um mesmo método de maneiras distintas. No entanto, a razão é falsa, pois JavaScript não tem suporte direto para sobrecarga de métodos como em outras linguagens. Em vez disso, a implementação do polimorfismo em JavaScript geralmente ocorre por meio de herança e sobrescrita de métodos.
_____

# Questões dissertativas

9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

Código corrijido:

```javascript
//define a função
function somaArray(numeros) {

    //define o inicio da soma
    let soma = 0;

    //define o intervalo, até onde a soma vai e que o vamor de i aumenta em 1
    for (let i = 0; i < numeros.length; i++) {
        //define a soma dos elementos do array após multiplicá-los por 2
        soma += 2*numeros[i];
    }
    //retorna o valor de soma
    return soma;
}
//define os elementos do array a serem inicializados e impressos
console.log(somaArray([1, 2, 3, 4]));
```

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript
class Produto {
    //criar os atributos de Produto
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }
  
    calcularDesconto() {
        // aplica um desconto fixo de 10% no preço do produto
        const desconto = this.preco * 0.10;
        return this.preco - desconto;
    }

    
    precificar() {
        console.log(`Produto: ${this.nome}, Preço: ${this.idade} .`);
      }
  }
  
  class Livro extends Produto {
    //cria os atributos de livro
    constructor(nome, preco) {
        //chama o construtor da classe pai
        super(nome, preco);
        this.autor = autor;
    }
  
    calcularDesconto() {
        //sobrescreve o método da classe pai para aplicar 20% de desconto
        const desconto = this.preco * 0.20;
        return this.preco - desconto;
    }

    precificar() {
        console.log(`Livro: ${this.nome}, Preço: ${this.idade} .`);
      }
  }
```
Nesse contexto, a herança permite que a classe Livro herde todos os métodos e propriedades da classe Produto por meio de extends. Para implementar a modificação do método na classe livro, seria necessário criar instâncias na classe, permitindo a diferente atribuição ou polimorfismos.