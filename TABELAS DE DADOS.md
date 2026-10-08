# 📊 Tabelas de Dados — Muay Learn

## 1. Introdução

Este documento apresenta a estrutura dos dados utilizados pelo sistema **Muay Learn**.

As tabelas representam as principais informações necessárias para o funcionamento da plataforma, incluindo usuários, aulas, quizzes, perguntas, progresso, resultados e conquistas.

A estrutura foi organizada de forma que cada tipo de informação possua sua própria tabela, facilitando a organização dos dados e sua futura implementação em um banco de dados relacional.

---

# 2. Visão Geral das Tabelas

O sistema será representado pelas seguintes tabelas:

1. `usuarios`
2. `aulas`
3. `quizzes`
4. `perguntas`
5. `progresso`
6. `resultados_quiz`
7. `conquistas`
8. `usuario_conquistas`

---

# 3. Tabela — Usuários

## Nome

`usuarios`

## Objetivo

Armazenar os dados dos usuários cadastrados no sistema.

A tabela permite identificar se o usuário possui perfil de **Aluno** ou **Administrador**.

## Estrutura

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|:---:|
| id_usuario | INT | Identificador único do usuário | Sim |
| nome | VARCHAR(100) | Nome completo | Sim |
| email | VARCHAR(150) | E-mail de acesso | Sim |
| senha | VARCHAR(255) | Senha armazenada de forma segura | Sim |
| tipo | VARCHAR(20) | Tipo de usuário | Sim |
| data_cadastro | DATE | Data de cadastro | Sim |
| status | VARCHAR(20) | Situação da conta | Sim |

## Exemplos

| id_usuario | nome | email | senha | tipo | data_cadastro | status |
|---:|---|---|---|---|---|---|
| 1 | João Silva | joao@email.com | ******** | Aluno | 07/10/2026 | Ativo |
| 2 | Administrador | admin@muaylearn.com | ******** | Administrador | 07/10/2026 | Ativo |
| 3 | Carlos Santos | carlos@email.com | ******** | Aluno | 08/10/2026 | Ativo |

### Observação

A senha não deverá ser armazenada em texto puro em uma implementação real. Ela deverá ser protegida utilizando técnicas de criptografia/hash apropriadas.

---

# 4. Tabela — Aulas

## Nome

`aulas`

## Objetivo

Armazenar os conteúdos educacionais disponibilizados aos alunos.

Cada aula deverá pertencer a um dos três níveis:

- Iniciante;
- Intermediário;
- Avançado.

## Estrutura

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|:---:|
| id_aula | INT | Identificador único da aula | Sim |
| titulo | VARCHAR(150) | Nome da aula | Sim |
| descricao | TEXT | Descrição da aula | Sim |
| nivel | VARCHAR(30) | Nível de dificuldade | Sim |
| conteudo | TEXT | Conteúdo educacional | Sim |
| imagem | VARCHAR(255) | Caminho da imagem | Não |
| video | VARCHAR(255) | Link ou caminho do vídeo | Não |
| status | VARCHAR(20) | Situação da aula | Sim |
| data_criacao | DATE | Data de criação | Sim |

## Exemplos

| id_aula | titulo | descricao | nivel | conteudo | status |
|---:|---|---|---|---|---|
| 1 | Introdução ao Muay Thai | Fundamentos da modalidade | Iniciante | Conteúdo da aula | Ativa |
| 2 | Guarda | Aprendendo a posição de guarda | Iniciante | Conteúdo da aula | Ativa |
| 3 | Jab | Aprendendo o jab | Iniciante | Conteúdo da aula | Ativa |
| 4 | Combinações | Combinações de golpes | Intermediário | Conteúdo da aula | Ativa |
| 5 | Controle de distância | Estratégias de distância | Avançado | Conteúdo da aula | Ativa |

---

# 5. Tabela — Quizzes

## Nome

`quizzes`

## Objetivo

Armazenar os quizzes relacionados às aulas.

