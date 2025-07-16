# Remote-pipeline

Repositório contendo a definição da *Golden Pipeline*, utilizada como base para CI/CD em múltiplos projetos da organização. A pipeline é implementada com **GitHub Actions** e tem como objetivo padronizar e automatizar o fluxo de integração e entrega contínua das aplicações.

---

## 📋 Índice

- [Introdução](#introdução)
- [Funcionalidades](#funcionalidades)
- [Etapas da Pipeline](#etapas-da-pipeline)
- [Reutilização](#reutilização)
- [Como Utilizar](#como-utilizar)
- [Futuras Expansões](#futuras-expansões)
- [Contribuição](#contribuição)
- [Licença](#licença)

---

## 📖 Introdução

Este repositório centraliza a pipeline padrão utilizada pelos projetos da organização. Seu objetivo é garantir consistência, reusabilidade e boas práticas no processo de CI/CD, facilitando a integração de novos projetos com a infraestrutura existente.

A pipeline é construída com **GitHub Actions**, e disponibilizada como um workflow reutilizável que pode ser invocado por outros repositórios.

---

## ⚙️ Funcionalidades

- Ação reutilizável com GitHub Actions
- Build e push automático de imagens Docker
- Deploy automatizado via **ArgoCD**
- Integração transparente com repositórios de aplicação

---

## 🔄 Etapas da Pipeline

Atualmente, a pipeline executa as seguintes etapas principais:

1. **Checkout do código**
2. **Build da imagem Docker**
3. **Push para o repositório de imagens**
4. **Deploy via ArgoCD**

> 🔧 Etapas futuras incluirão testes automatizados (unitários, integração, segurança, etc.).

---

## ♻️ Reutilização

Outros repositórios utilizam esta pipeline via **reutilização de workflow** do GitHub Actions:

```yaml
jobs:
  remote-pipeline:
    uses: golden-pipeline/remote-pipeline/.github/workflows/fake-shop-deploy-local.yml@feature-ecommerce
