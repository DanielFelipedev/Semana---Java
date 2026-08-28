# NOVO PROJETO
# PIPELINE CI/CD - GITHUB-ACTIONS

# O QUE É UMA PIPELINE?
É UM CONJUNTO DE TAREFAS QUE AUTOMATIZAM ETAPAS PRA UM OBJETIVO NO FINAL

# O QUE É CI/CD?
uma prática de desenvolvimento de software que usa automação para construir, testar e lançar códigos com rapidez e segurança.
CI/CD significa Integração Contínua (Continuous Integration) e Entrega ou Implantação Contínua (Continuous Delivery/Deployment).
Básicamente você dizer que está testando se minha integração da minha aplicação continua funcionando. 
# O Que Seria integração "Continuous Integration" ?
- Vejo a build se estar funcionando 
- Teste unitários estão funcionando
- Teste de integração estar funcionando


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
                                - name: checkout code       ----\
                                                                 > Ele fica responsável pra fazer o 
                                                                    git-clone e o checkout pra branche específica que tô cirando na pipeline
                                  uses: actions/checkout@v2 ----/

                                - name: Set up Node.js         ----------\
                                  uses: actions/setup-node@v2             \
                                                                           > - Nessa parte aqui é básicamente fazer uma instalação
                                                                           >  da linguagem que você escolher, ele precisa disso pra depois
                                                                           >  instalar as dependências que você precisar pra fazer os teste na aplicação   
                                  with:                                   /
                                    node-version: "14"  -----------------/
 
                                  - 