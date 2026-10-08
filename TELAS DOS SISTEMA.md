# 🖥️ Telas do Sistema — Muay Learn

## 1. Introdução

Este documento apresenta a especificação das telas previstas para o sistema **Muay Learn**.

O objetivo é descrever a estrutura e as principais funcionalidades de cada tela da plataforma, facilitando a compreensão da interface e do funcionamento do sistema.

As telas foram divididas em três áreas principais:

- **Área pública:** telas acessíveis antes do login;
- **Área do aluno:** funcionalidades destinadas aos alunos;
- **Área administrativa:** funcionalidades destinadas aos administradores.

---

# 🌐 Área Pública

## Tela 01 — Splash / Carregamento

### Objetivo

Apresentar a identidade visual do Muay Learn enquanto o sistema é carregado.

### Usuário

- Visitante
- Aluno
- Administrador

### Elementos da tela

- Logo do Muay Learn;
- Nome da plataforma;
- Slogan: **"Aprenda. Treine. Evolua."**
- Elemento visual relacionado ao Muay Thai;
- Indicador de carregamento.

### Ações

Após o carregamento, o sistema direciona o usuário para a página inicial ou para a área correspondente caso exista uma sessão autenticada.

---

## Tela 02 — Página Inicial

### Objetivo

Apresentar o Muay Learn para novos visitantes e explicar a proposta da plataforma.

### Usuário

- Visitante
- Aluno

### Elementos da tela

- Logo;
- Nome Muay Learn;
- Slogan;
- Breve descrição da plataforma;
- Apresentação dos níveis de aprendizado;
- Botão **"Começar agora"**;
- Botão **"Entrar"**;
- Informações sobre o funcionamento da plataforma.

### Ações

O visitante poderá:

- acessar o cadastro;
- acessar o login;
- conhecer a proposta do sistema.

---

## Tela 03 — Login

### Objetivo

Permitir que usuários cadastrados acessem o sistema.

### Usuário

- Aluno
- Administrador

### Campos

- E-mail;
- Senha.

### Elementos

- Botão **"Entrar"**;
- Link **"Esqueci minha senha"**;
- Link **"Criar conta"**.

### Regras

O sistema deverá verificar:

- se o e-mail existe;
- se a senha está correta;
- qual é o tipo de usuário.

### Resultado

Após autenticação:

- Aluno → Dashboard do aluno;
- Administrador → Dashboard administrativo.

---

## Tela 04 — Cadastro

### Objetivo

Permitir que novos alunos criem uma conta na plataforma.

### Usuário

- Visitante

### Campos

- Nome;
- E-mail;
- Senha;
- Confirmação da senha.

### Elementos

- Botão **"Criar conta"**;
- Link para login.

### Validações

O sistema deverá verificar:

- preenchimento dos campos obrigatórios;
- formato válido do e-mail;
- e-mail não cadastrado;
- confirmação da senha.

### Resultado

Após o cadastro, o usuário poderá realizar login e acessar a plataforma.

---

# 🥊 Área do Aluno

## Tela 05 — Recuperar Senha

### Objetivo

Permitir que um usuário recupere o acesso à sua conta.

### Usuário

- Aluno
- Administrador

### Elementos

- Campo de e-mail;
- Botão **"Enviar recuperação"**;
- Link para retornar ao login.

### Funcionamento

O usuário informa seu e-mail cadastrado e solicita a recuperação da senha.

---

## Tela 06 — Dashboard do Aluno

### Objetivo

Apresentar um resumo da evolução do aluno.

### Usuário

- Aluno

### Elementos

- Nome do aluno;
- Nível atual;
- XP acumulado;
- Barra de progresso;
- Quantidade de aulas concluídas;
- Última aula acessada;
- Conquistas recentes;
- Botão para continuar estudando.

### Ações

O aluno poderá:

- continuar uma aula;
- acessar as aulas;
- visualizar seu progresso;
- visualizar conquistas;
- acessar seu perfil.

---

