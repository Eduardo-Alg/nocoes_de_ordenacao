# 🧪 Testando Desempenho - 🔢 Algorítmos de Ordenação 

## 🚀 Tecnologias Utilizadas
- 🐍 **Linguagem:** Python 3.x💻
- 📚 **Bibliotecas:** Random, Datetime, Time, Matplotlib, Sys, String
- 💻 **Ambiente de Execução:** Jupyther Notebook / Google Colab

## 📂 Estrutura do Projeto
```
└── sample_data 
  ├── anscombe.json 
  ├── california_housing_test.csv 
  ├── california_housing_train.csv 
  ├── mnist_test.csv 
  ├── mnist_train_small.csv 
  └── README.md
```

## ⚙️ Execução
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Eduardo-Alg/nocoes_de_ordenacao/blob/main/A4__NO%C3%87%C3%95ES_DE_ORDENA%C3%87%C3%83O.ipynb)

## 📊 Exemplo de uso
Para executar o projeto no **Google Colab:**

1º **Gere lista de produtos executando a celula abaixo**:
```
import random
import datetime
import time
import matplotlib.pyplot as plt
import sys
import string

sys.setrecursionlimit(5000)

class Produto:
    def __init__(self, nome, preco, avaliacao, data_adicao, categoria):
        self.nome = nome
        self.preco = preco
        self.avaliacao = avaliacao
        self.data_adicao = data_adicao
        self.categoria = categoria

    def __repr__(self):
        return f"{self.nome}: $ {self.preco}, {self.avaliacao}, {self.data_adicao}, {self.categoria}"

def gerar_produtos(n):
    nomes = [f"Produto{i}" for i in range(n)]
    precos = [round(random.uniform(10, 1000), 2) for _ in range(n)]
    avaliacoes = [round(random.uniform(0, 5), 2) for _ in range(n)]
    datas = [(datetime.datetime.now() - datetime.timedelta(days=random.randint(0, 365))).date() for _ in range(n)]
    categorias = [f"{n}{i//26 or ''}" for i, n in enumerate(string.ascii_uppercase * n)]
    produtos = [Produto(nomes[i], precos[i], avaliacoes[i], datas[i], categorias[i]) for i in range(n)]
    return produtos

produtos = gerar_produtos(1000)

for produto in produtos[:10]:  # Mostrar os 10 primeiros produtos
    print(produto)

```
2º **Execute o algorítmo de ordenação desejado.**
```
# - Por preço (ascendente e descendente)
preco_ascendente = lambda: bubble_sort(produtos, "preco")
preco_descendente = lambda: bubble_sort(produtos, "preco", reverse=True)

# - Por avaliação (ascendente e descendente)
avaliacao_ascendente = lambda: bubble_sort(produtos, "avaliacao")
avaliacao_descendente = lambda: bubble_sort(produtos, "avaliacao", reverse=True)

# - Por data de adição (mais recente e mais antiga)
data_ascendente = lambda: bubble_sort(produtos, "data_adicao")
data_descendente = lambda: bubble_sort(produtos, "data_adicao", reverse=True)

# - Por categoria (ordem alfabética)
categoria = lambda: bubble_sort(produtos, "categoria")
```
3º **Exemplo de Execução**
```
preco_ascendente()

for produto in produtos[:10]:
    print(produto)
```

🖥️ **Saída esperada**:
```
Produto577: $ 10.73, 0.99, 2025-05-20, F22
Produto98: $ 12.08, 1.59, 2025-02-28, U3
Produto546: $ 13.53, 2.6, 2025-01-30, A21
Produto561: $ 13.7, 2.95, 2024-12-24, P21
Produto804: $ 15.0, 0.33, 2025-07-05, Y30
Produto286: $ 15.86, 2.36, 2025-08-12, A11
Produto947: $ 19.18, 3.53, 2025-08-04, L36
Produto680: $ 19.3, 1.91, 2025-02-22, E26
Produto813: $ 21.01, 1.08, 2025-08-05, H31
Produto456: $ 21.27, 4.4, 2025-08-05, O17
```

## 📈 Resultados / Visualizações

![Distribuição de Preços](<img width="986" height="548" alt="grafico_bubble_sort" src="https://github.com/user-attachments/assets/5d2540a7-3d3b-4581-a34e-1b2bca1b07ef" />
)