Uma aula poderá possuir um quiz associado.

## Estrutura

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|:---:|
| id_quiz | INT | Identificador do quiz | Sim |
| id_aula | INT | Aula relacionada | Sim |
| titulo | VARCHAR(150) | Nome do quiz | Sim |
| descricao | TEXT | Descrição do quiz | Não |
| status | VARCHAR(20) | Situação do quiz | Sim |

## Exemplos

| id_quiz | id_aula | titulo | descricao | status |
|---:|---:|---|---|---|
| 1 | 1 | Quiz — Fundamentos | Avaliação dos fundamentos | Ativo |
| 2 | 2 | Quiz — Guarda | Avaliação sobre guarda | Ativo |
| 3 | 3 | Quiz — Jab | Avaliação sobre o jab | Ativo |

### Relacionamento

Cada quiz pertence a uma aula.

```text
Aula 1 ──────── Quiz 1
Aula 2 ──────── Quiz 2
Aula 3 ──────── Quiz 3
```

---

# 6. Tabela — Perguntas

## Nome

`perguntas`

## Objetivo

Armazenar as perguntas utilizadas nos quizzes.

Cada pergunta pertence a um quiz.

## Estrutura

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|:---:|
| id_pergunta | INT | Identificador da pergunta | Sim |
| id_quiz | INT | Quiz relacionado | Sim |
| enunciado | TEXT | Texto da pergunta | Sim |
| alternativa_a | TEXT | Alternativa A | Sim |
| alternativa_b | TEXT | Alternativa B | Sim |
| alternativa_c | TEXT | Alternativa C | Sim |
| alternativa_d | TEXT | Alternativa D | Sim |
| resposta_correta | CHAR(1) | Alternativa correta | Sim |

## Exemplos

| id_pergunta | id_quiz | enunciado | alternativa_a | alternativa_b | alternativa_c | alternativa_d | resposta_correta |
|---:|---:|---|---|---|---|---|:---:|
| 1 | 1 | Qual é a função da guarda? | Defesa | Chute | Corrida | Ataque | A |
| 2 | 1 | Qual golpe utiliza a mão da frente? | Direto | Jab | Joelhada | Teep | B |
| 3 | 2 | Qual é a função principal da guarda? | Proteger | Correr | Chutar | Esquivar | A |

---

# 7. Tabela — Progresso

## Nome

`progresso`

## Objetivo

Armazenar informações relacionadas à evolução do aluno dentro da plataforma.

## Estrutura

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|:---:|
| id_progresso | INT | Identificador do progresso | Sim |
| id_usuario | INT | Aluno relacionado | Sim |
| aulas_concluidas | INT | Quantidade de aulas concluídas | Sim |
| xp | INT | XP acumulado | Sim |
| nivel | INT | Nível atual do aluno | Sim |
| percentual | DECIMAL(5,2) | Percentual de progresso | Sim |
| ultima_atualizacao | DATE | Data da última atualização | Sim |

## Exemplos

| id_progresso | id_usuario | aulas_concluidas | xp | nivel | percentual | ultima_atualizacao |
|---:|---:|---:|---:|---:|---:|---|
| 1 | 1 | 5 | 500 | 2 | 25.00 | 07/10/2026 |
| 2 | 3 | 2 | 200 | 1 | 10.00 | 08/10/2026 |

---

# 8. Tabela — Resultados dos Quizzes

## Nome

`resultados_quiz`

## Objetivo

Registrar o desempenho dos alunos após a realização dos quizzes.

## Estrutura

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|:---:|
| id_resultado | INT | Identificador do resultado | Sim |
| id_usuario | INT | Aluno que realizou o quiz | Sim |
| id_quiz | INT | Quiz realizado | Sim |
| acertos | INT | Quantidade de respostas corretas | Sim |
| erros | INT | Quantidade de respostas incorretas | Sim |
| total_perguntas | INT | Quantidade total de perguntas | Sim |
| percentual | DECIMAL(5,2) | Percentual de aproveitamento | Sim |
| xp_ganho | INT | XP recebido | Sim |
| data_realizacao | DATE | Data da realização | Sim |