## Tela 07 — Lista de Aulas

### Objetivo

Apresentar todas as aulas disponíveis para o aluno.

### Usuário

- Aluno

### Elementos

- Lista de aulas;
- Nome da aula;
- Descrição;
- Nível;
- Status da aula;
- Indicador de conclusão.

### Filtros

O aluno poderá filtrar as aulas por:

- Iniciante;
- Intermediário;
- Avançado.

### Ações

Ao selecionar uma aula, o aluno será direcionado para a tela da aula.

---

## Tela 08 — Aulas para Iniciantes

### Objetivo

Apresentar os conteúdos básicos do Muay Thai.

### Usuário

- Aluno

### Conteúdos previstos

- Base e postura;
- Guarda;
- Jab;
- Direto;
- Cruzado;
- Teep;
- Chutes;
- Joelhadas;
- Cotoveladas.

### Elementos

Cada aula deverá apresentar:

- título;
- descrição;
- nível;
- status de conclusão;
- botão para iniciar.

---

## Tela 09 — Aulas Intermediárias

### Objetivo

Apresentar conteúdos destinados a alunos que já dominam os fundamentos básicos.

### Usuário

- Aluno

### Conteúdos previstos

- Combinações;
- Bloqueios;
- Esquivas;
- Movimentação;
- Contra-ataques;
- Combinações de golpes.

### Elementos

- Lista de aulas;
- progresso;
- status de conclusão;
- botão para iniciar.

---

## Tela 10 — Aulas Avançadas

### Objetivo

Apresentar conteúdos relacionados à estratégia e ao desenvolvimento avançado.

### Usuário

- Aluno

### Conteúdos previstos

- Estratégia;
- Controle de distância;
- Timing;
- Combinações avançadas;
- Leitura do adversário;
- Estratégias de combate.

### Elementos

- Lista de aulas;
- descrição;
- progresso;
- status;
- botão para iniciar.

---

## Tela 11 — Aula

### Objetivo

Apresentar uma aula específica para o aluno.

### Usuário

- Aluno

### Elementos

- Título da aula;
- Nível;
- Descrição;
- Conteúdo;
- Imagens ou vídeos educacionais;
- Botão **"Concluir aula"**;
- Botão **"Iniciar quiz"**, quando disponível.

### Funcionamento

O aluno deverá estudar o conteúdo antes de marcar a aula como concluída.

### Resultado

Ao concluir a aula:

- progresso atualizado;
- XP registrado, quando aplicável;
- próxima atividade disponibilizada.

---

## Tela 12 — Técnica

### Objetivo

Apresentar detalhadamente uma técnica específica de Muay Thai.

### Usuário

- Aluno

### Elementos

- Nome da técnica;
- descrição;
- explicação passo a passo;
- imagem ou vídeo;
- principais pontos de atenção;
- erros comuns;
- botão para voltar à aula.

### Exemplos

- Jab;
- Direto;
- Teep;
- Chute;
- Joelhada;
- Cotovelada.

### Observação

Os conteúdos possuem finalidade educacional e não substituem a orientação de um treinador qualificado.

---

## Tela 13 — Quiz

### Objetivo

Avaliar o conhecimento adquirido pelo aluno durante a aula.

### Usuário

- Aluno

### Elementos

- Título do quiz;
- pergunta;
- alternativas;
- indicador de progresso;
- botão **"Próxima"**;
- botão **"Finalizar quiz"**.

### Funcionamento

O aluno deverá responder às perguntas apresentadas.

Após finalizar, o sistema deverá verificar as respostas e calcular o resultado.

---

## Tela 14 — Resultado do Quiz

### Objetivo

Apresentar o desempenho do aluno após a realização de um quiz.

### Usuário

- Aluno

### Informações

- Pontuação;
- quantidade de acertos;
- quantidade de erros;
- percentual de aproveitamento;
- XP recebido;
- possíveis conquistas desbloqueadas.

### Ações

