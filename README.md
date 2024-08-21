Exercícios de Manipulação de Dados em JavaScript

Exercício 1: Filtrar Usuários por Idade
Cenário:
Você tem uma lista de usuários, e cada usuário tem uma idade. Seu objetivo é filtrar os usuários que são maiores de idade (18 anos ou mais).

Dados de entrada:
````Javascript
const users = [
  { name: "Carlos", age: 17 },
  { name: "Ana", age: 22 },
  { name: "Bruno", age: 19 },
  { name: "Pedro", age: 15 }
];
````

Solução:
````Javascript
const usersOfLegalAge = users.filter(user => user.age >= 18)
````

Resultado esperado:
````Javascript
[
  { name: "Ana", age: 22 },
  { name: "Bruno", age: 19 }
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
const products = [
  { name: "Notebook", price: 1000 },
  { name: "Smartphone", price: 600 },
  { name: "Tablet", price: 400 }
];

const conversionRate = 5.25;
````

Solução:
````Javascript
const productsWithAValueInReais = products.map(product => ({
  name: product.name,
  price: product.price * conversionRate
}))
````

Resultado esperado:
````Javascript
[
  { name: "Notebook", price: 5250 },
  { name: "Smartphone", price: 3150 },
  { name: "Tablet", price: 2100 }
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
const items = [
  { name: "Camiseta", category: "Roupas" },
  { name: "Calça", category: "Roupas" },
  { name: "Notebook", category: "Eletrônicos" },
  { name: "Smartphone", category: "Eletrônicos" },
  { name: "Tênis", category: "Calçados" }
];
````

Solução:
````Javascript
const itemsGroupedByCategory = items.reduce((acc, item) => {
  if (!acc[item.category]) {
    acc[item.category] = []
  }

  acc[item.category].push(item.name)

  return acc
}, {})
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
const texto = "o rato roeu a roupa do rei de roma e o rato morreu de fome";
````

Solução:
````Javascript
const text = "o rato roeu a roupa do rei de roma e o rato morreu de fome";
const splittedText = text.split(" ")

const quantityOfEachWord = splittedText.reduce((acc, word) => {
  acc[word] = (acc[word] || 0) + 1

  return acc
}, {})
````

Resultado esperado:
````Javascript
{
    "o": 2,
    "rato": 2,
    "roeu": 1,
    "a": 1,
    "roupa": 1,
    "do": 1,
    "rei": 1,
    "de": 2,
    "roma": 1,
    "e": 1,
    "morreu": 1,
    "fome": 1
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
const numbers = [1, 2, 2, 3, 4, 4, 5, 5, 5, 99, 99, 9, 99];

````

Solução:
````Javascript
const removeDuplicateNumbers = [...new Set(numbers)];
````

Resultado esperado:
````Javascript
[1, 2, 3, 4, 5, 99, 9]
````

***
***
***

Exercício 6: Calcular a Média de Avaliações
Cenário:
Você tem uma lista de produtos, e cada produto tem uma lista de avaliações (notas de 1 a 5). Seu objetivo é calcular a média das avaliações para cada produto.

Dados de entrada:
````Javascript
const products = [
  { name: "Notebook", reviews: [5, 4, 4, 5] },
  { name: "Smartphone", reviews: [3, 4, 2, 5, 3] },
  { name: "Tablet", reviews: [5, 5, 4] }
];
````

Solução:
````Javascript
const calculatedAverageProducts = products.map(product => {
  const total = product.reviews.reduce((acc, review) => {
    acc += review

    return acc
  }, 0)

  const average = Number((total / product.reviews.length).toFixed(2))

  return {
    name: product.name,
    average, 
  }
})
````

Resultado esperado:
````Javascript
[
  { name: "Notebook", average: 4.5 },
  { name: "Smartphone", average: 3.4 },
  { name: "Tablet", average: 4.67 }
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
const dates = [
  "2024-06-30",
  "2024-07-01",
  "2024-08-15",
  "2024-08-20"
];
````

Solução:
````Javascript
const mostRecentDate = dates.reduce((acc, date) => new Date(date) > new Date(acc) ? date : acc)
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
const transactions = [
  { description: "Venda", value: 100 },
  { description: "Compra", value: -50 },
  { description: "Venda", value: 200 },
  { description: "Compra", value: -150 }
];
````

Solução:
````Javascript
const totalValueOfTransaction = transactions.reduce((acc, transaction) => {
  acc += transaction.value

  return acc
}, 0)
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
const products = [
  { name: "Notebook", category: "Eletrônicos", price: 1000 },
  { name: "Smartphone", category: "Eletrônicos", price: 600 },
  { name: "Tablet", category: "Eletrônicos", price: 400 },
  { name: "Camiseta", category: "Roupas", price: 50 },
  { name: "Calça", category: "Roupas", price: 80 }
];
````

Solução:
````Javascript
function categoriesAndAveragePrice(products) {
  const agroupedProducts = products.reduce((acc, product) => {
    if (!acc[product.category]) {
      acc[product.category] = { total: 0, quantity: 0 }
    }

    acc[product.category].total += product.price
    acc[product.category].quantity += 1
  
    return acc
  }, {})


  const output = Object.keys(agroupedProducts).map(category => ({
    category,
    average: agroupedProducts[category].total / agroupedProducts[category].quantity
  }))

  return output
}
````

Resultado esperado:
````Javascript
[
    {
        "category": "Eletrônicos",
        "average": 666.6666666666666
    },
    {
        "category": "Roupas",
        "average": 65
    }
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
const clients = [
  { id: 1, name: "Carlos Lima" },
  { id: 2, name: "Ana Souza" },
  { id: 3, name: "Bruno Silva" }
];

const requests = [
  { clientId: 1, product: "Notebook" },
  { clientId: 1, product: "Mouse" },
  { clientId: 2, product: "Teclado" }
];
````

Solução:
````Javascript
const clientsWithRequest = clients.map(client => {
  const clientRequest = requests.filter(request => request.clientId === client.id)

  return {
    ...client,
    request: clientRequest
  }
})
````

Resultado esperado:
````Javascript
[
  { id: 1, name: "Carlos Lima", requests: ["Notebook", "Mouse"] },
  { id: 2, name: "Ana Souza", requests: ["Teclado"] },
  { id: 3, name: "Bruno Silva", requests: [] }
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
const transactions = [
  { date: "2024-07-01", value: 100 },
  { date: "2024-07-15", value: 200 },
  { date: "2024-08-01", value: 150 },
  { date: "2024-08-20", value: 300 }
];
````

Solução:
````Javascript
const monthlyBilling = transactions.reduce((acc, transaction) => {
  const [year, month] = transaction.date.split("-")

  const yearAndMonth = `${year}-${month}`

  if (!acc[yearAndMonth]) {
    acc[yearAndMonth] = 0
  }

  acc[yearAndMonth] += transaction.value

  return acc
}, {})
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
const cart = [
  { productName: "Notebook", quantity: 1 },
  { productName: "Mouse", quantity: 2 },
  { productName: "Notebook", quantity: 1 },
  { productName: "Teclado", quantity: 1 }
];
````

Solução:
````Javascript
const agroupedProducts = cart.reduce((acc, product) => {
  const findProduct = acc.find(item => item.productName === product.productName)

  if (findProduct) {
    findProduct.quantity += product.quantity
  } else {
    acc.push(product)
  }

  return acc
}, [])
````

Resultado esperado:
````Javascript
[
  { "productName": "Notebook", "quantity": 2 },
  { "productName": "Mouse", "quantity": 2 },
  { "productName": "Teclado", "quantity": 1 }
]
````

***
***
***

Exercício 13: Detecção de Produtos Repetidos
Cenário:
Você tem uma lista de funcionários e precisa criar uma lista plana de funcionário e sua devida habilidade.

Dados de entrada:
````Javascript
const employees = [
  { "name": "Carlos", "skills": ["JavaScript", "React"] },
  { "name": "Ana", "skills": ["Java", "Spring"] },
  { "name": "Bruno", "skills": ["Python", "Django"] }
];
````

Solução:
````Javascript
const flatListOfEmployees = employees.flatMap(employee =>
  employee.skills.map(skill => ({
    nome: employee.name,
    skill,
  }))
);
````

Resultado esperado:
````Javascript
[
  { "name": "Carlos", "skill": "JavaScript" },
  { "name": "Carlos", "skill": "React" },
  { "name": "Ana", "skill": "Java" },
  { "name": "Ana", "skill": "Spring" },
  { "name": "Bruno", "skill": "Python" },
  { "name": "Bruno", "skill": "Django" }
]
````
