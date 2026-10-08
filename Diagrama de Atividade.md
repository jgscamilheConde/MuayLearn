2. Diagrama de Atividade

O diagrama de atividade representa o fluxo de utilização do sistema pelo aluno, desde o login até a realização de uma aula e, quando disponível, a realização do quiz.

@startuml

start

:Aluno realiza login;

if (Credenciais válidas?) then (Sim)

    :Acessar área de aulas;
    :Selecionar aula;
    :Visualizar conteúdo;
    :Finalizar conteúdo;

    if (Existe quiz?) then (Sim)

        :Iniciar quiz;
        :Responder perguntas;
        :Finalizar quiz;

        :Sistema verifica respostas;
        :Calcular resultado;
        :Registrar resultado;
        :Adicionar XP;
        :Atualizar progresso;

        if (Condição de conquista atingida?) then (Sim)
            :Desbloquear conquista;
        else (Não)
        endif

        :Exibir resultado;

    else (Não)

        :Registrar conclusão da aula;
        :Atualizar progresso;

    endif

else (Não)

    :Exibir mensagem de erro;
    :Solicitar novas credenciais;

endif

stop

@enduml
