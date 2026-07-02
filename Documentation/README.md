# Informações Gerais
## Configurações git
A primeira coisa que deve estar configurada é a sua identificação, cadastre o seu email do github e nome de usuário, caso seu email do hithub seja privado, lembre de colocar o email público gerado pelo github, você pode conseguir esse email na sua página de configuraçãoes. Após isso você tem que configurar a assinatura dos commits, primeiro autorize o git a assinar os commits com o comando "git config --global commit.gpgsign true", depois rode o comando "gpg --full-generate-key" para gerar a chave, use as opções RSA e RSA, 4096 bits, coloque os mesmos nomes de usuário e email que cadastrou no git.  
Com o sua [chave] configure a chave de assinatura do git "git config --global user.signingkey [chave]", assim já pode assinar seus commits, após isso deve rodar o comando "gpg --armor --export [chave]" e copiar todo o texto que aparecer, incluindo as linhas com traços "----", com esse contudo vá no seu perfil do github e na página de configuração clique em SSH e GPG keys, depois "New GPG key" e cole o conteudo que apareceu no terminal. Após isso você já poderá fazer commits no repositório caso esteja cadastrado como colaborador.  
A chave pode ser encontrada em 3 lugares principais:
- Quando você cadastra a chave ele mostra na tela o código alpha numérico.
- Se você já tiver feito um commit assinado ele mostra a chave de assinatura ao rodar o comando "git log --show-signature" ele irá mostrar informações da assinatura, incluindo a chave.
- Mais diretamente, você pode rodar o comando "gpg --list-secret-keys --keyid-format=long" para verificar as chaves cadastradas.

## Informações de commit 
- Faça o pull do repositório
- Rode os testes
- Se os testes falharem corrija e volte para o começo
- Após os testes passarem faça o commit em uma branch de desenvolvimento
- Faça o push da branch de desenvolvimento
- Vá para o repositório e crie o pull request
- Espere aprovação do pull request
- Caso seja recusado corrija os problemas e volte para o inicio