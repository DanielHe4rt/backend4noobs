# 4.3 Autenticação: OAuth

### Autenticação x Autorização

Antes de começarmos a falar sobre OAuth, precisamos definir dois conceitos chave sobre o processo de controle de acesso em uma API. São eles: Autenticação e Autorização.

> **Autenticação** é quando o sistema identifica quem você é. Quando você faz o login em um sistema, se identificando com usuário e senha, houve uma autenticação de que é realmente você que está conversando com o sistema.

> **Autorização** é quando o sistema diz se você (já autenticado) tem permissão para acessar determinado recurso dele.

Vamos supor que você, usuário fulano, faça o login no sistema X.

O sistema X vai verificar se seu usuário e senha estão corretos. Caso estejam, você está **autenticado** no sistema.

Agora vamos supor que você, usuário fulano já **autenticado**, quer ver a listagem de produtos que o sistema fornece. Se o seu usuário tiver a **autorização** necessária, o sistema irá mostrar a lista solicitada. Caso não tiver a **autorização**, mesmo que esteja **autenticado**, o sistema não permitirá que você tenha acesso a esse recurso.

### OAuth x OAuth 2.0

OAuth é um padrão aberto estabelecido para realizar autenticação e autorização entre sistemas diferentes através de APIs.

Sua versão 2.0, amplamente mais utilizada nas aplicações de hoje, implementa funcionalidades discutidas durante a adoção da sua primeira versão. Portanto, além de não ser compatível com a versão 1.0, o OAuth 2.0 representa uma versão mais segura, compatível e aperfeiçoada do padrão. Vamos centralizar os estudos exclusivamente na versão 2.0 porque, além de atualizada é a versão amplamente utilizada.

### OAuth 2.0

Para explicarmos o padrão de autenticação e autorização OAuth 2.0, precisamos conceituar três responsabilidades base do padrão, que são a *aplicação cliente*, o *servidor de autorização* e o *servidor de recursos*.

> **Aplicação cliente:** É a aplicação que faz a solicitação de autenticação e autorização para os servidores. É através dessa aplicação cliente que o usuário informa seus dados. Na maioria dos casos é uma aplicação _frontend_ propriamente dita. Na autenticação e autorização, essa aplicação cliente deve informar os dados do usuário que deseja se autenticar e também suas próprias credenciais próprias de aplicação, para que o servidor de autorização verifique se essa aplicação está permitida de usar a sua autenticação.

> **Servidor de autorização:** É o servidor que irá fornecer a autenticação solicitada do usuário. Uma vez que um usuário, através da aplicação cliente, solicita sua autenticação, o servidor de autorização irá retornar um token com sua autenticação e suas autorizações.

> **Servidor de recursos:** É o servidor que irá fornecer os recursos da aplicação principal. Por exemplo, em um _e-commerce_ é esse servidor que vai responder com os produtos, vendas, etc. Com o token de autorização em mãos, a aplicação cliente faz a solicitação do que deseja para o servidor de recursos, que por sua vez irá fornecer ou não as informações com base na autenticação e autorização previamente informadas por esse usuário.

_Observação: Por mais que o servidor de autorização e o servidor de recursos possuam responsabilidades diferentes, os mesmos podem ser implementados e configurados na mesma aplicação. Ao implementar essas duas responsabilidades em uma única API, essa terá um sistema de autenticação e autorização completo._

_Alguns exemplos de autenticação e autorização que usam OAuth 2.0 e são em servidores de autorização e de recursos separados são os famosos _logins_ automáticos via Facebook, Google, etc._

Vamos a um exemplo de um fluxo de autenticação e autorização com OAuth 2.0:

- A *aplicação cliente* solicita, passando usuário, senha e credenciais da aplicação, um Token de acesso para o *servidor de autorização*.
- O *servidor de autorização* verifica que a aplicação tem permissão e os dados do usuário são válidos. Agora, esse servidor devolver um Token de acesso para a *aplicação cliente*.
- A *aplicação cliente* solicita uma lista de produtos para o *servidor de recursos*. Esse servidor, por sua vez, valida o Token de acesso. Estando tudo ok com a autenticação e a autorização, o *servidor de recursos* retorna a lista de produtos solicitada para a *aplicação cliente*.

**Site oficial do OAuth 2.0: https://oauth.net/2/**
