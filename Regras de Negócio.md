# Regras de Negócio — Muay Learn

## 1. Introdução

As regras de negócio definem as condições e restrições que deverão ser respeitadas pelo sistema Muay Learn para que suas funcionalidades funcionem de acordo com a proposta da plataforma.

---

## 2. Regras de Negócio

### RN01 — E-mail único

Cada usuário deve possuir um endereço de e-mail único no sistema.

Não será permitido cadastrar dois usuários utilizando o mesmo endereço de e-mail.

---

### RN02 — Autenticação

O usuário deverá informar credenciais válidas para acessar funcionalidades que exigem autenticação.

---

### RN03 — Tipos de usuário

O sistema deverá possuir, inicialmente, dois tipos de usuário:

- Aluno;
- Administrador.

Cada tipo possuirá permissões diferentes.

---

### RN04 — Acesso administrativo

Somente usuários com perfil de Administrador poderão cadastrar, editar ou excluir conteúdos da plataforma.

---

### RN05 — Organização das aulas

As aulas deverão estar associadas a um nível de dificuldade:

- Iniciante;
- Intermediário;
- Avançado.

---

### RN06 — Progressão do aluno

O progresso do aluno deverá ser registrado conforme ele concluir as aulas e atividades disponíveis.

---

### RN07 — Ganho de XP

O sistema deverá atribuir XP ao aluno conforme atividades determinadas forem concluídas.

A quantidade de XP poderá variar de acordo com a atividade.

---

### RN08 — Conclusão de aula

Uma aula será considerada concluída quando o aluno finalizar o conteúdo e completar a atividade associada, quando houver.

---

### RN09 — Quiz

Cada pergunta cadastrada deverá possuir uma resposta correta definida pelo administrador.

---

### RN10 — Resultado do quiz

Após finalizar um quiz, o sistema deverá calcular o resultado com base nas respostas fornecidas pelo aluno.

---

### RN11 — Conquistas

As conquistas serão desbloqueadas quando o aluno atingir determinadas condições previamente definidas pelo sistema.

---

### RN12 — Exclusão de conteúdo

Quando uma aula ou pergunta for excluída pelo administrador, o conteúdo não deverá ficar disponível para novos acessos.

---

### RN13 — Integridade dos dados

O sistema deverá evitar o cadastro de informações obrigatórias incompletas ou inválidas.

---

## 3. Resumo

| Código | Regra |
|---|---|
| RN01 | Cada e-mail deve ser único |
| RN02 | É necessário autenticar-se para acessar funções protegidas |
| RN03 | Existem Aluno e Administrador |
| RN04 | Apenas Administrador gerencia conteúdos |
| RN05 | Aulas possuem níveis |
| RN06 | O progresso deve ser registrado |
| RN07 | Atividades podem gerar XP |
| RN08 | Aulas possuem critérios de conclusão |
| RN09 | Quizzes possuem respostas corretas |
| RN10 | O sistema calcula o resultado dos quizzes |
| RN11 | Conquistas dependem de condições |
| RN12 | Conteúdos excluídos deixam de ser disponibilizados |
| RN13 | Dados obrigatórios devem ser validados |
