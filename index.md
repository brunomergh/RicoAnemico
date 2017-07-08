## Modelo Rico e Anêmico

O "Modelo de Domínio Anêmico", é um design pattern de desenvolvimento de software baseado no domínio do negócio (domain), onde objetos que representam modelagem do negócio (model) são "anêmicos", ou seja: desprovidos de comportamento.

Neste pattern, os objetos do model apenas carregam os dados, e os comportamentos de negócio são expostos por outras classes que recebem estes objetos anêmicos para processá-los.

Quais são as diferenças de implementação desse modelo em comparação com o Modelo Orientado a Objeto?

A reposta para esta pergunta pode ser controversa. Alguns podem dizer que não se pode descrever diferenças pois o design pattern Anemic Domain Model também é orientado a objetos.

A noção de diferença nasce quando você aceita a proposição de que, na orientação a objetos, um objeto expõe dados e comportamentos. Neste caso, esta é a diferença: o design pattern Anemic Domain Model propõe justamente que estas coisas sejam separadas em objetos distintos.

Um pequeno exemplo dos dois modelos na linguagem java:

Anemic Domain Model:

class ContaaPagar {

    double valorDevido;
    boolean pago;
}

class BaixaContaaPagar {

    void baixar(ContaaPagar contaaPagar) {
        contaaPagar.pago = true;
        contaaPagar.valorDevido = 0d;
    }
}
Outro design pattern (DDD, por exemplo):

class ContaaPagar {

    double valorDevido;
    boolean pago;

    void baixar() {
        // baixa esta conta a pagar
        pago = true;
        valorDevido = 0d;
    }
}
