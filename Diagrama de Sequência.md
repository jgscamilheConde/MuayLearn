3. Diagrama de Sequência

O diagrama de sequência representa a interação entre o aluno, a interface, o sistema e o banco de dados durante a realização de um quiz.

@startuml

actor Aluno

participant "Interface" as Interface
participant "Sistema" as Sistema
database "Banco de Dados" as BD

Aluno -> Interface: Acessa o quiz

Interface -> Sistema: Solicitar quiz

Sistema -> BD: Buscar perguntas
BD --> Sistema: Retornar perguntas

Sistema --> Interface: Enviar perguntas
Interface --> Aluno: Exibir perguntas

Aluno -> Interface: Responder perguntas

Interface -> Sistema: Enviar respostas

Sistema -> BD: Consultar respostas corretas
BD --> Sistema: Retornar respostas

Sistema -> Sistema: Calcular pontuação

Sistema -> BD: Registrar resultado
Sistema -> BD: Atualizar progresso
Sistema -> BD: Adicionar XP

BD --> Sistema: Dados atualizados

Sistema --> Interface: Retornar resultado
Interface --> Aluno: Exibir pontuação e progresso

@enduml
