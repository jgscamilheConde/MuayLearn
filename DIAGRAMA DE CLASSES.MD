4. Diagrama de Classes

O diagrama de classes apresenta as principais classes do sistema, seus atributos, métodos e relacionamentos.

@startuml

class Usuario {
    - id: int
    - nome: String
    - email: String
    - senha: String
    - tipo: String

    + cadastrar()
    + realizarLogin()
}

class Aluno {
    - xp: int
    - nivel: int

    + realizarQuiz()
    + acompanharProgresso()
    + ganharXP()
}

class Administrador {

    + cadastrarAula()
    + editarAula()
    + excluirAula()
    + gerenciarPerguntas()
    + gerenciarUsuarios()
}

class Aula {
    - id: int
    - titulo: String
    - descricao: String
    - nivel: String
    - conteudo: String

    + visualizar()
}

class Quiz {
    - id: int
    - titulo: String

    + iniciar()
    + finalizar()
    + calcularResultado()
}

class Pergunta {
    - id: int
    - enunciado: String
    - alternativaA: String
    - alternativaB: String
    - alternativaC: String
    - alternativaD: String
    - respostaCorreta: String
}

class Progresso {
    - id: int
    - aulasConcluidas: int
    - xp: int
    - nivel: int

    + atualizar()
}

class Conquista {
    - id: int
    - nome: String
    - descricao: String
    - requisito: String

    + desbloquear()
}

Usuario <|-- Aluno
Usuario <|-- Administrador

Aluno "1" -- "1" Progresso
Aluno "1" -- "*" Conquista
Aluno "*" -- "*" Aula

Aula "1" -- "0..1" Quiz
Quiz "1" -- "*" Pergunta

Administrador --> Aula
Administrador --> Quiz
Administrador --> Pergunta
Administrador --> Usuario

@enduml
