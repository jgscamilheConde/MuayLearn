# Casos de Uso — Muay Learn

## 1. Atores

### 1.1 Aluno

Usuário que utiliza o Muay Learn para aprender os fundamentos do Muay Thai.

O aluno pode:

- Criar uma conta;
- Realizar login;
- Visualizar aulas;
- Acessar conteúdos;
- Realizar quizzes;
- Visualizar resultados;
- Acompanhar seu progresso;
- Ganhar XP;
- Visualizar conquistas.

### 1.2 Administrador

Usuário responsável pelo gerenciamento da plataforma.

O administrador pode:

- Realizar login;
- Cadastrar aulas;
- Editar aulas;
- Excluir aulas;
- Cadastrar perguntas;
- Editar perguntas;
- Excluir perguntas;
- Gerenciar usuários.

---

# 2. UC01 — Cadastrar usuário

**Ator principal:** Aluno

**Objetivo:** Permitir que uma pessoa crie uma conta no Muay Learn.

### Pré-condições

Não é necessário possuir uma conta.

### Fluxo principal

1. O usuário acessa a tela de cadastro.
2. O sistema solicita nome, e-mail e senha.
3. O usuário informa os dados.
4. O sistema valida os dados.
5. O sistema verifica se o e-mail já está cadastrado.
6. O sistema cria a conta.
7. O sistema informa que o cadastro foi realizado com sucesso.

### Fluxo alternativo

Se o e-mail já estiver cadastrado, o sistema deverá informar o usuário e impedir a criação de uma nova conta com o mesmo e-mail.

### Pós-condição

O usuário passa a possuir uma conta no sistema.

---

# 3. UC02 — Realizar login

**Atores:** Aluno e Administrador

**Objetivo:** Permitir que um usuário autenticado acesse as funcionalidades correspondentes ao seu perfil.

### Fluxo principal

1. O usuário acessa a tela de login.
2. Informa seu e-mail.
3. Informa sua senha.
4. O sistema verifica as credenciais.
5. O sistema identifica o tipo de usuário.
6. O sistema libera o acesso.

### Fluxo alternativo

Caso as credenciais estejam incorretas, o sistema informa que o e-mail ou senha são inválidos.

### Pós-condição

O usuário está autenticado no sistema.

---

# 4. UC03 — Visualizar aulas

**Ator principal:** Aluno

**Objetivo:** Permitir que o aluno encontre os conteúdos disponíveis.

### Fluxo principal

1. O aluno acessa a área de aulas.
2. O sistema apresenta os conteúdos disponíveis.
3. O sistema organiza as aulas por nível.
4. O aluno seleciona uma aula.
5. O sistema apresenta os detalhes da aula.

### Pós-condição

O aluno consegue acessar o conteúdo desejado.

---

# 5. UC04 — Realizar aula

**Ator principal:** Aluno

**Objetivo:** Permitir que o aluno estude o conteúdo de uma aula.

### Fluxo principal

1. O aluno seleciona uma aula.
2. O sistema apresenta o conteúdo.
3. O aluno estuda o material.
4. O aluno finaliza o conteúdo.
5. O sistema verifica se existe atividade associada.
6. Caso exista, o sistema disponibiliza o quiz.

### Pós-condição

A aula fica disponível para conclusão através da atividade associada.

---

# 6. UC05 — Realizar quiz

**Ator principal:** Aluno

**Objetivo:** Verificar o conhecimento adquirido pelo aluno.

### Fluxo principal

1. O aluno inicia o quiz.
2. O sistema apresenta as perguntas.
3. O aluno seleciona suas respostas.
4. O aluno finaliza o quiz.
5. O sistema verifica as respostas.
6. O sistema calcula a pontuação.
7. O sistema apresenta o resultado.
8. O sistema registra a conclusão.
9. O sistema adiciona XP conforme as regras definidas.

### Pós-condição

O resultado do quiz fica registrado no sistema.

---

# 7. UC06 — Acompanhar progresso

**Ator principal:** Aluno

**Objetivo:** Permitir que o aluno acompanhe sua evolução.

### Fluxo principal

1. O aluno acessa seu perfil.
2. O sistema consulta os dados de progresso.
3. O sistema apresenta aulas concluídas.
4. O sistema apresenta XP acumulado.
5. O sistema apresenta nível atual.
6. O sistema apresenta conquistas desbloqueadas.

### Pós-condição

O aluno visualiza sua evolução na plataforma.

---

# 8. UC07 — Gerenciar aulas

**Ator principal:** Administrador

**Objetivo:** Permitir o gerenciamento dos conteúdos educacionais.

### Fluxo principal

1. O administrador acessa o painel administrativo.
2. O sistema verifica suas permissões.
3. O administrador escolhe uma operação:
   - cadastrar;
   - editar;
   - excluir.
4. O sistema executa a operação escolhida.
5. O sistema confirma a operação.

### Pós-condição

As informações das aulas são atualizadas.

---

# 9. UC08 — Gerenciar perguntas

**Ator principal:** Administrador

**Objetivo:** Permitir o gerenciamento das perguntas utilizadas nos quizzes.

### Fluxo principal

1. O administrador acessa o gerenciamento de perguntas.
2. O sistema apresenta as perguntas cadastradas.
3. O administrador escolhe uma operação.
4. O administrador pode cadastrar, editar ou excluir uma pergunta.
5. O sistema valida os dados.
6. O sistema salva a alteração.

### Pós-condição

As perguntas do quiz são atualizadas.

---

# 10. UC09 — Gerenciar usuários

**Ator principal:** Administrador

**Objetivo:** Permitir que o administrador visualize e gerencie usuários.

### Fluxo principal

1. O administrador acessa o gerenciamento de usuários.
2. O sistema apresenta os usuários cadastrados.
3. O administrador seleciona um usuário.
4. O sistema apresenta suas informações.
5. O administrador realiza a operação permitida.
6. O sistema registra a alteração.

### Pós-condição

As informações do usuário são atualizadas.

---

# 11. Relação entre casos de uso

O caso de uso **Realizar Quiz** inclui a verificação das respostas e o registro do resultado.

A conclusão do quiz pode gerar a atualização do progresso e a atribuição de XP.

O caso de uso **Acompanhar Progresso** utiliza as informações registradas durante as atividades do aluno.

O Administrador possui acesso aos casos de uso relacionados ao gerenciamento do conteúdo e dos usuários.
