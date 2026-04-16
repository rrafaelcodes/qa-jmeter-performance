# 🚀 Teste de Performance e Carga em API (JMeter)

## 🎯 Objetivo do Projeto
Este projeto prático foi desenvolvido para validar a estabilidade, o tempo de resposta e os contratos (Status Codes) da API pública `jsonplaceholder.typicode.com` sob condições de estresse simulado, utilizando o Apache JMeter. O objetivo é garantir que a aplicação backend suporte o tráfego esperado executando um fluxo completo de ponta a ponta sem degradação de performance.

## 🛠️ Ferramentas Utilizadas
* **Apache JMeter:** Configuração de Threads, Samplers, Timers, HTTP Header Manager e Listeners.
* **API Alvo:** `https://jsonplaceholder.typicode.com`

## 📊 Cenário de Teste (Jornada do Usuário)
Foi configurado um cenário de carga simulando o fluxo real de um usuário com as seguintes características:
* **Usuários Simultâneos (Threads):** 50
* **Tempo de Inicialização (Ramp-up):** 10 segundos
* **Think Time (Temporizador):** Pausa constante de 1.5s entre cada requisição para simular o comportamento humano real de navegação.
* **Total de Amostras Disparadas:** 150 requisições na jornada.

### 🔄 Fluxo Validado:
1. **Listar Usuários (GET):** Busca de dados no endpoint `/users`. Validação de Status Code `200 OK`.
2. **Criar Usuário (POST):** Envio de payload JSON simulando cadastro. Validação de Status Code `201 Created`.
3. **Atualizar Usuário (PUT):** Edição de cadastro via JSON no endpoint `/users/2`. Validação de Status Code `200 OK`.

## 📈 Resultados Obtidos
A API demonstrou resiliência total sob a carga estipulada para a jornada, apresentando tempos de resposta excelentes e sem quebra de contratos:

* **Taxa de Erro:** 0,00% (Todas as 150 requisições passaram nas Asserções de segurança e contrato).
* **Tempo Médio de Resposta (Total):** 123 ms.
* **Pico Máximo de Estresse:** 402 ms (Registrado no método GET).
* **Desempenho por Rota:**
  * **GET (Listar):** Média de 76 ms.
  * **POST (Criar):** Média de 140 ms.
  * **PUT (Atualizar):** Média de 154 ms.

* <img width="1518" height="824" alt="image" src="https://github.com/user-attachments/assets/21676735-5b01-4340-a73e-1510ade5975b" />
<img width="1523" height="821" alt="image" src="https://github.com/user-attachments/assets/935390f8-a3cf-44fb-834d-be5106a1a050" />
