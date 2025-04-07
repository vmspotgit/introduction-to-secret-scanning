## Passo 1: Habilitar Verificação de Segredos

_Bem-vindo ao "Introdução à Verificação de Segredos"! :wave:_

Neste passo, você habilitará a verificação de segredos neste repositório. Uma vez que a verificação de segredos estiver habilitada, você adicionará uma nova credencial para ver como a verificação de segredos identifica a credencial.

**O que é um segredo**: No contexto da verificação de segredos, um segredo (ou credencial) é uma string em texto simples, ou um par de strings, que autoriza um usuário a acessar um serviço. Exemplos podem ser chaves/IDs de acesso secreto da AWS, chaves de API do Google ou tokens de API do Stripe. A documentação do GitHub hospeda uma lista de [todos os padrões suportados](https://docs.github.com/en/code-security/secret-scanning/secret-scanning-patterns#supported-secrets).

### :keyboard: Atividade 1.1: Habilitar verificação de segredos

A verificação de segredos está habilitada por padrão para todos os novos repositórios públicos. Se você estiver trabalhando em um repositório público, pode ir direto para "Atividade 1.2: Cometer um token." Para repositórios privados ou internos, a verificação de segredos está disponível com o [GitHub Advanced Security](https://docs.github.com/en/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security).

1. Abra uma nova aba do navegador e siga os passos na sua segunda aba enquanto lê as instruções nesta aba.
2. No seu repositório recém-criado, selecione **Settings** na barra de navegação superior.
3. Na seção **Security** à esquerda, selecione **Secret Scanning**.
4. Role até o final desta página e selecione o botão **Enable** ao lado de "Secret scanning."

> [!IMPORTANTE]
> Quando você habilita a verificação de segredos, pode receber uma notificação por e-mail sobre credenciais no seu repositório. Não se preocupe! Os tokens neste repositório de habilidades estão inativos. Não há risco para o seu ambiente.

### :keyboard: Atividade 1.2: Comitar um token

Agora que você habilitou a verificação de segredos neste repositório, vamos comiter um novo token para ver como isso funciona. Você comprometerá uma chave e ID de acesso da AWS no repositório. Não se preocupe, este é um token inativo que não pode ser usado para fazer login na AWS.

1. Você deve continuar a trabalhar nas atividades em uma segunda aba do navegador.
2. Clique na aba **Code** no seu repositório.
3. Exiba o arquivo `credentials.yml`.
4. Clique no botão "Edit" à direita.

    ![Uma captura de tela do credentials.yml na interface web do GitHub com o botão de edição destacado](/images/edit-credentials-file.png)

5. Copie o texto a seguir e cole-o no final do arquivo `credentials.yml`.

    ```yaml
    default:
      aws_access_key_id: AKIAQYLPMN5HNM4OZ56B
      aws_secret_access_key: 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
      output: json
      region: us-east-2
    ```

6. Clique em **Commit changes...** no canto superior direito. A janela "Commit changes" será exibida. Deixe as configurações padrão e clique em **Commit changes** para cometer diretamente na branch `main`.

Espere cerca de 20 segundos e então atualize esta página (a página onde você está seguindo as instruções). Um workflow do GitHub Actions no repositório será executado e substituirá automaticamente o conteúdo deste arquivo `README` com instruções para o próximo passo.
