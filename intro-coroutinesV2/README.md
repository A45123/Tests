# Assignment Tutorial 4 - intro-coroutinesV2 (Kotlin Flows)
[![IntelliJ IDEA](https://img.shields.io/badge/IDE-IntelliJ%20IDEA-blue)](#)
[![Kotlin](https://img.shields.io/badge/Language-Kotlin-orange)](#)

Course: Licenciatura em Engenharia Informática e Multimédia <br>
Student(s): 45123 <br>
Date: 12/04/2026 <br>
Repository URL: [intro-coroutinesV2](https://github.com/A45123/DAM/tree/main/Tutorial4-KotlinFlows/intro-coroutinesV2) <br>

---

## 📖 1. Introduction

O objetivo desta parte do trabalho é transformar uma aplicação que utiliza pedidos de rede bloqueantes numa aplicação responsiva e concorrente utilizando **Kotlin Coroutines** e **Channels**.

Posteriormente, o projeto foi refatorado para utilizar uma abordagem mais reativa através de **StateFlow** para a gestão de estados de carregamento (Loading Status).

Principais objetivos:
- Utilizar `suspend` functions para operações de rede.
- Implementar execução concorrente com corrotinas.
- Utilizar `StateFlow` para observar e reagir a mudanças de estado.
- Implementar `Channels` para gerir o fluxo de progresso entre o processamento e a UI.

---

## 🖥️ 2. System Overview

O sistema baseia-se num tutorial da JetBrains que utiliza uma interface Swing para listar contribuidores de repositórios do GitHub. A versão V2 foca-se na modernização da gestão de estado e comunicação assíncrona.

Principais componentes:
- **Contributors** – Interface e lógica base para obtenção de dados.
- **ContributorsUI** – Implementação da interface gráfica e gestão de subscrições aos fluxos de dados.
- **LoadingStateData** – Modelo de dados para representar o estado da operação.

---

## 🏗️ 3. Architecture and Design

```
kotlin
├── Contributors.kt
├── ContributorsUI.kt
└── GitHubService.kt
```

Conceitos aplicados:
- **Backing Property Pattern:** Uso de `MutableStateFlow` privado e `StateFlow` público.
- **Cold Flows vs Hot Flows:** Transição para `StateFlow` (hot) para estado da UI.
- **Channels:** Uso de canais para desacoplar a produção de progresso do seu consumo na UI.

---

## ⚙️ 4. Implementation

### 4.1. Task 1: LoadingStateData
Implementação de uma `data class` para encapsular o estado (`INIT`, `IN_PROGRESS`, `COMPLETED`, `CANCELED`), tempo de início e tempo decorrido.

### 4.2. Task 2: StateFlow & MutableStateFlow
Aplicação do padrão de propriedade de suporte no `ContributorsUI` para expor o estado de forma imutável, permitindo que a UI observe as mudanças de forma reativa.

### 4.3. Task 3: Reactive UI Updates
Atualização dos métodos de gestão de estado para emitir novos valores no fluxo e implementação de um `collector` que atualiza os componentes Swing (texto e ícone de loading) automaticamente.

### 4.4. Step 3: Progress with Channels
Refatoração da variante `CHANNELS` para utilizar um canal intermédio. Isto permite um melhor controlo de fluxo (back-pressure) e separação de interesses entre a lógica de negócio e a atualização da interface.

---

## 🔍 5. Testing and Validation

O projeto foi validado verificando:
- A interface não bloqueia durante os pedidos de rede.
- O estado de "Loading" é corretamente refletido na UI em todas as fases.
- O progresso intermédio é exibido corretamente sem sobrecarregar a UI thread.
- O cancelamento de pedidos funciona conforme esperado, fechando os canais e parando as corrotinas.

---

## 📝 6. Usage Instructions

- Abrir o projeto no IntelliJ IDEA.
- Configurar a API Key do GitHub (opcional, para evitar rate limits).
- Executar a classe `Main` em `src/main/kotlin`.
- Selecionar a variante de execução (ex: `CHANNELS` ou `STATE_FLOW`) e clicar em `Load`.

---

# Autonomous Software Engineering Sections- only for [AC NO, AI NO] sections

Esta secção não se aplica a este trabalho, uma vez que o enunciado indica explicitamente **AC NO** e **AI NO** para esta parte do tutorial.

---

# Development Process

## 📦 12. Version Control and Commit History

Utilizou-se Git para o controlo de versões, focando em commits granulares para cada tarefa de refatoração reativa.

---

## 🌱 13. Difficulties and Lessons Learned

### 13.1 Dificuldades
- Compreender a diferença prática entre `Flow` e `StateFlow`.
- Implementar o `Backing Property Pattern` corretamente para garantir o encapsulamento.
- Gerir a concorrência no acesso à UI thread a partir de canais.

### 13.2 Lições Aprendidas
- A importância da programação reativa para interfaces de utilizador fluidas.
- Como os `Channels` simplificam a comunicação entre corrotinas.
- Melhores práticas de estruturação de código assíncrono em Kotlin.

---

## 🔧 14. Future Improvements
- Implementar `SharedFlow` para eventos únicos (como erros).
- Adicionar testes unitários utilizando `runTest`.
- Migrar a interface de Swing para Jetpack Compose for Desktop.

---

## ⚠️ 15. AI Usage Disclosure (Mandatory)

Não foram utilizadas ferramentas de IA generativa para o desenvolvimento desta parte do código, seguindo as diretrizes de [AC NO, AI NO].
