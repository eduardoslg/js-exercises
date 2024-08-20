Exercícios de Manipulação de Dados em JavaScript

Exercício 1: Filtrar Usuários por Idade
Cenário:
Você tem uma lista de usuários, e cada usuário tem uma idade. Seu objetivo é filtrar os usuários que são maiores de idade (18 anos ou mais).

Dados de entrada:
````Javascript
const usuarios = [
  { nome: "Carlos", idade: 17 },
  { nome: "Ana", idade: 22 },
  { nome: "Bruno", idade: 19 },
  { nome: "Pedro", idade: 15 }
];
````

Solução:
````Javascript
function filtrarMaioresDeIdade(usuarios) {
  return usuarios.filter(usuario => usuario.idade >= 18);
}

const maioresDeIdade = filtrarMaioresDeIdade(usuarios);
````

Resultado esperado:
````Javascript
[
  { nome: "Ana", idade: 22 },
  { nome: "Bruno", idade: 19 }
]
````

***
***
***

Exercício 2: Transformação de Dados
Cenário:
Você tem uma lista de produtos, e cada produto tem um preço em dólares. Seu objetivo é converter o preço de cada produto para reais, considerando uma taxa de conversão de 5,25.

Dados de entrada:
````Javascript
const produtos = [
  { nome: "Notebook", preco: 1000 },
  { nome: "Smartphone", preco: 600 },
  { nome: "Tablet", preco: 400 }
];

const taxaDeConversao = 5.25;
````

Solução:
````Javascript
function converterPrecosParaReais(produtos, taxaDeConversao) {
  return produtos.map(produto => ({
    nome: produto.nome,
    preco: produto.preco * taxaDeConversao
  }));
}

const produtosEmReais = converterPrecosParaReais(produtos, taxaDeConversao);
````

Resultado esperado:
````Javascript
[
  { nome: "Notebook", preco: 5250 },
  { nome: "Smartphone", preco: 3150 },
  { nome: "Tablet", preco: 2100 }
]
````

***
***
***

Exercício 3: Agrupar Itens por Categoria
Cenário:
Você tem uma lista de itens, onde cada item pertence a uma categoria. Seu objetivo é agrupar esses itens por categoria.

Dados de entrada:
````Javascript
const itens = [
  { nome: "Camiseta", categoria: "Roupas" },
  { nome: "Calça", categoria: "Roupas" },
  { nome: "Notebook", categoria: "Eletrônicos" },
  { nome: "Smartphone", categoria: "Eletrônicos" },
  { nome: "Tênis", categoria: "Calçados" }
];
````

Solução:
````Javascript
function agruparPorCategoria(itens) {
  return itens.reduce((acc, item) => {
    if (!acc[item.categoria]) {
      acc[item.categoria] = [];
    }
    acc[item.categoria].push(item.nome);
    return acc;
  }, {});
}

const itensAgrupados = agruparPorCategoria(itens);
````

Resultado esperado:
````Javascript
{
  "Roupas": ["Camiseta", "Calça"],
  "Eletrônicos": ["Notebook", "Smartphone"],
  "Calçados": ["Tênis"]
}
````

***
***
***

Exercício 4: Contagem de Palavras em um Texto
Cenário:
Você tem um texto e deseja saber quantas vezes cada palavra aparece nele.

Dados de entrada:
````Javascript
const texto = "o rato roeu a roupa do rei de roma";
````

Solução:
````Javascript
function contarPalavras(texto) {
  const palavras = texto.split(" ");
  return palavras.reduce((acc, palavra) => {
    acc[palavra] = (acc[palavra] || 0) + 1;
    return acc;
  }, {});
}

const contagemDePalavras = contarPalavras(texto);
````

Resultado esperado:
````Javascript
{
  "o": 2,
  "rato": 1,
  "roeu": 1,
  "a": 1,
  "roupa": 1,
  "do": 1,
  "rei": 1,
  "de": 1,
  "roma": 1
}
````

***
***
***

Exercício 5: Remover Duplicatas de um Array
Cenário:
Você tem um array de números e deseja remover os números duplicados.

Dados de entrada:
````Javascript
const numeros = [1, 2, 2, 3, 4, 4, 5];
````

Solução:
````Javascript
function removerDuplicatas(numeros) {
  return [...new Set(numeros)];
}

const numerosUnicos = removerDuplicatas(numeros);
````

Resultado esperado:
````Javascript
[1, 2, 3, 4, 5]
````

***
***
***

