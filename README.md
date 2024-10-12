# Sistema de Gerenciamento de Pedidos de Restaurante
# Soulstech

## Descrição do Projeto
Este projeto é um sistema de gerenciamento de pedidos para restaurantes, que permite aos clientes navegar pelo menu, realizar pedidos e acompanhar o status dos mesmos. O restaurante pode gerenciar os pedidos recebidos em tempo real e processar pagamentos de forma eficiente.

## Funcionalidades
- **Cadastro de Clientes**: Tela de registro para novos usuários, com validação de dados.
- **Visualização do Menu**: Exibição do menu com itens organizados em categorias e filtrados conforme a preferência do cliente.
- **Realização de Pedidos**: Seleção de itens, revisão e confirmação do pedido.
- **Processamento de Pagamento**: Integração com gateways de pagamento para garantir uma experiência de pagamento segura.
- **Gerenciamento de Pedidos pelo Restaurante**: Controle do restaurante para visualizar, atualizar e gerenciar os pedidos em tempo real.
  
## Backlog da Sprint

### Meta da Sprint 1 - Cadastro de Clientes
- Implementação da tela de cadastro de clientes, com validação de dados e integração com backend.
- Execução de testes unitários para garantir o correto funcionamento do registro.

### Meta da Sprint 2 - Visualização do Menu
- Listagem dos itens do menu com filtros e categorias.
- Interface otimizada para uma navegação rápida e fácil.

### Meta da Sprint 3 - Realização de Pedidos
- Desenvolvimento do fluxo completo para a seleção e confirmação de pedidos.
- Implementação de testes unitários.

### Meta da Sprint 4 - Processamento de Pagamento
- Integração do sistema com gateways de pagamento.
- Testes de segurança e integração com o backend.

### Meta da Sprint 5 - Gerenciamento de Pedidos pelo Restaurante
- Funcionalidade que permite ao restaurante acompanhar e atualizar o status dos pedidos.

## Endpoints da API

### Cadastro de Clientes
- **POST /clientes**
  - Descrição: Criação de um novo cliente no sistema.
  - Parâmetros:
    - `nome`: Nome do cliente.
    - `email`: Email do cliente.
    - `senha`: Senha do cliente.
  - Exemplo de Request:
    ```json
    {
      "nome": "João Silva",
      "email": "joao@example.com",
      "senha": "123456"
    }
    ```
  - Exemplo de Response:
    ```json
    {
      "message": "Cliente cadastrado com sucesso",
      "clienteId": 1
    }
    ```

### Visualização do Menu
- **GET /menu**
  - Descrição: Retorna a listagem de itens do menu com categorias e filtros.
  - Parâmetros: 
    - `categoria` (opcional): Filtra os itens por categoria.
  - Exemplo de Request:
    ```
    GET /menu?categoria=bebidas
    ```
  - Exemplo de Response:
    ```json
    [
      {
        "id": 1,
        "nome": "Pizza Margherita",
        "preco": 29.90,
        "categoria": "Pizzas"
      },
      {
        "id": 2,
        "nome": "Suco de Laranja",
        "preco": 8.90,
        "categoria": "Bebidas"
      }
    ]
    ```

### Realização de Pedidos
- **POST /pedidos**
  - Descrição: Cria um novo pedido no sistema.
  - Parâmetros:
    - `clienteId`: ID do cliente que está realizando o pedido.
    - `itens`: Lista de IDs dos itens do menu e suas respectivas quantidades.
  - Exemplo de Request:
    ```json
    {
      "clienteId": 1,
      "itens": [
        {
          "itemId": 1,
          "quantidade": 2
        },
        {
          "itemId": 3,
          "quantidade": 1
        }
      ]
    }
    ```
  - Exemplo de Response:
    ```json
    {
      "message": "Pedido realizado com sucesso",
      "pedidoId": 101
    }
    ```

### Processamento de Pagamento
- **POST /pagamento**
  - Descrição: Processa o pagamento de um pedido.
  - Parâmetros:
    - `pedidoId`: ID do pedido a ser pago.
    - `metodoPagamento`: Método de pagamento utilizado (ex: "cartao", "pix").
  - Exemplo de Request:
    ```json
    {
      "pedidoId": 101,
      "metodoPagamento": "cartao"
    }
    ```
  - Exemplo de Response:
    ```json
    {
      "message": "Pagamento processado com sucesso"
    }
    ```

### Gerenciamento de Pedidos pelo Restaurante
- **GET /pedidos**
  - Descrição: Retorna a listagem de pedidos pendentes e em andamento para o restaurante.
  - Exemplo de Request:
    ```
    GET /pedidos
    ```
  - Exemplo de Response:
    ```json
    [
      {
        "pedidoId": 101,
        "cliente": "João Silva",
        "status": "Pendente",
        "itens": [
          {
            "nome": "Pizza Margherita",
            "quantidade": 2
          }
        ]
      },
      {
        "pedidoId": 102,
        "cliente": "Maria Souza",
        "status": "Em andamento",
        "itens": [
          {
            "nome": "Lasanha",
            "quantidade": 1
          }
        ]
      }
    ]
    ```

## Tecnologias Utilizadas
- **Frontend**: HTML, CSS, JavaScript, React
- **Backend**: Node.js, Express
- **Banco de Dados**: MySQL
- **Integração de Pagamentos**: Stripe, PayPal

## Instruções de Instalação
1. Clone o repositório:
    ```bash
    git clone https://github.com/seuprojeto.git
    ```
2. Instale as dependências do backend:
    ```bash
    cd backend
    npm install
    ```
3. Instale as dependências do frontend:
    ```bash
    cd frontend
    npm install
    ```
4. Inicie o servidor backend:
    ```bash
    npm start
    ```
5. Inicie o servidor frontend:
    ```bash
    npm start
    ```

## Testes
- Testes unitários foram implementados usando **Jest**.
- Para rodar os testes:
    ```bash
    npm test
    ```

## Contribuições
- Pull requests são bem-vindos. Para grandes mudanças, por favor, abra uma issue primeiro para discutir o que você gostaria de mudar.
