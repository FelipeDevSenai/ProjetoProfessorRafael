Entendendo Algoritmos | Exemplos em Python

Este repositório contém implementações básicas dos algoritmos apresentados no livro Entendendo Algoritmos, com foco em estruturas de busca, lembrando que esse trabalho/projeto foi orientado Pelo professor Rafael. ✍🏼

👨 Nome
Felipe Batista Miranda  
👨‍🏫 Professor
Rafael
Disciplina: Sistemas Operacionais/PM

---

1) 🔍 Busca Linear
   O que é?
A busca linear percorre todos os elementos de uma lista até encontrar o valor desejado.  
É simples, mas pode ser lenta para listas muito grandes.

Código 1.0 (Python)
```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1

Exemplos ->
lista = [10, 20, 30, 40, 50]
print("Busca Linear:", linear_search(lista, 30))  # retorna índice 2
Saída esperada
Busca Linear: 2

2) Código 2.0
🔎 Busca Binária
 O que é?
A busca binária é muito mais rápida, mas só funciona em listas ordenadas.
A cada passo, divide a lista ao meio até encontrar o valor ou terminar a busca.

Código (Python)
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1

Mais alguns Exemplos
lista = [1, 3, 5, 7, 9, 11]
print("Busca Binária:", binary_search(lista, 7))  # retorna índice 3
Saída esperada
Busca Binária: 3

3) Busca Não Linear (Árvore Binária de Busca)
 O que é?
A árvore binária de busca (BST) organiza dados de forma hierárquica.
Cada nó pode ter até dois filhos, e a busca segue pela esquerda (se menor) ou direita (se maior).

Código (Python)
class Node:
    def _init_(self, key):
        self.key = key
        self.left = None
        self.right = None

def insert(root, key):
    if root is None:
        return Node(key)
    if key < root.key:
        root.left = insert(root.left, key)
    else:
        root.right = insert(root.right, key)
    return root

def search(root, key):
    if root is None or root.key == key:
        return root
    if key < root.key:
        return search(root.left, key)
    return search(root.right, key)

Alguns exemplos e considerações Finais
root = Node(10)
insert(root, 5)
insert(root, 15)
insert(root, 7)

res = search(root, 7)
print("Busca Não Linear:", "Encontrado" if res else "Não encontrado")
Saída esperada
Busca Não Linear: Encontrado
