
# Adicionando Chaves SSH no Ubuntu
No terminal, digite

`$cd ~/.ssh`

Caso o terminal não exiba a Frase de arquivo ou diretório não encontrado prossiga para **Adicionando chaves**

Caso o terminal exiba: `bash: cd: ./.ssh:Nenhum arquivo ou diretório ` , você deverá gerar um par de rsa ket público / privado  com 
> ` ssh-keygen -t rsa -C "seu@email.com"`

- Siga as instruções da tela setando onde a chave será salva e a passphrase (se necessário)

## Adicionando chaves

` mkdir key_backup`
` cd id_rsa* key backup`
` rm id_rsa*`

- Abra o terminal e digite `gedit id_rsa.pub`
- O Ubuntu abrirá um arquivo, copie todo o seu conteúdo:
- Abra o site do github e faça o login.
- Vá no Perfil do GitHub -> Chaves SSH e GPG . Clique em NOVA CHAVE SSH (Esse é o link direto https://github.com/settings/ssh/new ) \
![](https://vladmihalcea.com/wp-content/uploads/2014/04/github-add-key1.png)

- Abra o terminal novamente e digite o seguinte comando `ssh-add`