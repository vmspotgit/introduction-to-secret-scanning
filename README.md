<header>

# Introdução à varredura de segredos

_O GitHub verifica repositórios em busca de tipos conhecidos de segredos, como chaves de API e tokens de autenticação, para prevenir o uso fraudulento de segredos que foram comprometidos acidentalmente. Neste curso do GitHub, você aprenderá como habilitar a varredura de segredos para identificar segredos e evitar que sejam comprometidos em seu repositório._

</header>

## Passo 2: Revisar e fechar alertas de verificação de segredos

_Você habilitou a verificação de segredos e adicionou um segredo para testar se o recurso está funcionando! :tada:_

No último passo, você habilitou a verificação de segredos no repositório e cometeu uma credencial da AWS no repositório. Neste passo, você primeiro revisará os alertas de verificação de segredos. Depois, você habilitará a proteção de push, que impede que você escreva acidentalmente credenciais em um repositório. Finalmente, você tentará escrever uma nova credencial para ver como a proteção de push funciona.

### :keyboard: Atividade 2.1: Visualizar todos os alertas de verificação de segredos

1. Abra uma nova aba do navegador e siga os passos na sua segunda aba enquanto lê as instruções nesta aba.
2. Navegue até a aba **Security** na barra de navegação superior do seu repositório.
3. Selecione **Secret Scanning** na barra de navegação à esquerda.

Esta página contém a lista de alertas de verificação de segredos. Você pode filtrar e classificar esta página com base em critérios como o estado do alerta (aberto ou fechado), validade e tipo de segredo. Você verá três alertas listados aqui.

- **Chave de Acesso Secreta da Amazon AWS**: Esta é a chave de acesso que você cometeu no último passo.
- **ID da Chave de Acesso da Amazon AWS**: Este é o ID da chave cometido no último passo.
- **Token de Acesso Pessoal do GitHub**: Este token já estava no arquivo `credentials.yml` antes de você começar.

### :keyboard: Atividade 2.2: Revisar um alerta de verificação de segredos

Nesta atividade, você explorará o alerta. Você revisará a validade de um segredo e identificará onde o segredo foi detectado no repositório.

Abra o alerta **ID da Chave de Acesso da Amazon AWS** e explore as informações exibidas.

- **Alert status**: Esta seção mostra o status atual do alerta (aberto ou fechado) e relata quando o alerta foi detectado pela primeira vez.

  ![Captura de tela do alerta de ID da Chave de Acesso da Amazon AWS com o status atual aberto destacado.](/images/alert-status.png)

- **Alert validity state**: Exibido apenas para tokens onde a verificação de segredos pode contatar a plataforma parceira para verificar se o token está ativo. Esta seção mostra o estado de validade: "Active", "Inactive" ou "Possibly active", e como remediar o segredo exposto. Um segredo tem o estado "Possibly active" até que a plataforma parceira valide que está ativo ou inativo.

  ![Captura de tela do alerta de ID da Chave de Acesso da Amazon AWS com o estado de validade destacado.](/images/alert-validity-state.png)

- **Secret location**: Esta seção descreve os locais onde o segredo foi identificado no seu repositório. Se o segredo existir em vários arquivos, a verificação de segredos vinculará a cada arquivo. O committer, um link para o SHA do commit e a data do commit também são incluídos para cada localização. Observe que você deve ignorar os dois primeiros locais, pois fazem parte da definição do curso. Você pode ver o token que adicionou em `credentials.yml` como o terceiro local.

  ![Captura de tela de um alerta com a localização do segredo destacada.](/images/secret-location.png)

- **Alert audit trail**: A trilha de auditoria do alerta contém quaisquer alterações no estado do alerta, bem como quem fez a alteração. Neste exemplo, o alerta tem apenas um evento "Aberto" até agora. Se o alerta for fechado, um novo evento será adicionado à trilha de auditoria.

  ![Captura de tela da parte inferior de um alerta com a trilha de auditoria destacada.](/images/audit-trail.png)

### :keyboard: Atividade 2.3: Fechar um alerta

Quando a verificação de segredos encontra um segredo no seu repositório, a primeira coisa que você deve fazer é desativar esse segredo no provedor. Isso impede qualquer uso futuro dessa credencial. Depois que o segredo for desativado, o próximo passo é fechar o alerta marcando-o como "Revoked". Nesta atividade, você abrirá um alerta que foi validado como "Inactive" pela verificação de segredos e, em seguida, marcará esse alerta como "Revoked".

1. Na sua outra aba, volte para a lista completa de alertas de verificação de segredos, usando o link **Secret scanning alerts** no canto superior esquerdo do alerta ou usando a aba **Security** conforme descrito acima.
2. Na lista de alertas de verificação de segredos, abra o alerta intitulado **GitHub Personal Access Token**.
3. No topo deste alerta, se o alerta estiver marcado como "Secret inactive on github.com", então a verificação de segredos já validou essa credencial e descobriu que está desativada. Se o alerta ainda estiver marcado como "Possibly active secret", clique no botão **Verify secret** para validar agora.
5. Agora que sabemos que este segredo não está mais ativo, estamos prontos para fechar o alerta. Selecione o dropdown **Close as** e escolha **Revoked**.
7. Insira um comentário na caixa de texto.
8. Escolha **Close alert**.
   ![Captura de tela do alerta de Token de Acesso Pessoal do GitHub, as opções de fechar alerta estão ativadas e a opção "revogado" está destacada. O campo de comentário foi preenchido com "segredo inativo".](/images/revoke-token.png)
