<header>

# Introdução à varredura de segredos

_O GitHub verifica repositórios em busca de tipos conhecidos de segredos, como chaves de API e tokens de autenticação, para prevenir o uso fraudulento de segredos que foram comprometidos acidentalmente. Neste curso do GitHub, você aprenderá como habilitar a varredura de segredos para identificar segredos e evitar que sejam comprometidos em seu repositório._

</header>

## Bem-vindo

Credenciais em texto simples acidentalmente armazenadas em repositórios no GitHub são um alvo comum para atacantes. De fato, encontramos bem mais de um milhão de tokens armazenados na plataforma GitHub a cada ano. A varredura de segredos é uma ferramenta poderosa que permite às equipes identificar essas credenciais em texto simples, removê-las e criar regras para evitar que sejam escritas no GitHub em primeiro lugar.

A varredura de segredos está disponível gratuitamente para repositórios públicos em todos os planos. Empresas que necessitam de capacidades de varredura de segredos para repositórios privados devem revisar o [GitHub Advanced Security](https://docs.github.com/en/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security). O GitHub Advanced Security permite usar a varredura de segredos e outros recursos de segurança em repositórios privados e internos.

- **Para quem é este curso**: Desenvolvedores, Engenheiros DevOps, equipes de segurança.
- **O que você aprenderá**: Como identificar credenciais em texto simples no seu repositório e como evitar que sejam expostas no GitHub em futuros commits.
- **Pré-requisitos**: Noções básicas de git e funcionalidades do GitHub. Recomendamos que você complete o curso [Introdução ao GitHub](https://github.com/skills/introduction-to-github).
- **Quanto tempo**: Este curso leva menos de 15 minutos para ser concluído.

Neste curso, você irá:

1. Habilitar a varredura de segredos
2. Identificar segredos armazenados em seu repositório
3. Habilitar a proteção de push
4. Evitar que segredos sejam escritos em seu repositório

### Como iniciar este curso

[![start-course](https://raw.githubusercontent.com/dev-pods/introduction-to-secret-scanning/873eb13decfe79fd486ff84bd97de0dab4912d9a/images/botao.svg)](https://github.com/new?template_owner=dev-pods&template_name=introduction-to-secret-scanning&owner=%40me&name=introduction-to-secret-scanning&description=GitHub+Habilidades:+Introdução+para+Secret+Scanning&visibility=public)

1. Clique com o botão direito em **Iniciar curso** e abra o link em uma nova aba.
2. Na nova aba, a maioria dos prompts será preenchida automaticamente para você.
   - Para o proprietário, escolha sua conta pessoal ou uma organização para hospedar o repositório.
   - Você precisará tornar o repositório público, pois repositórios privados não têm acesso à varredura de segredos sem uma licença do [GitHub Advanced Security](https://docs.github.com/en/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security).
   - Role para baixo e clique no botão **Criar repositório** na parte inferior do formulário.
3. Após a criação do seu novo repositório, espere cerca de 20 segundos e atualize a página. Siga as instruções passo a passo no README do novo repositório.

<footer>

---

Obter ajuda: [Poste em nosso fórum de discussão](https://github.com/skills/.github/discussions) &bull; [Revise a página de status do GitHub](https://www.githubstatus.com/)

&copy; 2025 GitHub &bull; [Código de Conduta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

</footer>
