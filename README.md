# N8N - Configuração de sistema

- O que é necessário?
    1. Docker
    2. Usar o LocalTunnel (opcional)

- Configurações para criar um webhook:
    - Instalar o LocalTunnel via npm (é necessário NodeJS)
    - Comando de instalação:

      ```bash
      npm install -g localtunnel
      ```

- Como iniciar?
    - É necessário criar um arquivo .env e adicionar estas informações no arquivo (use o .env.example para criar seu .env):
        1. N8N_BASIC_AUTH_USER: nome do usuário para o n8n, pode ser escolhe a vontade
        2. N8N_BASIC_AUTH_PASSWORD: senha para acessar a conta do n8n
        3. LT_SUBDOMAIN: nome do subdominio do localtunnel (ex: meu-projeto-tunnel)

    - Use este comando no diretorio do projeto para criar o container n8n:
        ```bash
        docker compose up -d
        ```

    - Para ativar um webhook com tunnel (permite comunicação externa com sua maquina para testes, não é recomendado para produção por questões de segurança) [opcional] use este comando no seu terminal:
        ```bash
        lt --port 5678 --subdomain meu-projeto-tunnel # Aqui você coloca o nome do seu subdominio, faça o mais unico possível
        ```