9. Observe que o alerta agora tem um estado de "Closed" e que a trilha de auditoria na parte inferior do alerta mostra que você fechou o alerta como revogado.

## Passo 3: Habilitar proteção de push

_Muito bem! Você revisou e fechou um alerta de verificação de segredos! :tada:_

Até agora, você aprendeu como identificar segredos já armazenados no seu repositório. Nesta seção, você habilitará a proteção de push no repositório para impedir que novos segredos sejam escritos no repositório.

**O que é proteção de push**: Quando alguém tenta enviar alterações de código para o GitHub (um push), a verificação de segredos verifica segredos de alta confiança (aqueles identificados com uma baixa taxa de falso positivo). A verificação de segredos lista quaisquer segredos que detecta para que o autor possa revisar os segredos e removê-los ou, se necessário, permitir que esses segredos sejam enviados.

### :keyboard: Atividade 3.1: Habilitar proteção de push

A proteção de push está habilitada por padrão para todos os repositórios públicos. Se você estiver trabalhando em um repositório público, pode ir direto para "Atividade 3.2: Tentar enviar um segredo." Para repositórios privados ou internos, habilite a proteção de push nas "Settings" do repositório.

1. Abra uma nova aba do navegador e siga os passos na sua segunda aba enquanto lê as instruções nesta aba.
2. Navegue até **Settings** na barra de navegação superior.
3. Na seção "Security" à esquerda, selecione **Advanced Security**.
4. Role até o final da página e selecione **Enable** ao lado de "Push Protection".

### :keyboard: Atividade 3.2: Tentar enviar um segredo

Agora que a proteção de push para a verificação de segredos está habilitada, novos segredos que a verificação de segredos tem alta confiança em identificar serão bloqueados de serem escritos no repositório. Nesta atividade, você comprometerá uma nova credencial ao repositório para experimentar a proteção de push.

1. Na sua outra aba do navegador, clique em **Code** na barra de navegação superior.
2. Abra o arquivo `credentials.yml`.
3. Clique no botão **Edit** (ícone de lápis) à direita.
4. Copie e cole a seguinte string no final do arquivo:

    ```
      github-token: github_pat_<REMOVEME>11A4YXR6Y0v36CYFkuT5I1_ZRWX91c8k0waSN6x7AiVJ6zZ9ZHUQXBblBqFQpKd23V6CL7MWMPopnmBxzn
    ```

5. Exclua `<REMOVEME>` da string que você acabou de colar. A string `<REMOVEME>` está lá para que a verificação de segredos não crie um alerta antes que você possa testar a proteção de push. Seu arquivo deve ficar assim:

    ![Captura de tela do credentials.yml sendo editado na interface web do GitHub. Um github-token recém-adicionado está destacado.](/images/push-protection.png)

6.  Selecione **Commit changes...**.
7.  Selecione **Commit changes**.
8.  Em vez de cometer o arquivo atualizado no seu repositório, um alerta de proteção de push avisa que suas mudanças incluem um Token de Acesso Pessoal do GitHub.

> [!DICA]
> Quando você trabalha em um ambiente local ou em um GitHub Codespace, a verificação de segredos não pode bloquear seu commit. Em vez disso, seu push para o GitHub é bloqueado. Nesse caso, se o segredo estiver ativo, você precisará remover o segredo da sua branch e do histórico de commits, veja [Resolvendo um push bloqueado na linha de comando](https://docs.github.com/en/code-security/secret-scanning/pushing-a-branch-blocked-by-push-protection#resolving-a-blocked-push-on-the-command-line).

### :keyboard: Atividade 3.3: Ignorar proteção de push

Agora que você está ciente do segredo em suas mudanças, você deve remover o segredo e tentar o commit novamente. Em alguns casos, você pode estar disposto a aceitar o risco de adicionar um segredo ao seu repositório. Nesses casos, você pode optar por ignorar a proteção de push. Nesta atividade, você ignorará a proteção de push e escreverá o token no seu repositório (não se preocupe, o token de exemplo é seguro).

1. Selecione o botão de rádio ao lado de **It's used in tests**.
2. Clique em **Allow secret**.
3. Um banner de notificação informa que você agora pode cometer o segredo.
4. Selecione **Commit changes...** novamente.
5. Selecione **Commit changes**.

Espere cerca de 20 segundos e então atualize esta página (a página onde você está seguindo as instruções). Um workflow do GitHub Actions no repositório será executado e substituirá automaticamente o conteúdo deste arquivo `README` com instruções para o próximo passo.

<footer>

---

Obter ajuda: [Poste em nosso fórum de discussão](https://github.com/skills/.github/discussions) &bull; [Revise a página de status do GitHub](https://www.githubstatus.com/)

&copy; 2025 GitHub &bull; [Código de Conduta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

</footer>
