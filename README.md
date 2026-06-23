# WhatsApp SaaS Docker Stack 🐳📱

Esta é a stack definitiva de alta performance para quem quer rodar a **Evolution API** em produção de forma profissional.
Não rode APIs de WhatsApp localmente ou em PM2 se quiser escala. Use esta arquitetura.

## 🏗️ O que vem nesta Arquitetura?

1. **PostgreSQL**: Banco de dados robusto. (A Evolution não é confiável apenas com arquivos SQLite para muitas instâncias).
2. **Redis**: Para gerenciar os Webhooks na fila e fazer cache de estados, impedindo que a API trave com picos de mensagens.
3. **Evolution API**: A versão mais recente configurada para consumir o Postgres e o Redis nativamente.

## 🚀 Como fazer Deploy na sua VPS

1. Instale o Docker e o Docker Compose no Ubuntu.
2. Clone este repositório e entre na pasta:
   ```bash
   git clone https://github.com/SEU_USUARIO/whatsapp-saas-docker-stack.git
   cd whatsapp-saas-docker-stack
   ```
3. Edite as variáveis no `docker-compose.yml` (Troque as senhas e a URL global!).
4. Suba o ambiente em background:
   ```bash
   docker-compose up -d
   ```
5. Acesse sua API na porta `:8080` (Recomendamos colocar atrás de um Nginx com SSL).

---
Se você usa Laravel, conecte o seu `ENV` do Laravel na mesma rede Docker ou aponte para a porta exposta deste container.
