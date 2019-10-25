---
layout: post
title: Refactoring de Código - Por onde começar?
author: bih_letti
category: Best Practices
featured_image: sample/post-thumb-1.jpg
excerpt: Refactoring de código é o processo de esclarecer e simplificar o design do código existente, sem alterar seu comportamento.
---

## O que é Refactoring de Código?

> "Refactoring de código é o processo de esclarecer e simplificar o design do código existente, sem alterar seu comportamento.”

Pode assumir várias formas:

* Dependências não íntegras entre classes ou pacotes;
* Má alocação de responsabilidades de classe;
* Muitas responsabilidades por método ou classe;
* Código duplicado;
* Outras variedades de confusão e desordem

A refatoração evita o "apodrecimento" do código, garantindo a facilidade de manter e estender a base de código. Essa extensibilidade é a razão para refatorar e medir seu sucesso.

Mas note que é apenas "seguro" refatorar extensivamente o código se tivermos extensos conjuntos de testes unitários do tipo que obtemos trabalhando com o conceito de Test-First.

Sem poder executar esses testes após cada pequena etapa de uma refatoração, corremos o risco de introduzir erros. Se você está fazendo um verdadeiro desenvolvimento orientado a testes (Test-Driven Development - TDD), no qual o design evolui continuamente, então você não tem escolha sobre a refatoração regular, já que é assim que você evolui o design.

#### Code Hygiene:

Uma metáfora popular para a refatoração é limpar a cozinha enquanto você cozinha.

## Refatorações específicas

As refatorações são o oposto de mexer sem parar no código; elas são precisas e finitas. O livro Refactoring de Martin Fowler discorre sobre o assunto descrevendo 72 "refatorações" específicas por nome (por exemplo, "Extrair método", que extrai um bloco de código de um método e cria um novo método para ele). Esse livro traz uma ótima contribuição em relação as refatorações específicas existentes, mas, bem pontuado pelo time de arquitetura da Natura, de acordo com o Handrus Stephan Nogueira, o livro Refactoring é um dos livros mais famosos neste tema, mas não "definitivo" sobre o assunto, afinal todos os dias temos novos paradigmas de programação sendo criados e explorados.
Cada refatoração converte uma seção de código (um bloco, um método, uma classe) de um dos 22 estados "mal-cheirosos" bem compreendidos para um estado mais otimizado.

## Refatorando para Padrões

A refatoração não ocorre apenas em níveis de código baixos. Em seu recente livro Refactoring to Patterns, Joshua Kerievsky habilmente defende que a refatoração é a técnica que devemos usar para introduzir os padrões de projeto da Gang of Four em nosso código.

## O fluxo de refatoração

Em um contexto Test-First, a refatoração tem o mesmo fluxo que qualquer outra alteração de código. Você tem seus testes automatizados. Você começa a refatoração fazendo a menor alteração discreta possível que irá compilar, executar e funcionar. Sempre que possível, você faz essas alterações adicionando ao código existente, em paralelo a ele. Você executa os testes. Em seguida, você faz a próxima pequena alteração discreta e executa os testes novamente. Quando a refatoração está em vigor e os testes estão todos limpos, você volta e remove o código paralelo antigo. Depois que os testes ficarem limpos depois disso, você está pronto.
Fonte:  https://resources.collab.net/agile-101/code-refactoring

## 4 Princípios do Refactoring de Código

Keep It Small
* A refatoração é mais segura e barata quando é feita em muitos pequenos incrementos, e não em grandes lotes.
* O pior extremo é o sistema completo reescrever a refatoração.
* As melhores atividades de refatoração levam segundos ou minutos para serem executadas.
* Pequenas refatorações criam um constante "overhead" modesto no trabalho da equipe. Essa sobrecarga então se torna uma parte natural do ritmo da equipe. 

Business Catalysts

* Quando é o primeiro que uma refatoração deve ser feita? Não sempre que a equipe técnica quiser fazê-lo. Em vez disso, a equipe técnica precisa usar solicitações de negócios como catalisadores para refatoração. Se a empresa precisar de um novo recurso, a refatoração só deve ser feita nas partes do sistema necessárias para ativar esse recurso. Em outras palavras, não refatore toda a interface do usuário, apenas refatore as partes relacionadas ao pedido de negócios específico

Team Cohesion
* O trabalho em equipe no Agile exige altos níveis de comunicação e colaboração. No trabalho de refatoração, o trabalho em equipe se aplica tanto quanto em qualquer outra atividade.
* Exemplos: unit testing frameworks,  mocking frameworks, pair programming e mob programming.

Transparency

