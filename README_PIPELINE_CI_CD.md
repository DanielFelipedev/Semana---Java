# NOVO PROJETO
# PIPELINE CI/CD - GITHUB-ACTIONS

# O QUE É UMA PIPELINE?
É UM CONJUNTO DE TAREFAS QUE AUTOMATIZAM ETAPAS PRA UM OBJETIVO NO FINAL

# O QUE É CI/CD?
uma prática de desenvolvimento de software que usa automação para construir, testar e lançar códigos com rapidez e segurança.

# ESTRUTURA DE UM SCRIPTS

    NAME: 

      >   ON: 

            >PUSH: --> essa daqui vai ser a ordem pra executar 

                > BRANCHES: 
         
                     > - MAIN --> branche principal que vai ser chamada 
         
                  > JOBS: --> Isso daqui se chama básicamente de etapas macro que depende de 
                              pequenas etaps micro pra executar
                        > BUILD: 
                           > RUNS-ON: ubuntu-latest
                           > STEPS: 