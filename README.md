# N8N - Configuração de sistema

- O que é necessário?
    1. Docker
    2. Conta no Ngrok

- Configurações da conta:
    - Para utilizar o n8n local só é necessário somente uma conta, de nível gratuito, no ngrok
    - É necessário configurar um dominio estático que sera utilizado durante o processo
        - Esse página explica como criar o dominio [Static domains for all ngrok users](https://ngrok.com/blog-post/free-static-domains-ngrok-users), sendo não necessário definir um endpoint, para o sistema que vamos fazer.

- Como iniciar?
    - Apos criar a conta no ngrok e criar o dominio, crie um arquivo .env com base no .env.example e adicione todos os dados necessários nessa ordem:
        1. N8N_BASIC_AUTH_USER: nome do usuário para o n8n, pode ser escolhe a vontade
        2. N8N_BASIC_AUTH_PASSWORD: senha para acessar a conta do n8n
        3. N8N_HOST: sera igual ao NGROK_DOMAIN
        4. NGROK_AUTHTOKEN: Token do ngrok, quando criar a conta você já possue acesso a ele
        5. NGROK_DOMAIN: nome do dominio do ngrok sem https://
        6. WEBHOOK_URL: nome do dominio completo
    
    - Por fim, use o comando no diretorio do projeto:
        ```bash
        docker compose up -d
        ```