Exercício 6: Calcular a Média de Avaliações
Cenário:
Você tem uma lista de produtos, e cada produto tem uma lista de avaliações (notas de 1 a 5). Seu objetivo é calcular a média das avaliações para cada produto.

Dados de entrada:
````Javascript
const produtos = [
  { nome: "Notebook", avaliacoes: [5, 4, 4, 5] },
  { nome: "Smartphone", avaliacoes: [3, 4, 2, 5, 3] },
  { nome: "Tablet", avaliacoes: [5, 5, 4] }
];
````

Solução:
````Javascript
function calcularMediaAvaliacoes(avaliacoes) {
  const total = avaliacoes.reduce((acc, nota) => acc + nota, 0);
  return Number((total / avaliacoes.length).toFixed(2));
}

const produtosComMedia = produtos.map(produto => ({
  nome: produto.nome,
  mediaAvaliacoes: calcularMediaAvaliacoes(produto.avaliacoes)
}));
````

Resultado esperado:
````Javascript
[
  { nome: "Notebook", mediaAvaliacoes: 4.5 },
  { nome: "Smartphone", mediaAvaliacoes: 3.4 },
  { nome: "Tablet", mediaAvaliacoes: 4.67 }
]
````

***
***
***

Exercício 7: Encontrar a Data Mais Recente
Cenário:
Você tem uma lista de datas e deseja encontrar a data mais recente.

Dados de entrada:
````Javascript
const datas = [
  "2024-07-01",
  "2024-08-15",
  "2024-06-30",
  "2024-08-20"
];
````

Solução:
````Javascript
function encontrarDataMaisRecente(datas) {
  return datas.reduce((maisRecente, data) => 
    new Date(data) > new Date(maisRecente) ? data : maisRecente
  );
}

const dataMaisRecente = encontrarDataMaisRecente(datas);
````

Resultado esperado:
````Javascript
"2024-08-20"
````

***
***
***

Exercício 8: Somar os Valores de um Array de Objetos
Cenário:
Você tem uma lista de transações, onde cada transação tem um valor. Seu objetivo é calcular a soma total dos valores.

Dados de entrada:
````Javascript
const transacoes = [
  { descricao: "Venda", valor: 100 },
  { descricao: "Compra", valor: -50 },
  { descricao: "Venda", valor: 200 },
  { descricao: "Compra", valor: -150 }
];
````

Solução:
````Javascript
function somarValores(transacoes) {
  return transacoes.reduce((total, transacao) => total + transacao.valor, 0);
}

const valorTotal = somarValores(transacoes);
````

Resultado esperado:
````Javascript
100
````

***
***
***

Exercício 9: Agrupar Produtos por Categoria e Calcular Média de Preços
Cenário:
Você tem uma lista de produtos, onde cada produto pertence a uma categoria e tem um preço. Seu objetivo é agrupar os produtos por categoria e calcular a média de preços para cada categoria.

Dados de entrada:
````Javascript
const produtos = [
  { nome: "Notebook", categoria: "Eletrônicos", preco: 1000 },
  { nome: "Smartphone", categoria: "Eletrônicos", preco: 600 },
  { nome: "Tablet", categoria: "Eletrônicos", preco: 400 },
  { nome: "Camiseta", categoria: "Roupas", preco: 50 },
  { nome: "Calça", categoria: "Roupas", preco: 80 }
];
````

Solução:
````Javascript
function agruparECalcularMediaPorCategoria(produtos) {
  const agrupado = produtos.reduce((acc, produto) => {
    if (!acc[produto.categoria]) {
      acc[produto.categoria] = { total: 0, quantidade: 0 };
    }
    acc[produto.categoria].total += produto.preco;
    acc[produto.categoria].quantidade += 1;
    return acc;
  }, {});

  return Object.keys(agrupado).map(categoria => ({
    categoria,
    mediaPreco: Number((agrupado[categoria].total / agrupado[categoria].quantidade).toFixed(2))
  }));
}

const mediaPorCategoria = agruparECalcularMediaPorCategoria(produtos);
````

Resultado esperado:
````Javascript
[
  { categoria: "Eletrônicos", mediaPreco: 666.67 },
  { categoria: "Roupas", mediaPreco: 65.00 }
]
````

***
***
***

Exercício 10: Unir Informações de Listas Diferentes
Cenário:
Você tem duas listas: uma de clientes e outra de pedidos. Seu objetivo é unir as informações para que cada cliente tenha uma lista de seus pedidos.