- Refazer quiz;
- voltar para a aula;
- acessar progresso;
- continuar estudando.

---

## Tela 15 — Progresso

### Objetivo

Permitir que o aluno acompanhe sua evolução dentro da plataforma.

### Usuário

- Aluno

### Informações

- XP acumulado;
- nível atual;
- aulas concluídas;
- quizzes realizados;
- percentual de progresso;
- conquistas desbloqueadas.

### Elementos visuais

- Barra de progresso;
- indicadores numéricos;
- histórico de atividades.

---

## Tela 16 — Conquistas

### Objetivo

Apresentar as conquistas disponíveis e desbloqueadas pelo aluno.

### Usuário

- Aluno

### Elementos

- Lista de conquistas;
- nome;
- descrição;
- requisito;
- status: bloqueada ou desbloqueada;
- data de desbloqueio.

### Exemplos

- **Primeiro Golpe**
- **Primeiro Treino**
- **Em Evolução**
- **Guerreiro**
- **Mestre dos Fundamentos**

---

## Tela 17 — Perfil do Aluno

### Objetivo

Permitir que o aluno visualize e gerencie seus dados.

### Usuário

- Aluno

### Informações

- Nome;
- E-mail;
- Nível;
- XP;
- progresso;
- conquistas.

### Ações

- Editar dados;
- alterar senha;
- visualizar progresso;
- sair da conta.

---

# ⚙️ Área Administrativa

## Tela 18 — Dashboard Administrativo

### Objetivo

Apresentar ao administrador uma visão geral da plataforma.

### Usuário

- Administrador

### Informações

- Quantidade de usuários;
- quantidade de alunos;
- quantidade de aulas;
- quantidade de quizzes;
- quantidade de perguntas;
- quantidade de conquistas.

### Ações

O administrador poderá acessar:

- usuários;
- aulas;
- quizzes;
- perguntas;
- conquistas.

---

## Tela 19 — Gerenciamento de Usuários

### Objetivo

Permitir ao administrador visualizar e gerenciar usuários cadastrados.

### Usuário

- Administrador

### Informações

- ID;
- nome;
- e-mail;
- tipo;
- data de cadastro;
- status.

### Ações

- Visualizar usuário;
- editar usuário;
- excluir usuário;
- pesquisar usuário.

---

## Tela 20 — Cadastro de Aula

### Objetivo

Permitir ao administrador criar uma nova aula.

### Usuário

- Administrador

### Campos

- Título;
- descrição;
- nível;
- conteúdo;
- imagem;
- vídeo;
- status.

### Níveis

- Iniciante;
- Intermediário;
- Avançado.

### Ações

- Salvar aula;
- cancelar cadastro.

---

## Tela 21 — Edição de Aula

### Objetivo

Permitir ao administrador alterar uma aula existente.

### Usuário

- Administrador

### Campos editáveis

- Título;
- descrição;
- nível;
- conteúdo;
- imagem;
- vídeo;
- status.

### Ações

- Salvar alterações;
- cancelar;
- excluir aula.

---

## Tela 22 — Gerenciamento de Aulas

### Objetivo

Permitir ao administrador visualizar e organizar todas as aulas cadastradas.

### Usuário

- Administrador

### Elementos

- Lista de aulas;
- título;
- nível;
- status;
- data de criação.

### Ações

- Criar aula;
- editar;
- excluir;
- pesquisar;
- filtrar por nível.

---

## Tela 23 — Gerenciamento de Quizzes

### Objetivo

Permitir ao administrador gerenciar os quizzes relacionados às aulas.

### Usuário

- Administrador

### Informações

- ID;
- título;
- aula relacionada;
- quantidade de perguntas;
- status.

### Ações

- Criar quiz;
- editar quiz;
- excluir quiz;
- visualizar perguntas.

---

## Tela 24 — Cadastro de Pergunta

### Objetivo

Permitir ao administrador cadastrar uma nova pergunta em um quiz.

### Usuário

- Administrador

### Campos

