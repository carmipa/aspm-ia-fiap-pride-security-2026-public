# 🏗️ 03 - Arquitetura Tecnica

<p align="left">
  <img src="https://img.shields.io/badge/Doc-Arquitetura-black?style=flat&logo=architecture&logoColor=white" alt="Arquitetura">
  <img src="https://img.shields.io/badge/Foco-Modularidade-2ea44f?style=flat&logo=dependabot&logoColor=white" alt="Modularidade">
</p>

**Navegacao:** [📚 Dicionario](./README.md) • [⚙️ Anterior: Instalacao](./02-instalacao-execucao.md) • [🧩 Proximo: Modulos](./04-modulos-responsabilidades.md)

## 🧭 Menu de Diagramas

- [Fluxo geral da aplicacao](#fluxo-geral-da-aplicacao)
- [Arquitetura por camadas](#arquitetura-por-camadas)
- [Execucao local e container](#execucao-local-e-container)

## 📌 Visao da arquitetura

A arquitetura atual prioriza simplicidade, separacao por responsabilidade e facilidade de manutencao.

## 🗺️ Diagramas (Mermaid GitHub)

### Fluxo geral da aplicacao

```mermaid
flowchart TD
    U[Usuario] --> M[main.py]
    M --> MENU[Menu principal]
    MENU --> CAD[Fluxo de cadastro]
    MENU --> LIST[Listagem]
    MENU --> SOBRE[Tela sobre]
    CAD --> DATA[(Persistencia em arquivo)]
    LIST --> DATA
```

### Arquitetura por camadas

```mermaid
flowchart LR
    A[Camada CLI - app/ui] --> B[Camada de regras - fluxos]
    B --> C[Camada utilitaria - app/utils]
    B --> D[Camada de dados - app/data]
```

### Execucao local e container

```mermaid
flowchart LR
    DEV[Dev local] --> PY[python main.py]
    DEV --> DOCKER[docker compose up --build]
    PY --> APP[Aplicacao CLI]
    DOCKER --> APP
```

## 🧱 Camadas principais

- `main.py`: ponto de entrada da aplicacao.
- `app/ui`: menus e interacao com usuario.
- `app/utils`: funcoes de suporte (helpers, tempo, etc.).
- `app/data`: persistencia simples baseada em arquivo.

## 🎯 Principios adotados

- Modularidade: cada pasta atende a um papel especifico.
- Legibilidade: codigo orientado a aprendizado e evolucao.
- Escalabilidade incremental: base preparada para novos modulos.

## 🚀 Evolucao esperada

- Introducao de camada de servicos.
- Persistencia em banco relacional ou NoSQL.
- Isolamento dos fluxos de scanner e auditoria.

---

**Proxima leitura recomendada:** [🧩 04 - Modulos e Responsabilidades](./04-modulos-responsabilidades.md)
