# LoginSessaoGluocrm
Gluocrm é uma plataforma focada em soluções Customer Relationship Management, onde dados de clientes e parceiros de empresas diversas podem ser registrados, movidos, editados, consultados entre outros. A plataforma oferece possibilidade de integração completa via API . 

- Esse script auxiliará os desenvolvedores a iniciarem a sessão via API na plataforma de forma mais rapida e simplificada, sem ter que se atentar com as etapas de inicialização de sessão descritos nos documentos de integração.

> Pagina comercial da ferramenta https://www.gluocrm.com.br/
> 
> Pagina da documentação de desenvolvimento da ferramenta https://developers.gluocrm.com.br/
>

# A baixo um fluxograma que demonstra o processo de autenticação na API (em duas etapas):
<img src="https://imgur.com/Oio8Sc0.png" />

<br><br/>

# Exemplificação da geração dos elementos para validação da sessão:

- token = '123'; // obtido no método getchallenge
- userkey = '456'; // cadastro do usuário (foi informado via e-mail)
- baseKey = '123456'; // juntando as duas chaves
- chave final = md5('123456'); // e10adc3949ba59abbe56e057f20f883e

- E então o md5 gerado é enviado via metodo POST com a chave "accessKey:e10adc3949ba59abbe56e057f20f883e" no corpo do request 


-  A resposta é remelhante a {
  "application/json": {
    "sessionName": "1eaf6c9d5d7a558d1e0z2",
    "userId": "19x1",
    "version": "0.22"
  }
}

<br><br/>

# GET_SESSION.PY

- Para utilização do script, antes obtenha as credenciais de acesso com o suporte da plataforma gluocrm.
> A conta que será utilizada para efetuar API Rest no portal GLUO obrigatoriamente deve obter permissão para acesso aos recursos disponibilizados no site.
> 
> É preciso obter tres dados de credenciais para utilização do script; Link, Nome do usuario, Chave de acesso da API
> 

- Biblioteca resquisitada: dotenv 
- Utilize pip install python-dotenv 

<br><br/>
- Utilize um arquivo .env para inserir as proprias credenciais

<img src="https://imgur.com/tz0iznu.png" />

- Salvo as credenciais já é possivel executar o script 

<img src="https://imgur.com/SEkdKmZ.png" />

- Executando o .py será exibido rapidamente a sessão iniciada com a API no terminal

<img src="https://imgur.com/TW3EkB9.png" />
  
- Tabém será criado um .txt nomeado session.txt contendo a chave gerada
> Se desejar remover -> linha 103 a 106

<img src="https://imgur.com/vJOcCFS.png" />

# Conclusão

- Script visa obter de forma rapida o parametro "sessionName" cujo qual é obrigatorio obter em toda e qualquer requisição enviados ao portal gluocrm via API.

<img src="https://imgur.com/pGnqjnh.png" />

> ~Alan Mateus Rodrigues
> 
> ~linkedin: https://www.linkedin.com/in/alan-rodrigues-983822218/
