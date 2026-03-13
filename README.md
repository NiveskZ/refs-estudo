# Data Engineering & Science Knowledge Base

Este repositório centraliza referências técnicas, guias de estudo e documentação de aprendizado sobre o ecossistema de dados. O projeto consolida conhecimentos em Sistemas de Gerenciamento de Bancos de Dados (SGBD), Engenharia de Dados e Arquiteturas Distribuídas.

Atualmente, este espaço hospeda o projeto prático **Caderno Temático**, desenvolvido com o auxílio do Google NotebookLM, focado na arquitetura interna de bancos de dados.

---

## 1. Projeto: Caderno Temático ([NotebookLM](https://notebooklm.google.com/notebook/43143a25-5763-4f9e-af30-b651baf67ccd))

Este segmento documenta a utilização de Inteligência Artificial Generativa para a curadoria e síntese de conhecimentos avançados em infraestrutura de dados.

### 1.1 Contexto e Objetivos
O objetivo deste módulo é consolidar a base teórica sobre o funcionamento interno de SGBDs, analisando a transição entre o design relacional clássico e as exigências de sistemas modernos intensivos em dados.

**Objetivos de estudo:**
* Mapeamento de estruturas internas de armazenamento (B-Trees, LSM-Trees e WAL).
* Análise de consistência e disponibilidade em sistemas distribuídos (Teorema CAP).
* Estudo de padrões para evolução de esquemas e refatoração de dados.

### 1.2 Curadoria de Fontes
As fontes foram selecionadas com base em rigor acadêmico e relevância técnica. Priorizou-se documentações oficiais e materiais de autores referência na área.

| Recurso | Autor / Provedor | Categoria | Acesso |
| :--- | :--- | :--- | :--- |
| **PostgreSQL 18 Documentation** | PostgreSQL Global Dev Group | Documentação Técnica | [PDF Oficial](https://www.postgresql.org/files/documentation/pdf/18/postgresql-18-US.pdf) |
| **Designing Data-Intensive Applications** | Martin Kleppmann | Arquitetura de Sistemas | [Repositório de Apoio](https://github.com/ps06756/Designing-Data-Intensive-Applications) |
| **Build Your Own Database from Scratch** | cstack (GitHub) | Engenharia / Tutorial | [Acessar Tutorial](https://cstack.github.io/db_tutorial/) |
| **Getting Started with SQL** | Thomas Nield (O'Reilly) | SQL / Design | [Repositório Oficial](https://github.com/thomasnield/oreilly_getting_started_with_sql) |
| **Database Internals** | Alex Petrov | Sistemas Distribuídos | Referência Bibliográfica |
| **Refactoring Databases** | Scott J. Ambler & P. Sadalage | Evolução de Esquema | Referência Bibliográfica |
| **Introdução a Sistemas de BD** | C. J. Date | Referência Acadêmica | Referência Bibliográfica |
| **Banco de Dados - Projeto e Impl.** | Felipe Nery R. Machado | Prática de Mercado | Referência Bibliográfica |

### 1.3 Engenharia de Prompts e Metodologia
A interação com o NotebookLM foi estruturada para garantir profundidade técnica e correlação entre as fontes.

* **Estratégia de Contextualização:** As consultas foram formuladas exigindo que a IA comparasse teses de diferentes autores (ex: comparando a implementação de logs de transação no PostgreSQL com os conceitos de Write-Ahead Logging descritos por Petrov).
* **Refinamento (Troubleshooting):** Durante os testes, perguntas genéricas resultaram em definições superficiais. O ajuste consistiu em solicitar "análises de trade-offs" e exemplos práticos de implementação, o que forçou a IA a extrair dados específicos dos documentos técnicos carregados.

---

## 2. Miniguia de Estudo: SGBD (Resultados)

### Resumo Técnico
Os SGBDs modernos são divididos em componentes distintos: o **Query Processor** (responsável pela análise e otimização de consultas) e o **Storage Engine** (focado na persistência e integridade em disco). O entendimento da área exige discernir quando utilizar estruturas otimizadas para leitura (B-Trees) ou para escrita (LSM-Trees), além de compreender como as propriedades ACID garantem a confiabilidade em sistemas transacionais (OLTP) frente aos modelos analíticos (OLAP).

### Glossário Fundamental
* **ACID:** Propriedades que garantem que as transações de banco de dados sejam processadas de forma confiável (Atomicidade, Consistência, Isolamento e Durabilidade).
* **LSM-Tree (Log-Structured Merge-Tree):** Estrutura de dados que privilegia a performance de escrita, comumente utilizada em sistemas NoSQL e motores de armazenamento modernos.
* **WAL (Write-Ahead Logging):** Protocolo que garante que nenhuma alteração de dado seja perdida, registrando a intenção de alteração em um log antes da escrita definitiva no banco.
* **Database Refactoring:** Aplicação de pequenas mudanças no design de um banco de dados para melhorar sua estrutura sem alterar sua semântica original.

### Prompts para Revisão Ativa
* *"Com base nas fontes, explique como o PostgreSQL 18 lida com o isolamento de transações para evitar anomalias de leitura."*
* *"Compare as estratégias de armazenamento em linha versus armazenamento em coluna para cargas de trabalho analíticas."*
* *"Descreva o fluxo de uma escrita em uma estrutura LSM-Tree conforme detalhado em 'Database Internals'."*

---

## 3. Licença
Este projeto está licenciado sob a **MIT License** - consulte o arquivo [LICENSE](LICENSE) para mais detalhes.
