# Planilha_Gilson_NP1

Repositório utilizado com a intenção de treinar o GitHub

Trabalho de: William Martins Jr. 

DADOS DE IDENTIFICAÇÃO

Disciplina: Estrutura de Dados

Conteúdo abordado: Listas encadeadas

Professor: Gilson Pereira do Carmo Filho

Nº do trabalho: 1

Pontos válidos: 10

DESCRIÇÃO DO TRABALHO

Planilha eletrônica é um tipo de programa de computador que utiliza tabelas para realização de cálculos ou
apresentação de dados. Cada tabela é formada por uma grade composta de linhas e colunas. O elemento
indicado pelo cruzamento entre uma linha e uma coluna chama-se célula. Para identificarmos uma célula,
normalmente utilizamos o nome da coluna seguido do nome da linha. Por exemplo, se tomarmos a coluna de
nome A e a linha de número 10, neste cruzamento teremos a célula A10.
Toda informação deve ser colocada em alguma célula para poder ser utilizada. As células são, portanto, o
componente elementar de uma planilha eletrônica, e podem armazenar valores e fórmulas. Os valores podem
ser numéricos (números, data e hora) ou textuais. As fórmulas definem como deve ser calculado o valor de
uma célula (por exemplo "=A1+A2+A3+A4+A5"). O conceito de fórmula, que é basicamente o conceito
elementar de fórmula matemática, é que dá às planilhas eletrônicas seu principal motivo de existência, fazendo
com que sejam utilizadas principalmente para aplicações financeiras e pequenos bancos de dados.
Planilhas eletrônicas podem ser representadas por matrizes esparsas, que são matrizes nas quais a maioria das
posições é preenchida por zeros (ou nula). Para essas matrizes, podemos economizar um espaço significativo
de memória se apenas os termos não nulosforem armazenados. As operações usais sobre essas matrizes (somar,
multiplicar etc.) também podem ser feitas em tempo muito menor se não armazenarmos as posições nulas.
Uma maneira eficiente de representar estruturas com tamanho variável e/ou desconhecido, como as matrizes
esparsas, é com o emprego de alocação encadeada, utilizando listas. Vamos então usar essa representação para
armazenar uma planilha eletrônica. Cada coluna da planilha poderá ser representada por uma lista linear
circular com uma célula cabeça. Da mesma maneira, cada linha da planilha também poderá ser representada
por uma lista linear circular com uma célula cabeça. Cada célula da estrutura, além das células cabeça,
representará os termos não nulos da planilha e poderá ser como no seguinte código:

Universidade de Fortaleza 2

FUNDAÇÃO EDSON QUEIROZ

UNIVERSIDADE DE FORTALEZA

CENTRO DE CIENCIAS TECNOLOGICAS

class Celula {

Celula direita, abaixo;

int linha, coluna;

double valor;

string formula;

};

O campo abaixo seria usado para referenciar o elemento não nulo na mesma coluna. O campo direita seria
usado para referenciar o próximo elemento não nulo na mesma linha. Dada uma planilha representada por uma
matriz A, para um valor ai, j não nulo, deverá haver uma célula com o campo valor contendo ai, j, o campo linha
contendo i e o campo coluna contendo j. Essa célula deverá pertencer a lista circular da linha i e também deverá
pertencer à lista circular da coluna j. Ou seja, cada célula pertencerá a duas listas ao mesmo tempo. Para
diferenciar as células cabeça, pode-se colocar o valor -1 nos campos linha e coluna dessas células.
Considere uma planilha representada pela seguinte matriz esparsa:

𝐴 =
(50 0 0 0

10 0 20 0

0 0 0 0

−30 0 −60 5)

Uma representação da matriz A pode ser vista na Figura 1. Com essa representação, uma matriz esparsa m x n
com r elementos não nulos gastará ( m + n + r ) células. É bem verdade que cada célula ocupa vários bytes na
memória; no entanto, o total de memória usado será menor do que as m x n posições necessárias para
representar a matriz toda, desde que r seja suficientemente pequeno.
Dada a representação de listas duplamente encadeadas, o trabalho consiste em desenvolver uma planilha
eletrônica capaz de realizar as operações de inserir, remover, alterar e visualizar o conteúdo de suas células.
Quando o conteúdo de uma célula for uma fórmula, o valor exibido pela célula deverá ser automaticamente
atualizado caso haja alteração no valor das células referenciadas pela fórmula.
Para inserir e remover células das listas que formam a planilha, crie métodos especiais para esse fim. Por
exemplo:

void insere(int i, int j, double v)

para inserir o valor v na linha i, coluna j da planilha.

É obrigatório o uso de alocação dinâmica de memória para implementar as listas de adjacência que representam a planilha.

A interface com o usuário poderá ser gráfica ou baseada em texto (console).
