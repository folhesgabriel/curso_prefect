# Proposta de Curso: Orquestração de Pipelines com Prefect e Docker

## Contexto
Este curso destina-se a profissionais ou entusiastas de Engenharia de Dados que desejam aprender como automatizar e orquestrar fluxos de dados (pipelines) utilizando **Prefect** e **Docker**. A proposta abordará desde a configuração do ambiente e instalação das ferramentas até o desenvolvimento e implantação de pipelines containerizadas.

---

## Objetivo
- **Demonstrar o funcionamento do Prefect** para automação de pipelines;  
- **Integrar o Prefect** a um banco de dados PostgreSQL;  
- **Mostrar como realizar o deploy** dos pipelines utilizando Docker.

---

## Público-Alvo
- Pessoas com **conhecimentos básicos em Python**;  
- Profissionais ou estudantes interessados em **Engenharia de Dados**;  
- Aqueles que desejam **aprender sobre orquestração de pipelines** e boas práticas de automação.

---

## Ementa Detalhada

### 1. Configurando o Ambiente: Entendendo o Prefect e Realizando Instalação
**Duração**: até 2h 

- **Osquestradores de fluxos de dados: qual o sentido? por qual motivo são utilizados? **
  - Explicar o que são osquestradores para introduzir o prefect
- **Visão geral do Prefect**  
  - Conceitos de *flows* e *tasks*: como o prefect organiza o código python para transformá-lo numa pipeline?
  - Vantagens de orquestração em projetos de dados.
  - Demonstração ao vivo de uma pipeline sendo executada no prefect.
- **Instalação do Prefect**  
  - Preparando ambiente Python (virtualenv ou Conda).  
  - Instalação via `pip` e verificação de versão.  
- **Executando o Primeiro Flow**  
  - Criando e rodando um `flow` simples (exemplo “Hello World”).  
  - Observando logs e status do flow.

> **Atividade Prática**  
> 1. Clonar repositório do GitHub com material prévio.  
> 2. Configurar ambiente virtual.  
> 3. Executar flow de exemplo e verificar resultados.

---

### 2. Primeira Pipeline: Realizando um Flow Mais Elaborado
**Duração**: até 2h 

- **Estrutura de um Flow Elaborado**  
  - Criação de múltiplas *tasks*.  
  - Encadeamento de tarefas (ETL, por exemplo).  
- **Parâmetros e Contexto**  
  - Passando parâmetros para *tasks*.  
  - Utilização de variáveis de ambiente.  
- **Logger e Monitoramento**  
  - Boas práticas de *logging* no Prefect.  
  - Visualização no Painel local do Prefect (UI).

> **Atividade Prática**  
> 1. Criar uma pipeline multi-tarefas (ex.: ler um arquivo CSV, processar dados).  
> 2. Adicionar parâmetros dinâmicos para controlar datas ou caminhos de arquivos.  
> 3. Verificar logs e status de cada *task*.

---

### 3. Inserindo PostgreSQL: Realizar Dump em um Postgres Pré-Configurado com Docker
**Duração**: até 2h 
- **Introdução ao Docker**  
  - Conceito de contêineres e imagens.  
  - Vantagens de usar Docker em projetos de Engenharia de Dados.  
- **Configuração do Postgres com Docker**  
  - *Pull* da imagem oficial do Postgres.  
  - Criação de volume e persistência de dados.  
- **Realizando Dump de Dados**  
  - Uso de `pg_dump` e `psql` (exportar e importar dados).  
  - Integração da *task* de dump com Prefect.

> **Atividade Prática**  
> 1. Subir contêiner Docker com PostgreSQL configurado.  
> 2. Criar uma *task* do Prefect para gerar um *dump* de dados fictícios e armazenar no contêiner.  
> 3. Garantir persistência do *dump* em um volume ou diretório mapeado.

---

### 4. Desenvolvendo uma Pipeline
**Duração**: até 2h 

- **Estrutura Completa de Pipeline**  
  - Conexão com fontes de dados (APIs, arquivos, bancos).  
  - Aplicação de transformações e validações (ex.: `pandas`).  
- **Mecanismos de Retries e Agendamento**  
  - Configurando retentativas (retry) em caso de falha.  
  - Agendamento de execuções recorrentes (schedules).  
- **Boas Práticas de Desenvolvimento**  
  - Organização de código e versionamento (Git).  
  - Documentação de *tasks* e *flows*.

> **Atividade Prática**  
> 1. Criar uma pipeline que faz ETL (leitura de CSV, transformação, carga no PostgreSQL).  
> 2. Configurar retentativas e envio de alertas em caso de falha.  
> 3. Criar agendamento básico (execução diária).

---

### 5. Fazendo o Deploy da Pipeline com Docker
**Duração**: até 2h 

todo: minha ideia era fazer um deploy manual usando o Cloud Run do GCP ou algo similar; Outra alternativa poderia ser criar uma VM e fazer o deploy usando somente docker compose. 
- **Containerização do Projeto**  
  - Construindo imagem Docker com Prefect e dependências.  
  - Definição de `Dockerfile` e uso de *docker-compose* para gerenciar múltiplos serviços.  
- **Estratégias de Deploy**  
  - Deploy local vs. Deploy em nuvem (AWS ECS, Kubernetes).  
  - Configurações de rede, variáveis de ambiente e volumes.  
- **Verificação e Escalabilidade**  
  - Testando a pipeline em contêineres antes de produção.  
  - Escalabilidade horizontal (replicas de contêiner).

> **Atividade Prática**  
> 1. Criar um `Dockerfile` para a aplicação e realizar *build* da imagem.  
> 2. Executar contêiner com Prefect Server e Agente para orquestrar *flows*.  
> 3. Verificar logs e resultados em ambiente containerizado.

---

## Formato do Curso
- **Carga Horária**: ~10 horas (distribuídas em 4 encontros ou módulos).  
- **Metodologia**:  
  - Aulas expositivas com exemplos práticos (*live coding*).  
  - Exercícios e desafios práticos para consolidação do aprendizado.  
- **Material**:  
  - Repositório GitHub com scripts e arquivos de exemplo.  
  - Slides e anotações de cada módulo.  
  - Links de referência e bibliografia complementar.

---

## Resultados Esperados
Ao final do curso, os participantes serão capazes de:
1. **Configurar e executar flows** no Prefect, entendendo conceitos de *tasks* e *flows*.  
2. **Integrar** o Prefect a um banco de dados Postgres via Docker, realizando dumps e cargas.  
3. **Desenvolver pipelines completos** com mecanismos de retries, agendamento e monitoramento.  
4. **Realizar o deploy** das pipelines em contêineres Docker, preparando-as para produção.

---

### Conclusão
Este curso fornece uma abordagem prática de como aplicar Prefect e Docker no dia a dia de Engenharia de Dados. Os participantes sairão aptos a criar pipelines escaláveis e robustos, desde o desenvolvimento local até ambientes de produção, dominando conceitos de orquestração, containerização e melhores práticas de automação.
