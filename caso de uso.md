#1. Diagrama de Casos de Uso

O diagrama de casos de uso apresenta as principais funcionalidades do sistema e a interação entre os atores Aluno e Administrador.

@startuml
left to right direction

skinparam packageStyle rectangle

actor "Aluno" as Aluno
actor "Administrador" as Admin

rectangle "Muay Learn" {

    usecase "Cadastrar usuário" as UC01
    usecase "Realizar login" as UC02
    usecase "Visualizar aulas" as UC03
    usecase "Realizar aula" as UC04
    usecase "Realizar quiz" as UC05
    usecase "Acompanhar progresso" as UC06
    usecase "Visualizar conquistas" as UC07

    usecase "Gerenciar aulas" as UC08
    usecase "Gerenciar perguntas" as UC09
    usecase "Gerenciar usuários" as UC10

    usecase "Verificar respostas" as UC11
    usecase "Registrar resultado" as UC12
    usecase "Adicionar XP" as UC13
}

Aluno --> UC01
Aluno --> UC02
Aluno --> UC03
Aluno --> UC04
Aluno --> UC05
Aluno --> UC06
Aluno --> UC07

Admin --> UC02
Admin --> UC08
Admin --> UC09
Admin --> UC10

UC05 ..> UC11 : <<include>>
UC05 ..> UC12 : <<include>>
UC05 ..> UC13 : <<include>>

@enduml
