# Assignment Tutorial 4 - Kotlin Flows, AI LLMs & Firebase
[![IntelliJ IDEA](https://img.shields.io/badge/IDE-IntelliJ%20IDEA-blue)](#)
[![Android Studio](https://img.shields.io/badge/IDE-Android%20Studio-green)](#) 
[![Kotlin](https://img.shields.io/badge/Language-Kotlin-orange)](#)
[![Version](https://img.shields.io/badge/API-24%2B-blue)](#)

Course: Licenciatura em Engenharia Informática e Multimédia <br>
Student(s): 45123 <br>
Date: 12/04/2026 <br>
Repository URL: [Tutorial4-KotlinFlows](https://github.com/A45123/DAM/tree/main/Tutorial4-KotlinFlows) <br>

---

## 📖 1. Introduction

Este repositório reúne os projetos desenvolvidos durante o **Tutorial 4** da unidade curricular de **Desenvolvimento de Aplicações Móveis**.

O foco deste conjunto de trabalhos foi a exploração de **Kotlin Flows**, integração com APIs de **Large Language Models (LLMs)** e a utilização da plataforma **Google Firebase**.

Os objetivos principais foram:

* Implementar concorrência e código assíncrono com **Coroutines, Flows e Channels**.
* Desenvolver um assistente de IA capaz de interagir com **OpenAI GPT** e **Google Gemini**.
* Configurar e utilizar serviços do **Firebase** (Auth, Firestore, Realtime Database, Storage).
* Aplicar padrões de design reativos para gestão de estado na UI.

---

# Projetos

## [intro-coroutinesV2](https://github.com/A45123/DAM/tree/main/Tutorial4-KotlinFlows/intro-coroutinesV2) — Reactive State Management

Evolução de um tutorial de corrotinas para uma arquitetura reativa utilizando **StateFlow** e **Channels**.

* **Loading Status com StateFlow:** Substituição da gestão manual de estado por um fluxo reativo, garantindo encapsulamento e atualizações automáticas da UI.
* **Progress Updates com Channels:** Implementação de canais para gerir o fluxo de dados entre o processamento em background e a interface, lidando com back-pressure de forma robusta.

---

## [AISimpleCalls](https://github.com/A45123/DAM/tree/main/Tutorial4-KotlinFlows/AISimpleCalls) — AI Assistant Console App

Aplicação de consola em Kotlin que demonstra a integração polimórfica com múltiplos provedores de LLM.

* **Multi-Provider Support:** Arquitetura flexível para alternar entre OpenAI e Google Gemini.
* **Temperature & Token Control:** Configuração dinâmica de parâmetros de geração através de ficheiros de propriedades.
* **Sentiment Analysis:** Motor de análise de sentimento com escala de 7 pontos e justificação estruturada em JSON.
* **Serialization:** Uso de **GSON** com Data Classes para comunicação type-safe com as APIs REST.

---

## [Firebase Projects](https://github.com/A45123/DAM/tree/main/Tutorial4-KotlinFlows) — Android Cloud Integration

Conjunto de aplicações Android demonstrando o poder do ecossistema Firebase.

* **Friendly Chat (build-android-start):** App de mensagens em tempo real utilizando **Authentication**, **Realtime Database** e **Cloud Storage**.
* **Notes Pro (NotesProXMLViews3):** Gestor de notas com persistência em **Cloud Firestore** e suporte para autenticação por email.
* **GOAT Feature:** Extensão da aplicação de notas para suportar imagens e funcionalidades avançadas de organização.

---

# Repository Structure

```
.
├── intro-coroutinesV2 (Kotlin Flows & Coroutines)
├── AISimpleCalls (AI Assistant console app)
├── build-android-start (Firebase Friendly Chat)
└── NotesProXMLViews3 (Firebase Notes Pro)
```

---