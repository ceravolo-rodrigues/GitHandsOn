

## Baixe Putty para Windows (Opte pela versão MSI)
https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

## Instale
Next-next-finish :)

## Execute o cmd do Windows e digite
`cd c:\Users\NOME_DO_USER`
`mkdir .ssh`

*Já deixe o Github logado para facilitar*

## Gerando as chaves 

- Abra  puttygen
- Clique em GENERATE
- Mova seu mouse aleatoriamente
- A tela abaixo irá aparecer
![](https://vladmihalcea.com/wp-content/uploads/2014/04/puttygen-save-private-key.png)
- Copie o conteúdo PUBLIC KEY (ctrl+c mesmo). **Não feche o app**
- Vá no Perfil do GitHub -> Chaves SSH e GPG . Clique em NOVA CHAVE SSH (Esse é o link direto https://github.com/settings/ssh/new )
![](https://vladmihalcea.com/wp-content/uploads/2014/04/github-add-key1.png)
- Dê um nome sugestivo. MEU-PC. 
- Cole a chave copiada. Clique em adicionar
- Volte ao Puttygen. 
- Coloque uma passphrase para segurança. Ela será perguntada a cada ação com REMOTE.
- Salve a chave privada em C:\Users\NOME_DO_USER\\.ssh\github-rsa.ppk
- Abra o PAGEANT
- Vá no System tray e clique no ícone do PAGEANT e Clique com o Botão direito e escolha Adicione a chave

# DICA 
## Adicione o pageant na lista de programas que iniciam com windows
- WindowsKey + R
- Digite shell:startup
- Crie um atalho. 
- Em target coloque  "C:\Program Files\PuTTY\pageant.exe" github-rsa.ppk . 
- Em Start in coloque C:\Users\NOME_DO_USER\\.ssh\

# Problemas comuns
>Saída do git após algum comando:
 FATAL ERROR: No supported authentication methods available (server sent: publickey)
- Talvez Seu PAGEANT não esteja Rodando
- Talvez seu PAGEANT esta rodando mas a chave não está adicionada