## Exemplos

| id_resultado | id_usuario | id_quiz | acertos | erros | total_perguntas | percentual | xp_ganho | data_realizacao |
|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 1 | 1 | 1 | 8 | 2 | 10 | 80.00 | 100 | 07/10/2026 |
| 2 | 1 | 2 | 9 | 1 | 10 | 90.00 | 120 | 08/10/2026 |
| 3 | 3 | 1 | 6 | 4 | 10 | 60.00 | 60 | 08/10/2026 |

---

# 9. Tabela — Conquistas

## Nome

`conquistas`

## Objetivo

Armazenar as conquistas disponíveis no sistema.

As conquistas serão desbloqueadas quando o aluno atingir determinados requisitos.

## Estrutura

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|:---:|
| id_conquista | INT | Identificador da conquista | Sim |
| nome | VARCHAR(100) | Nome da conquista | Sim |
| descricao | TEXT | Descrição | Sim |
| requisito | TEXT | Condição para desbloqueio | Sim |
| xp_bonus | INT | XP concedido | Sim |
| status | VARCHAR(20) | Situação da conquista | Sim |

## Exemplos

| id_conquista | nome | descricao | requisito | xp_bonus | status |
|---:|---|---|---|---:|---|
| 1 | Primeiro Golpe | Primeira aula concluída | Completar 1 aula | 50 | Ativa |
| 2 | Primeiro Treino | Primeiras aulas concluídas | Completar 5 aulas | 100 | Ativa |
| 3 | Em Evolução | Evolução dentro da plataforma | Alcançar 500 XP | 150 | Ativa |
| 4 | Guerreiro | Conclusão de várias aulas | Completar 10 aulas | 250 | Ativa |
| 5 | Mestre dos Fundamentos | Domínio do nível iniciante | Concluir nível iniciante | 500 | Ativa |

---

# 10. Tabela — Conquistas dos Alunos

## Nome

`usuario_conquistas`

## Objetivo

Relacionar os alunos às conquistas que eles desbloquearam.

Essa tabela é necessária porque um aluno pode possuir várias conquistas e uma conquista pode ser desbloqueada por vários alunos.

## Estrutura

| Campo | Tipo | Descrição | Obrigatório |
|---|---|---|:---:|
| id | INT | Identificador do registro | Sim |
| id_usuario | INT | Aluno relacionado | Sim |
| id_conquista | INT | Conquista desbloqueada | Sim |
| data_desbloqueio | DATE | Data em que foi desbloqueada | Sim |

## Exemplos

| id | id_usuario | id_conquista | data_desbloqueio |
|---:|---:|---:|---|
| 1 | 1 | 1 | 07/10/2026 |
| 2 | 1 | 2 | 08/10/2026 |
| 3 | 3 | 1 | 08/10/2026 |

---

# 11. Relacionamento entre as Tabelas

As principais relações entre os dados são:

```text
USUÁRIO
   │
   ├────────────── PROGRESSO
   │
   ├────────────── RESULTADOS_QUIZ
   │
   └────────────── USUARIO_CONQUISTAS
                          │
                          └──── CONQUISTAS


AULA
 │
 └────────────── QUIZ
                    │
                    └──── PERGUNTAS
```

---

# 12. Relacionamentos

## Usuário → Progresso

Um usuário do tipo aluno possui um registro de progresso.

```text
Usuário 1 ───── 1 Progresso
```

---

## Usuário → Resultados

Um aluno pode realizar vários quizzes.

```text
Usuário 1 ───── * Resultados
```

---

## Aula → Quiz

Uma aula pode possuir nenhum ou um quiz associado.

```text
Aula 1 ───── 0..1 Quiz
```

---

## Quiz → Perguntas

Um quiz pode possuir várias perguntas.

