# Teste de Performance com K6


💡 Esse projeto foi construído acompanhando o curso Teste de Performance com K6 do professor Marlo Henrique de Oliveira. Com esse material, consegui reforçar conceitos já vistos em um primeiro curso básico que fiz e consegui também evoluir no desenvolvimento de scripts de testes de Performance. Nesse projeto, é possível verificar testes de carga, stress, fumaça na API disponibilizada pelo próprio k6: https://test-api.k6.io/. Com ela, foram realizados testes tanto em API publica quanto API privada.


## 🔖 Cenários de Teste

### Cenário 1: Teste de fumaça - API Publica --> Arquivo smoke-test.js
    - Buscar todos os crocodilos na API
    - Critérios:
        - 1 usuário por 30 segundos.
    - Limites: 
        - 99% das requisições com sucesso.


### Cenário 2: Teste de Carga - API Publica --> Arquivo load-test-id.js
    - Buscar crocodilo por ID
    - Critérios:
        - Ramp up 10 Vus em 10 segundos;
        - Carga de 10 Vus por 10 segundos;
        - Ramp Down 0 Vus em 10 segundos.
    - Limites:
        - Requisição com sucesso > 95%;
        - Tempo de requisição p(90) < 200ms.

### Cenário 3: Teste de Carga - API Publica --> Arquivo load-test-register.js
    - Realizar registro de novo usuário
    - Critérios:
        - Carga de 10 Vus por 10 segundos;
    - Limites:
        - Requisição com falha inferior a 1%;
        - Tempo de requisição p(95) < 500ms;
        - Requisição com sucesso superior a 95%.

### Cenário 4: Teste de Stress - API Publica --> Arquivo stress-test.js
    - Realizar login com novo usuário
    - Critérios:
        - Ramp up 5 Vus em 5 segundos;
        - Carga 5 Vus por 5 segundos;
        - Ramp up 50 Vus em 2 segundos;
        - Carga 50 Vus por 5 segundos;
        - Ramp Down 0 Vus em 5 segundos.
    - Limites:
        - Requisição com falha inferior a 1%;

### Cenário 5: Teste de Carga - API Privada --> Arquivo load-test-private.js
    - Realizar login com novo usuário
    - Critérios:
        - Carga de 10 Vus por 10 segundos;
    - Limites:
        - Requisição com falha inferior a 1%;
        - Duração da requisição p(95) inferior a 250ms;

## Informações sobre o projeto

📌 Na pasta tests são encontrados os cenários de testes;

📌 Na pasta tests/results são encontrados os relatórios de testes;

📌 Na pasta tests/fixtures são encontradas as massas de testes utilizadas no projeto.


## Execução do projeto

📌 Para executar o projeto, basta fazer o clone do repositório e ter o K6 instalado na máquina.
