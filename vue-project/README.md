 # Calculadora Windows 95 com Vue.js 

Este é um projeto de uma calculadora moderna inspirada no design clássico da interface do usuário das calculadoras Windows 95. O projeto foi desenvolvido usando Vue.js para a lógica do aplicativo e Tailwind CSS para estilização.

## Visão Geral

Este projeto é um exemplo de como você pode criar uma aplicação web moderna com um design retro utilizando tecnologias atuais. A calculadora permite realizar operações básicas de adição, subtração, multiplicação e divisão.

## Funcionalidades

- **Adição**: Soma dois valores.
- **Subtração**: Subtrai o segundo valor do primeiro.
- **Multiplicação**: Multiplica dois valores.
- **Divisão**: Divide o primeiro valor pelo segundo (com verificação para evitar divisão por zero).
- **Design Retro**: Inspirado no design clássico das calculadoras Windows 95, com um layout amigável e fácil de usar.

## Tecnologias Utilizadas

- **Vue.js**: Framework JavaScript para construção de interfaces de usuário.
- **Tailwind CSS**: Framework de utilitários CSS flexível e responsivo.
- **HTML/CSS**: Para estrutura e estilização da aplicação.

## Instalação

1. Clone este repositório:
    ```bash
    git clone https://github.com/seu-usuario/calculadora-windows95.git
    cd calculadora-windows95
    ```

2. Instale as dependências:
    ```bash
    npm install
    ```

3. Inicie o servidor de desenvolvimento:
    ```bash
    npm run serve
    ```

## Estrutura do Projeto

A estrutura do projeto é organizada da seguinte forma:

```
calculadora-windows95/
├── public/
│   └── index.html          # Arquivo HTML principal
├── src/
│   ├── assets/             # Assets (imagens, ícones)
│   ├── components/         # Componentes Vue.js
    └── Cabeçalho.vue         # Componente principal
    └── Calculadora.vue       # Componente principal
    └── Rodapé.vue            # Componente principal
│   └── App.vue         # Componente principal
│   ├── main.js             # Ponto de entrada do aplicativo
│   
├── index.html              # Arquivo HTML principal
├── package.json            # Gerenciamento de pacotes
├── README.md               # Documentação do projeto

```

## Como Usar

1. **Adição**: Insira dois valores e clique no botão "+".
2. **Subtração**: Insira dois valores e clique no botão "-".
3. **Multiplicação**: Insira dois valores e clique no botão "x".
4. **Divisão**: Insira dois valores e clique no botão "/".
5. O resultado será exibido na seção de resultados abaixo dos inputs.

## Personalização

Você pode personalizar o estilo da calculadora modificando os arquivos CSS ou utilizando classes utilitárias do Tailwind CSS conforme necessário.

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests para melhorar este projeto.

## Licença

Este projeto é licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para mais detalhes.