```text
Quiz 1 ───── * Perguntas
```

---

## Usuário → Conquistas

Um aluno pode possuir várias conquistas.

Uma mesma conquista pode pertencer a vários alunos.

Por isso é utilizada a tabela intermediária `usuario_conquistas`.

```text
Usuário * ───── * Conquista
```

Representação no banco:

```text
Usuário
   ↓
usuario_conquistas
   ↓
Conquista
```

---

# 13. Chaves Primárias

As seguintes colunas funcionam como identificadores únicos:

| Tabela | Chave Primária |
|---|---|
| usuarios | id_usuario |
| aulas | id_aula |
| quizzes | id_quiz |
| perguntas | id_pergunta |
| progresso | id_progresso |
| resultados_quiz | id_resultado |
| conquistas | id_conquista |
| usuario_conquistas | id |

---

# 14. Chaves Estrangeiras

As principais chaves estrangeiras são:

| Tabela | Campo | Referência |
|---|---|---|
| quizzes | id_aula | aulas.id_aula |
| perguntas | id_quiz | quizzes.id_quiz |
| progresso | id_usuario | usuarios.id_usuario |
| resultados_quiz | id_usuario | usuarios.id_usuario |
| resultados_quiz | id_quiz | quizzes.id_quiz |
| usuario_conquistas | id_usuario | usuarios.id_usuario |
| usuario_conquistas | id_conquista | conquistas.id_conquista |

---

# 15. Organização no Google Planilhas

Para atender à proposta do projeto acadêmico, cada tabela poderá ser criada como uma aba separada dentro de uma única planilha.

Sugestão:

```text
📊 Muay Learn — Banco de Dados

├── Usuários
├── Aulas
├── Quizzes
├── Perguntas
├── Progresso
├── Resultados Quiz
├── Conquistas
└── Usuário Conquistas
```

Cada aba deverá possuir:

- primeira linha com os nomes dos campos;
- uma linha para cada registro;
- identificadores únicos;
- dados organizados por coluna;
- valores consistentes com os tipos definidos.

---

# 16. Exemplo de Organização

### Aba: Usuários

```text
id_usuario | nome | email | senha | tipo | data_cadastro | status
1          | João | joao@email.com | ******** | Aluno | 07/10/2026 | Ativo
```

### Aba: Aulas

```text
id_aula | titulo | descricao | nivel | conteudo | status
1       | Jab     | Golpe básico | Iniciante | ... | Ativa
```

### Aba: Quizzes

```text
id_quiz | id_aula | titulo | descricao | status
1       | 1       | Quiz Jab | Avaliação | Ativo
```

### Aba: Perguntas

```text
id_pergunta | id_quiz | enunciado | alternativa_a | alternativa_b | alternativa_c | alternativa_d | resposta_correta
1           | 1       | Qual golpe...? | Jab | Direto | Teep | Chute | A
```

---

# 17. Resumo da Estrutura

O banco de dados do Muay Learn será composto inicialmente por **8 tipos principais de dados**:

| Nº | Tabela | Finalidade |
|---:|---|---|
| 1 | Usuários | Cadastro e autenticação |
| 2 | Aulas | Conteúdo educacional |
| 3 | Quizzes | Avaliações |
| 4 | Perguntas | Questões dos quizzes |
| 5 | Progresso | Evolução dos alunos |
| 6 | Resultados Quiz | Desempenho nas avaliações |
| 7 | Conquistas | Conquistas disponíveis |
| 8 | Usuário Conquistas | Conquistas desbloqueadas |

---

# 18. Observação Final

As tabelas apresentadas neste documento representam uma estrutura inicial para a modelagem dos dados do Muay Learn.

A estrutura poderá ser refinada durante a implementação do sistema, especialmente na definição dos tipos de dados, índices, relacionamentos, regras de integridade e mecanismos de segurança.

A senha dos usuários deverá ser armazenada utilizando mecanismos seguros de hash e nunca em texto puro.
