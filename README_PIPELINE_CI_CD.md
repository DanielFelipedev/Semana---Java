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

    name: Notificar por email no push
        on:
            push:
        branches:
            - main
        
    jobs:
        send-email:
        runs-on: ubuntu-latest
    steps:
        - name: Enviar email
        uses: dawidd6/action-send-mail@v3
    with:
        server_address: smtp.gmail.com
        server_port: 465
        username: ${{ secrets.EMAIL_USERNAME }}
        password: ${{ secrets.EMAIL_PASSWORD }}
        subject: "Novo push no repositório!"
        to: seuemail@gmail.com
        from: GitHub Actions
        body: "Você acabou de fazer um push na branch main. Confira: ${{ github.event.head_commit.url }}"