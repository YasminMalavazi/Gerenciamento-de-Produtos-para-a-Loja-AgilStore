# Gerenciamento-de-Produtos-para-a-Loja-AgilStore
# AgilStore Inventory Management API

Esta API fornece funcionalidades básicas para o gerenciamento de produtos na loja AgilStore. Utiliza Flask como framework e persiste os dados em um arquivo JSON.

## Funcionalidades

1. **Adicionar Produto**
   - **Endpoint**: `POST /products`
   - **Descrição**: Adiciona um novo produto ao inventário.
   - **Exemplo de Payload**:
     ```json
     {
       "name": "Smartphone",
       "category": "Electronics",
       "quantity": 10,
       "price": 799.99
     }
     ```

2. **Listar Produtos**
   - **Endpoint**: `GET /products`
   - **Descrição**: Lista todos os produtos no inventário.
   - **Parâmetros opcionais**:
     - `category`: Filtra por categoria.
     - `sort_by`: Ordena por `name`, `quantity` ou `price`.

3. **Atualizar Produto**
   - **Endpoint**: `PUT /products/<product_id>`
   - **Descrição**: Atualiza informações de um produto existente.
   - **Exemplo de Payload**:
     ```json
     {
       "name": "Updated Smartphone",
       "quantity": 15
     }
     ```

4. **Excluir Produto**
   - **Endpoint**: `DELETE /products/<product_id>`
   - **Descrição**: Remove um produto do inventário.

5. **Buscar Produto**
   - **Endpoint**: `GET /products/search`
   - **Descrição**: Busca produtos por `id` ou parte do nome.
   - **Parâmetros**:
     - `q`: Query de busca.

## Persistência de Dados

Os produtos são salvos no arquivo `inventory.json` no diretório do projeto.

## Tecnologias Utilizadas

- **Python 3.8+**
- **Flask**

## Como Rodar o Projeto

1. **Clone o repositório**:
   ```bash
   git clone <url-do-repositorio>
   cd <nome-do-repositorio>
   ```

2. **Instale as dependências**:
   ```bash
   pip install flask
   ```

3. **Inicie o servidor**:
   ```bash
   python app.py
   ```

4. **Use uma ferramenta como Postman ou cURL para interagir com a API**.

## Exemplo de Requisições com cURL

- **Adicionar Produto**:
  ```bash
  curl -X POST http://127.0.0.1:5000/products \
       -H "Content-Type: application/json" \
       -d '{"name": "Smartphone", "category": "Electronics", "quantity": 10, "price": 799.99}'
  ```

- **Listar Produtos**:
  ```bash
  curl http://127.0.0.1:5000/products
  ```

- **Atualizar Produto**:
  ```bash
  curl -X PUT http://127.0.0.1:5000/products/<product_id> \
       -H "Content-Type: application/json" \
       -d '{"name": "Updated Smartphone", "quantity": 15}'
  ```

- **Excluir Produto**:
  ```bash
  curl -X DELETE http://127.0.0.1:5000/products/<product_id>
  ```

- **Buscar Produto**:
  ```bash
  curl http://127.0.0.1:5000/products/search?q=Smartphone
  ```

