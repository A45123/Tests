# Assignment Tutorial 4 - Notes Pro (Firebase & GOAT)
[![Android Studio](https://img.shields.io/badge/IDE-Android%20Studio-green)](#)
[![Kotlin](https://img.shields.io/badge/Language-Kotlin-orange)](#)
[![Firebase](https://img.shields.io/badge/Platform-Firebase-yellow)](#)

Course: Licenciatura em Engenharia Informática e Multimédia <br>
Student(s): 45123 <br>
Date: 12/04/2026 <br>
Repository URL: [NotesPro](https://github.com/A45123/DAM/tree/main/Tutorial4-KotlinFlows/NotesProXMLViews3) <br>

---

## 📖 1. Introduction

O objetivo deste projeto é desenvolver uma aplicação robusta de gestão de notas pessoais utilizando **Cloud Firestore** para persistência e **Firebase Authentication** para segurança dos dados.

Além das funcionalidades base de um gestor de notas, este projeto inclui a funcionalidade **GOAT (Greatest Of All Times)**: a capacidade de anexar imagens a cada nota e uma organização avançada por categorias.

---

## 🖥️ 2. System Overview

A aplicação permite criar, editar e eliminar notas. Cada nota é sincronizada com a conta do utilizador, garantindo que os dados estão acessíveis em qualquer dispositivo.

Principais funcionalidades:
- Autenticação com validação de email.
- Persistência na nuvem com Firestore.
- Notas com suporte para imagens (GOAT feature).
- Interface moderna com RecyclerView e FirestoreAdapter.

---

## 🏗️ 3. Architecture and Design

A aplicação segue o padrão de arquitetura sugerido para Android com separação entre a lógica de UI e o acesso aos dados via Firebase SDK.

Componentes principais:
- **Cloud Firestore:** Base de dados NoSQL orientada a documentos para armazenamento das notas.
- **Firebase Auth:** Sistema de autenticação com fluxo de verificação de email.
- **NoteAdapter:** Implementação personalizada de `FirestoreRecyclerAdapter` para ligação direta entre a base de dados e a lista.

---

## ⚙️ 4. Implementation

### 4.1. Firestore Integration
Configuração de coleções e documentos para representar as notas dos utilizadores, utilizando sub-coleções para garantir que um utilizador apenas acede às suas próprias notas.

### 4.2. Email Verification
Implementação da lógica de envio de email de verificação após o registo. O acesso à aplicação apenas é permitido após a conta ser validada pelo utilizador através do link enviado.

### 4.3. GOAT Feature: Images in Notes
Adição da capacidade de selecionar uma imagem da galeria e associá-la a uma nota. A imagem é guardada no Firebase Storage e o seu URL é referenciado no documento da nota no Firestore.

### 4.4. UI Refinement
Uso de `FloatingActionButton` para criação de notas e menus contextuais para edição/eliminação, proporcionando uma experiência de utilizador fluida.

---

## 🔍 5. Testing and Validation

- Verificação do isolamento de dados entre diferentes utilizadores.
- Validação do fluxo de recuperação de password e verificação de email.
- Teste de performance ao carregar listas de notas com imagens.
- Verificação do modo offline do Firestore (cache local).

---

## 📝 6. Usage Instructions

- Configurar `google-services.json` no projeto.
- Ativar Firestore e Authentication na consola do Firebase.
- Definir as regras de segurança do Firestore para permitir acesso apenas a utilizadores autenticados aos seus próprios documentos.
- Compilar e correr no Android Studio.

---

# Autonomous Software Engineering Sections- only for [AC YES, AI YES] sections

Nesta secção do trabalho, foi permitido o uso de ferramentas de IA para auxiliar no design da base de dados Firestore e na implementação das funcionalidades extra (GOAT).

---

# Development Process

## 📦 12. Version Control and Commit History

O projeto foi desenvolvido de forma iterativa, começando pela autenticação, seguida pela persistência das notas e terminando na integração de média.

---

## 🌱 13. Difficulties and Lessons Learned

### 13.1 Dificuldades
- Sincronização entre o upload da imagem para o Storage e a gravação do documento no Firestore.
- Gestão do ciclo de vida do `FirestoreRecyclerAdapter` para evitar fugas de memória.

### 13.2 Lições Aprendidas
- Flexibilidade do modelo NoSQL para evolução de esquemas de dados (ex: adicionar campo de imagem a posteriori).
- Importância de feedback visual (progress bars) durante operações de rede assíncronas.

---

## 🔧 14. Future Improvements
- Adicionar lembretes (notifications) para notas.
- Suporte para Markdown nas notas.
- Colaboração em tempo real (partilha de notas entre utilizadores).

---

## ⚠️ 15. AI Usage Disclosure (Mandatory)

Foram utilizadas ferramentas de IA generativa para sugestões de estruturação de sub-coleções no Firestore e otimização do carregamento de imagens com bibliotecas como Glide ou Coil.