* De muitas maneiras, esse é o princípio de refatoração mais simples: a equipe precisa ser completamente aberta e honesta com todas as partes interessadas sobre o custo da refatoração.

Fonte: http://www.agileadvice.com/2016/03/24/scrumxplean/refactoring-4-key-principles/

## Diferenças entre Reestruturação, Reescrita e Refatoração

On Rearchitecting (vs Restructuring) vs Refactoring

"Em sua curta entrada em bliki Refactoring Malapropism, Martin Fowler discute como às vezes o termo "refatoração" é usado quando não é apropriado. Em particular, é discutida a confusão com o termo "reestruturação". Como é mostrado em seu livro Refatoração: aprimorando o design do código existente, uma tarefa de refatoração em um determinado grupo de código implica aplicar uma técnica específica para fazer pequenas transformações de preservação de comportamento em código-fonte. O ponto chave aqui são as palavras "técnica específica / s" e "pequena", que qualificam as transformações descritas nos principais capítulos do livro. Para mim, reestruturação significa algo maior e abstrato. Algo que não implica apenas transformar uma parte específica do código, mas reorganizar os componentes que definem a arquitetura do sistema. Rearchitect / Reestruture um sistema implica aplicar transformações de granulação maiores, como por exemplo, os chamados padrões arquitetônicos (veja os livros do POSA). É por isso que para mim o termo "reestruturação" de um sistema é equivalente a "reestruturar" esse sistema (e eu prefiro o termo rearchitect)."


On Refactoring vs Rewriting

"E quanto a refatoração e reescrita? Para mim, reescrever tem a ver com legibilidade e clareza de código em duas dimensões relacionadas à (arte) de implementar código: seleção adequada e combinação de estruturas de controle e seleção apropriada de nomes de classes, nomes de atributos, relacionamentos e nomes de métodos. Com relação às estruturas de controle, considero reescrever apenas no contexto de um único método interno para melhorar a leitura (por exemplo, reescrevendo um loop). Fora desse escopo, considero a refatoração. Três livros interessantes que lidam com a reescrita e as melhores práticas ao implementar o código são o clássico McConnell's Code Complete, o Kent Kent's Implementation Patterns e o Robert Martin's Clean Code.

Costumo separar modificações na estrutura do sistema (reestruturação / reestruturação e refatoração) das partes internas de um método (que implicam reescrever). Algumas pessoas podem argumentar que você pode refatorar a estrutura de algum trecho de código e, ao mesmo tempo, reescrever os identificadores de atributos, operações e parâmetros, se necessário. De fato, em IDEs como Eclipse ou IntelliJ, você pode encontrar nas ações de refatoração uma entrada "renomear". No entanto, mesmo com a ajuda de IDEs, a reescrita pode introduzir o risco de introduzir erros. A refatoração também é propensa a erros se você não seguir as regras. Portanto, é melhor não ter duas fontes de erros ao mesmo tempo."

Fonte:http://onsoftwaredesignandconstruction.blogspot.com/2009/11/re-rearchitecting-restructuring.html

## Então... quanto tempo dedicar ao Refactoring?

Em nenhuma fonte pesquisada existe um consenso sobre tempo ou % dedicada a refactoring com uma comprovação científica. O que é possível notar é que essa necessidade varia de acordo com cada aplicação, de acordo com suas características e peculiaridades. Entendo que o que faz sentido é compreender as diferenças majoritárias entre refatoração, reescrita e reestruturação que determinam pontos cruciais na utilização deste tempo.

A frase do autor inicial é marcante “refactoring de código é o processo de esclarecer e simplificar o design do código existente, sem alterar seu comportamento", pois simboliza o que acredito. A partir do momento em que há alteração do comportamento daquilo em que está sendo feito o refactoring, não é mais um refactoring - é uma mudança estrutural, uma change, uma mudança de arquitetura, uma reestruturação - algo maior do que uma refatoração.

Pensando nisso, a refatoração deve obrigatoriamente fazer parte do contexto de desenvolvimento de todas as aplicações da Natura, pois através dela, poderemos garantir um código com maior qualidade e clareza, além de que, entendo que com o tempo esse código trará menor entropia no entendimento do mesmo para o time que nele trabalha, dada a rotatividade dos desenvolvedores das consultorias que atuam no nosso contexto Natura.

O que entendo ser importante é definir em cada ativo digital/plataforma os conceitos do que será trabalhado no refactoring da aplicação, pois existem aplicações que não utilizam ainda testes automatizados ou unitários, e, dado os contextos diferentes que atuamos, as premissas e contextos tornam necessários que cada techlead defina uma % que será utilizada no refactoring da sua aplicação.
