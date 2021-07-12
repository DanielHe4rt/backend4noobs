# 3.2 Tipos de Requisição HTTP

Se você tá se perguntando o que é um tipo de requisição eu vou te dar logo uns nomes pra gente começar a brincadeira: GET, POST, PUT e DELETE.

Esses nomezinhos ai são tipos de requisições onde você manda dados para o servidor preenchendo formulários, fazendo login em redes sociais ou até mesmo fazendo buscas em qualquer lugar.

Assim como os códigos HTTP, os tipos de requisições tem suas peculiaridades e são usados para coisas especificas.

Se você for traduzir o método GET, ele vira literalmente CONSEGUIR. Se você manda uma requisição pro google, pesquisando algo, você espera CONSEGUIR dados. 

O método GET tem a única missão de trazer dados, fazer consultas no servidor e nada mais. Se você usar o GET para mais do que além de trazer dados, pode ser que algo esteja errado na sua engenhoca chamada aplicação. Mas é aquele negócio né: funciona? Funciona! Mas até que ponto isso é bom?


O método POST é usado quando você precisa ENVIAR dados para o servidor, onde você vai diretamente IMPACTAR no servidor enquanto ele processa esses dados. Geralmente é dado por formulários de alguma coisa, podendo ser registro de algo, newsletter, login etc.

O método PUT é usado quando você quer ALTERAR algum dado dentro do seu servidor. Se você está editando o seu perfil de alguma rede social, o correto seria usar o PUT (ou o PATCH para atualizações parciais). 

O método DELETE é usado quando você precisa apagar algo via formulário. Esse é o mais óbvio né?

Mas ai você me pergunta: Aahh Daniel na minha empresa a gente usa GET e POST pra tudo. Tem problema?

Problema não tem, já tô surpreso de não usarem só GET. Mas, seria legal, vocês adequarem para que os métodos sejam usados corretamente. Já que é pra fazer o negócio, que tal fazer bem feito e garantir mais um pedacinho da integridade do software produzido? 