- Quiz relacionado;
- enunciado;
- alternativa A;
- alternativa B;
- alternativa C;
- alternativa D;
- resposta correta.

### Ações

- Salvar pergunta;
- cancelar.

### Regra

Cada pergunta deverá possuir uma alternativa definida como resposta correta.

---

## Tela 25 — Edição de Pergunta

### Objetivo

Permitir ao administrador alterar uma pergunta existente.

### Usuário

- Administrador

### Campos

- Enunciado;
- alternativa A;
- alternativa B;
- alternativa C;
- alternativa D;
- resposta correta.

### Ações

- Salvar alterações;
- cancelar;
- excluir pergunta.

---

## Tela 26 — Gerenciamento de Conquistas

### Objetivo

Permitir ao administrador cadastrar e gerenciar as conquistas disponíveis no sistema.

### Usuário

- Administrador

### Informações

- Nome da conquista;
- descrição;
- requisito;
- quantidade de XP;
- status.

### Ações

- Criar conquista;
- editar conquista;
- excluir conquista;
- ativar ou desativar conquista.

---

# 🔄 Fluxo Geral das Telas

O fluxo principal do aluno pode ser representado da seguinte maneira:

```text
Página Inicial
      ↓
    Cadastro
      ↓
     Login
      ↓
Dashboard do Aluno
      ↓
Lista de Aulas
      ↓
Selecionar Nível
      ↓
Selecionar Aula
      ↓
Visualizar Conteúdo
      ↓
   Existe Quiz?
    ↙       ↘
  Sim       Não
   ↓         ↓
Realizar   Concluir
  Quiz       Aula
   ↓         ↓
Resultado ←──┘
   ↓
Atualizar XP
   ↓
Atualizar Progresso
   ↓
Verificar Conquista
   ↓
Dashboard
```

---

# 🔐 Controle de Acesso

As telas deverão respeitar o tipo de usuário autenticado.

| Tela | Visitante | Aluno | Administrador |
|---|:---:|:---:|:---:|
| Página inicial | ✅ | ✅ | ✅ |
| Cadastro | ✅ | ❌ | ❌ |
| Login | ✅ | ✅ | ✅ |
| Dashboard aluno | ❌ | ✅ | ❌ |
| Aulas | ❌ | ✅ | ❌ |
| Quiz | ❌ | ✅ | ❌ |
| Progresso | ❌ | ✅ | ❌ |
| Conquistas | ❌ | ✅ | ❌ |
| Perfil | ❌ | ✅ | ❌ |
| Dashboard admin | ❌ | ❌ | ✅ |
| Usuários | ❌ | ❌ | ✅ |
| Gerenciar aulas | ❌ | ❌ | ✅ |
| Gerenciar quizzes | ❌ | ❌ | ✅ |
| Gerenciar perguntas | ❌ | ❌ | ✅ |
| Gerenciar conquistas | ❌ | ❌ | ✅ |

---

# 📱 Responsividade

Todas as telas deverão ser projetadas considerando diferentes tamanhos de tela.

A interface deverá funcionar adequadamente em:

- Computadores;
- notebooks;
- tablets;
- smartphones.

Os elementos deverão se adaptar ao tamanho da tela sem comprometer a leitura ou a utilização das funcionalidades.

---

# 🎨 Identidade Visual

A interface do Muay Learn deverá transmitir características relacionadas ao Muay Thai e ao aprendizado esportivo.

A identidade visual poderá utilizar:

- elementos relacionados ao Muay Thai;
- luvas;
- ringue;
- cordas;
- silhuetas de lutadores;
- elementos esportivos;
- indicadores de progresso;
- ícones de conquistas.

A interface deverá manter uma aparência moderna, organizada e de fácil utilização.

---

# 🥊 Observação

O Muay Learn é uma proposta de plataforma educacional para estudo dos fundamentos do Muay Thai.

As informações apresentadas no sistema possuem finalidade educacional e não substituem a orientação presencial de um professor ou treinador qualificado.
