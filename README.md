# Data Engineering & Science Knowledge Base

Este repositório serve como um repositório centralizado de referências técnicas, guias de estudo e documentação de aprendizado sobre o ecossistema de dados. O projeto evolui conforme novas tecnologias são exploradas, consolidando conhecimentos em SGBD, Engenharia de Dados, Ciência de Dados e Arquiteturas Distribuídas.

Atualmente, o repositório hospeda o projeto prático "Caderno Temático", desenvolvido com o auxílio do Google NotebookLM, focado em Sistemas de Gerenciamento de Bancos de Dados.

---

## 1. Projeto: Caderno Temático (NotebookLM)

Este segmento documenta o uso de IA Generativa para a curadoria e síntese de conhecimentos avançados em bancos de dados.

### 1.1 Contexto e Objetivos
O objetivo inicial deste módulo é consolidar a base teórica sobre o funcionamento interno de SGBDs. O foco recai sobre a transição entre o design relacional clássico e as exigências de sistemas modernos e intensivos em dados.

**Objetivos de estudo:**
* Mapeamento de estruturas internas (B-Trees, LSM-Trees e WAL).
* Estudo de consistência em sistemas distribuídos (Teorema CAP).
* Aplicação de padrões de refatoração de esquemas para evolução de bases de dados.

### 1.2 Curadoria de Fontes
As fontes foram selecionadas com base em rigor acadêmico e relevância no mercado de engenharia de dados.

| Recurso | Autor / Provedor | Categoria | Acesso |
| :--- | :--- | :--- | :--- |
| **PostgreSQL 18 Documentation** | PostgreSQL Global Dev Group | Documentação Técnica | [Acessar](https://www.postgresql.org/files/documentation/pdf/18/postgresql-18-US.pdf) |
| **Designing Data-Intensive Applications** | Martin Kleppmann | Arquitetura de Sistemas | [Repositório Oficial](https://github.com/ept/ddia-code) |
| **Database Internals** | Alex Petrov | Sistemas Distribuídos | [Conceitos Base](https://www.databass.dev/) |
| **Getting Started with SQL** | Thomas Nield (O'Reilly) | SQL / Design | [Repositório Oficial](https://github.com/thomasnield/oreilly_getting_started_with_sql) |
| **Refactoring Databases** | Scott J. Ambler & P. Sadalage | Evolução de Esquema | [Catálogo de Padrões](https://scottambler.com/refactoring-databases/) |
| **Introdução a Sistemas de BD** | C. J. Date | Referência Acadêmica | Referência Bibliográfica |
| **Banco de Dados - Projeto e Impl.** | Felipe Nery R. Machado | Prática de Mercado | Referência Bibliográfica |

### 1.3 Engenharia de Prompts e Metodologia
A interação com o NotebookLM foi estruturada para evitar alucinações e garantir profundidade técnica.

* **Estratégia de Contextualização:** As consultas foram formuladas exigindo que a IA comparasse teses de diferentes autores (ex: comparando a visão de "durabilidade" entre o modelo ACID clássico de Date e as implementações distribuídas de Petrov).
* **Refinamento (Troubleshooting):** Identificou-se que perguntas genéricas resultavam em definições de glossário simples. O ajuste consistiu em solicitar "análises de trade-offs" entre diferentes tecnologias, o que forçou a IA a correlacionar os dados das fontes enviadas.

---

## 2. Miniguia de Estudo: SGBD (Resultados)

### Resumo Técnico
Os SGBDs atuam como a camada mediadora entre a aplicação e o armazenamento físico. O entendimento moderno da área exige separar o **Query Processor** (otimização e execução de SQL) do **Storage Engine** (onde reside a complexidade de concorrência e persistência). Enquanto bancos tradicionais otimizam para transações (OLTP), arquiteturas modernas de dados buscam eficiência analítica (OLAP) e escalabilidade através de particionamento.

### Glossário Fundamental
* **ACID:** Conjunto de propriedades (Atomicidade, Consistência, Isolamento e Durabilidade) que garante a confiabilidade das transações.
* **LSM-Tree (Log-Structured Merge-Tree):** Estrutura que privilegia a performance de escrita, fundamental para bancos de dados de alta ingestão.
* **Database Refactoring:** Processo de aplicar pequenas mudanças no design de um banco sem alterar sua semântica comportamental.

### Prompts para Revisão Ativa
* *"Explique como o isolamento de transações no PostgreSQL 18 lida com o fenômeno de 'Dirty Reads'."*
* *"Compare as estratégias de particionamento horizontal discutidas por Kleppmann com as implementações de sharding padrão de mercado."*

---

## 3. Roadmaps Futuros
Este repositório será expandido com os seguintes módulos:
* **Módulo SQL Avançado:** Técnicas de otimização de queries e planos de execução.
* **Módulo NoSQL:** Exploração de bancos de documentos (MongoDB) e grafos (Neo4j).
* **Módulo Data Science:** Pipelines de processamento com Python, Scikit-learn e integração de modelos preditivos.

## 4. Licença
Este projeto está licenciado sob a **MIT License** - consulte o arquivo [LICENSE](LICENSE) para mais detalhes.
