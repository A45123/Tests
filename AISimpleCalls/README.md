# Assignment Tutorial 4 - AISimpleCalls (AI Assistant)
[![IntelliJ IDEA](https://img.shields.io/badge/IDE-IntelliJ%20IDEA-blue)](#)
[![Kotlin](https://img.shields.io/badge/Language-Kotlin-orange)](#)

Course: Licenciatura em Engenharia Informática e Multimédia <br>
Student(s): 45123 <br>
Date: 12/04/2026 <br>
Repository URL: [AISimpleCalls](https://github.com/A45123/DAM/tree/main/Tutorial4-KotlinFlows/AISimpleCalls) <br>

---

## 📖 1. Introduction

O objetivo deste projeto é desenvolver um Assistente de IA polimórfico capaz de interagir com as APIs da **OpenAI (GPT)** e **Google (Gemini)**.

A aplicação explora a integração com APIs REST, serialização de dados com GSON e a parametrização de modelos de linguagem para diferentes tipos de tarefas, como chat simples e análise de sentimento.

---

## 🖥️ 2. System Overview

A aplicação é um programa de consola em Kotlin que utiliza uma arquitetura baseada em interfaces para abstrair o fornecedor de IA.

Principais componentes:
- **AIAssistant** – Interface base que define as operações de chamada à API.
- **AIAssistantOpenAI / AIAssistantGemini** – Implementações específicas que lidam com os diferentes formatos de JSON de cada API.
- **AIAssistantFactory** – Implementação do padrão Factory para instanciar o assistente configurado.
- **Main** – Ciclo principal de interação com o utilizador.

---

## 🏗️ 3. Architecture and Design

```
kotlin
├── AIAssistant.kt
├── AIAssistantFactory.kt
├── AIAssistantOpenAI.kt
├── AIAssistantGemini.kt
└── Main.kt
```

Conceitos aplicados:
- **Polimorfismo:** Abstração dos detalhes da API atrás de uma interface comum.
- **Factory Pattern:** Criação dinâmica de instâncias com base na configuração.
- **Serialization (JSON):** Uso de GSON tanto para construção manual de JSON como para mapeamento em Data Classes.
- **Retry Logic:** Implementação de mecanismos de repetição em caso de falha de rede ou rate limit.

---

## ⚙️ 4. Implementation

### 4.1. Multi-Provider Integration
Suporte para OpenAI e Gemini utilizando as versões `-CLASSES` (typed data classes) e versões base (JSON manual).

### 4.2. Configuration Management
Parametrização do sistema através de `config.properties`, permitindo definir:
- `AI_LLM`: Escolha do modelo (OPENAI, GEMINI, etc).
- `TEMPERATURE`: Controlo da criatividade das respostas.
- `MAX_TOKENS`: Limite de tamanho da resposta.

### 4.3. Sentiment Analysis
Implementação de um motor de análise de sentimento que avalia o input numa escala de 7 pontos (Very Negative a Very Positive) e retorna uma justificação estruturada em JSON.

### 4.4. Temperature Tests
Realização de testes comparativos para demonstrar como o parâmetro `temperature` afeta a determinismo e a criatividade do modelo (0.0, 0.5, 1.0).

---

## 🔍 5. Testing and Validation

- **Testes de Integração:** Chamadas reais às APIs para verificar a conectividade e parsing.
- **Unit Tests:** Verificação da lógica de construção de prompts e processamento de respostas JSON.
- **Sentiment Tests:** Validação do formato de saída JSON e da coerência das classificações.

---

## 📝 6. Usage Instructions

- Adicionar as chaves de API (`OPENAI_API_KEY`, `GEMINI_API_KEY`) ao ficheiro `config.properties`.
- Configurar o modelo pretendido no mesmo ficheiro.
- Executar `./gradlew run` para iniciar o chat.
- Para análise de sentimento, prefixar o input com `sentiment:`.

---

# Autonomous Software Engineering Sections- only for [AC YES, AI YES] sections

Nesta parte do trabalho, foi permitido o uso de ferramentas de assistência (AC YES, AI YES) para auxiliar na implementação das estruturas de dados complexas das APIs e na lógica de retry.

---

# Development Process

## 📦 12. Version Control and Commit History

O histórico de commits reflete a adição incremental de funcionalidades: primeiro a integração base, seguida pela parametrização e finalmente as capacidades de análise avançada.

---

## 🌱 13. Difficulties and Lessons Learned

### 13.1 Dificuldades
- Lidar com as diferenças estruturais entre o JSON da OpenAI e do Gemini.
- Implementar o parsing robusto da análise de sentimento quando o modelo falha em retornar JSON puro.
- Gestão de rate limits das contas gratuitas das APIs.

### 13.2 Lições Aprendidas
- Vantagens de utilizar Data Classes para serialização em vez de manipulação manual de strings JSON.
- A importância da parametrização (tokens, temperatura) para obter resultados consistentes.

---

## 🔧 14. Future Improvements
- Adicionar suporte para processamento de imagens (Gemini Pro Vision).
- Implementar histórico de conversa (memória de contexto).
- Interface gráfica básica.

---

## ⚠️ 15. AI Usage Disclosure (Mandatory)

Foram utilizadas ferramentas de IA (GitHub Copilot/ChatGPT) para agilizar o mapeamento das classes de resposta das APIs e para sugestões de prompts de análise de sentimento.