Dados de entrada:
````Javascript
const clientes = [
  { id: 1, nome: "Carlos Lima" },
  { id: 2, nome: "Ana Souza" },
  { id: 3, nome: "Bruno Silva" }
];

const pedidos = [
  { clienteId: 1, produto: "Notebook" },
  { clienteId: 1, produto: "Mouse" },
  { clienteId: 2, produto: "Teclado" }
];
````

Solução:
````Javascript
function unirClientesEPedidos(clientes, pedidos) {
  return clientes.map(cliente => ({
    ...cliente,
    pedidos: pedidos
      .filter(pedido => pedido.clienteId === cliente.id)
      .map(pedido => pedido.produto)
  }));
}

const clientesComPedidos = unirClientesEPedidos(clientes, pedidos);
````

Resultado esperado:
````Javascript
[
  { id: 1, nome: "Carlos Lima", pedidos: ["Notebook", "Mouse"] },
  { id: 2, nome: "Ana Souza", pedidos: ["Teclado"] },
  { id: 3, nome: "Bruno Silva", pedidos: [] }
]
````

***
***
***

Exercício 11: Cálculo de Faturamento Mensal
Cenário:
Você tem uma lista de transações de um mês, com data e valor. Precisa calcular o faturamento total por mês.

Dados de entrada:
````Javascript
const transacoes = [
  { "data": "2024-07-01", "valor": 100 },
  { "data": "2024-07-15", "valor": 200 },
  { "data": "2024-08-01", "valor": 150 },
  { "data": "2024-08-20", "valor": 300 }
];
````

Solução:
````Javascript
const faturamentoMensal = transacoes.reduce((acumulador, transacao) => {
  const [ano, mes] = transacao.data.split('-');

  const chaveMes = `${ano}-${mes}`;

  if (acumulador[chaveMes]) {
    acumulador[chaveMes] += transacao.valor;
  } else {
    acumulador[chaveMes] = transacao.valor;
  }

  return acumulador;
}, {});
````

Resultado esperado:
````Javascript
{
  "2024-07": 300,
  "2024-08": 450
}
````

***
***
***

Exercício 12: Detecção de Produtos Repetidos
Cenário:
Você tem uma lista de produtos em um carrinho de compras, onde pode haver produtos repetidos. Precisa agrupar os produtos repetidos e somar suas quantidades.

Dados de entrada:
````Javascript
const carrinho = [
  { "produto": "Notebook", "quantidade": 1 },
  { "produto": "Mouse", "quantidade": 2 },
  { "produto": "Notebook", "quantidade": 1 },
  { "produto": "Teclado", "quantidade": 1 }
];
````

Solução:
````Javascript
const produtosAgrupados = carrinho.reduce((acumulador, item) => {
  const produtoExistente = acumulador.find(prod => prod.produto === item.produto);

  if (produtoExistente) {
    produtoExistente.quantidade += item.quantidade;
  } else {
    acumulador.push({ produto: item.produto, quantidade: item.quantidade });
  }

  return acumulador;
}, []);
````

Resultado esperado:
````Javascript
[
  { "produto": "Notebook", "quantidade": 2 },
  { "produto": "Mouse", "quantidade": 2 },
  { "produto": "Teclado", "quantidade": 1 }
]
````

***
***
***

Exercício 13: Detecção de Produtos Repetidos
Cenário:
Você tem uma lista de produtos em um carrinho de compras, onde pode haver produtos repetidos. Precisa agrupar os produtos repetidos e somar suas quantidades.

Dados de entrada:
````Javascript
const funcionarios = [
  { "nome": "Carlos", "habilidades": ["JavaScript", "React"] },
  { "nome": "Ana", "habilidades": ["Java", "Spring"] },
  { "nome": "Bruno", "habilidades": ["Python", "Django"] }
];
````

Solução:
````Javascript
const funcionariosPlanos = funcionarios.flatMap(funcionario =>
  funcionario.habilidades.map(habilidade => ({
    nome: funcionario.nome,
    habilidade: habilidade
  }))
);
````

Resultado esperado:
````Javascript
[
  { "nome": "Carlos", "habilidade": "JavaScript" },
  { "nome": "Carlos", "habilidade": "React" },
  { "nome": "Ana", "habilidade": "Java" },
  { "nome": "Ana", "habilidade": "Spring" },
  { "nome": "Bruno", "habilidade": "Python" },
  { "nome": "Bruno", "habilidade": "Django" }
]
````
