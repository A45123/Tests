# Assignment Tutorial 4 - Friendly Chat (Firebase)
[![Android Studio](https://img.shields.io/badge/IDE-Android%20Studio-green)](#)
[![Kotlin](https://img.shields.io/badge/Language-Kotlin-orange)](#)
[![Firebase](https://img.shields.io/badge/Platform-Firebase-yellow)](#)

Course: Licenciatura em Engenharia Informática e Multimédia <br>
Student(s): 45123 <br>
Date: 12/04/2026 <br>
Repository URL: [FriendlyChat](https://github.com/A45123/DAM/tree/main/Tutorial4-KotlinFlows/build-android-start) <br>

---

## 📖 1. Introduction

O objetivo deste projeto é implementar uma aplicação de mensagens em tempo real integrada com o ecossistema **Firebase**.

O trabalho baseia-se no codelab "Friendly Chat" e demonstra a integração de autenticação, base de dados em tempo real e armazenamento de ficheiros na nuvem.

---

## 🖥️ 2. System Overview

A aplicação permite que os utilizadores façam login, enviem mensagens de texto e partilhem imagens que são sincronizadas instantaneamente entre todos os clientes ligados.

Principais funcionalidades:
- Autenticação de utilizadores.
- Sincronização de mensagens em tempo real.
- Upload e visualização de imagens.
- Personalização básica da interface.

---

## 🏗️ 3. Architecture and Design

A aplicação utiliza uma arquitetura baseada em XML Views com integração direta dos SDKs do Firebase.

Serviços utilizados:
- **Firebase Authentication:** Gestão de login via Email/Password.
- **Firebase Realtime Database:** Armazenamento e sincronização de mensagens JSON.
- **Cloud Storage for Firebase:** Armazenamento de imagens enviadas pelos utilizadores.

---

## ⚙️ 4. Implementation

### 4.1. Firebase Configuration
Configuração do projeto na consola do Firebase e integração do ficheiro `google-services.json` no módulo da aplicação.

### 4.2. User Authentication
Implementação do fluxo de login. Foi resolvido um bug visual na `SignInActivity` onde a ActionBar sobrepunha o campo de email, através da utilização temporária de um tema `NoActionBar`.

### 4.3. Realtime Messaging
Uso do `FirebaseRecyclerAdapter` para ligar as mensagens da base de dados diretamente à `RecyclerView`, garantindo atualizações automáticas sempre que uma nova mensagem é inserida.

### 4.4. Image Sharing
Integração com o seletor de imagens do sistema e upload para o Cloud Storage, seguido da gravação do URL da imagem na base de dados para visualização pelos outros utilizadores.

---

## 🔍 5. Testing and Validation

- Validação do fluxo de registo e login de novos utilizadores.
- Teste de latência na receção de mensagens entre múltiplos dispositivos/emuladores.
- Verificação da persistência das imagens no Cloud Storage.
- Teste de regras de segurança básicas na consola do Firebase.

---

## 📝 6. Usage Instructions

- Colocar o ficheiro `google-services.json` válido na pasta `app/`.
- Ativar Authentication (Email/Password), Realtime Database e Cloud Storage na consola do Firebase.
- Executar a aplicação num emulador ou dispositivo Android (API 24+).

---

# Autonomous Software Engineering Sections- only for [AC YES, AI NO] sections

Foi permitido o uso de ferramentas de auto-complete (AC YES) para agilizar o uso das APIs do Firebase, mas a lógica de integração foi desenvolvida sem auxílio de IA geradora de código (AI NO).

---

# Development Process

## 📦 12. Version Control and Commit History

O desenvolvimento seguiu os passos do codelab, com commits focados em cada serviço do Firebase adicionado.

---

## 🌱 13. Difficulties and Lessons Learned

### 13.1 Dificuldades
- Configuração correta das permissões e regras de segurança no Firebase.
- Resolução de conflitos de UI entre o tema da aplicação e a biblioteca de autenticação.

### 13.2 Lições Aprendidas
- Facilidade de escalar aplicações móveis utilizando serviços Backend-as-a-Service (BaaS).
- Importância da sincronização em tempo real para experiências de utilizador colaborativas.

---

## 🔧 14. Future Improvements
- Adicionar login via Google e GitHub.
- Implementar notificações push via Firebase Cloud Messaging (FCM).
- Adicionar suporte para mensagens de voz.

---

## ⚠️ 15. AI Usage Disclosure (Mandatory)

Não foram utilizadas ferramentas de IA generativa para a resolução dos problemas técnicos deste projeto.
