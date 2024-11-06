# API Cepify

**API Cepify** é uma API desenvolvida com Laravel para consulta de dados de endereço a partir de um CEP. O objetivo desse projeto é fornecer uma maneira simples de acessar informações sobre um CEP, como rua, bairro, cidade e estado, a partir de uma integração com a API externa ViaCEP.

## Tecnologias Utilizadas

- **Backend**: Laravel (PHP)
- **Frontend** (Opcional): Vue.js
- **API Externa**: ViaCEP (https://viacep.com.br/ws/)
- **Gerenciamento de Dependências**: Composer (Laravel), npm (Vue.js)

## Como Rodar o Projeto

### Backend (Laravel)

1. Clone o repositório para sua máquina:
   ```bash
   git clone https://github.com/davicardososantos/API-Cepify.git
   

2. Instale as dependências do Laravel:
   ```bash
   cd API-Cepify
   composer install
   ```

3. Configure o arquivo `.env` (sem necessidade de banco de dados para este projeto).

4. Inicie o servidor local:
   ```bash
   php artisan serve
   ```

5. A API estará disponível em `http://127.0.0.1:8000`.

### Frontend (Vue.js)

1. Instale as dependências do Vue.js:
   ```bash
   cd resources/js
   npm install
   ```

2. Inicie o servidor de desenvolvimento Vue:
   ```bash
   npm run dev
   ```

3. A SPA Vue estará disponível em `http://localhost:8080`.

## Endpoints da API

### `GET /api/consulta-cep/{cep}`
Retorna os dados de endereço para o CEP fornecido.

- **Parâmetros**: 
  - `cep` (obrigatório): O CEP a ser consultado (somente números).
  
- **Exemplo de Requisição**:
  ```bash
  GET http://127.0.0.1:8000/api/consulta-cep/01001000
  ```

- **Exemplo de Resposta**:
  ```json
  {
    "logradouro": "Praça da Sé",
    "bairro": "Sé",
    "localidade": "São Paulo",
    "uf": "SP"
  }
  ```

- **Tratamento de Erros**:
  - Se o CEP for inválido ou não encontrado, a API retornará:
    ```json
    {
      "error": "CEP inválido ou não encontrado."
    }
    ```

## Como Contribuir
    1. Fork este repositório.
    2. Crie uma branch para sua feature (`git checkout -b feature-nova`).
    3. Faça o commit das suas alterações (`git commit -am 'Adiciona nova feature'`).
    4. Push para a branch (`git push origin feature-nova`).
    5. Abra um Pull Request.
