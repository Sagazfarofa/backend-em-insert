# Evidências — Partes 1 e 2
## Identificação
Nome do aluno:
Turma:
Data:
---
## 1. Link do meu repositório GitHub
Cole abaixo o link do seu repositório:
https://github.com/SEU_USUARIO/backend-em-insert
---
# Parte 1 — Clonagem, configuração e publicação
## 2. Comprovação do remote configurado
Execute no terminal:
git remote -v
Cole abaixo o resultado:
cole aqui o resultado do comando
---
## 3. Comprovação dos commits
Execute no terminal:
git log --oneline
Cole abaixo o resultado:
cole aqui o resultado do comando

Projeto Back-end — Trilha backend-em-insert

Material do aluno

O resultado deve mostrar commits como:
Configura projeto insert
Atualiza rota raiz com pesquisa por data
---
## 4. Comprovação do status do projeto
Execute no terminal:
git status
Cole abaixo o resultado:
cole aqui o resultado do comando
---
## 5. Comprovação da execução do projeto
Execute no terminal:
npm run dev
Cole abaixo a mensagem exibida no terminal:
cole aqui o resultado do terminal
---
## 6. Teste da rota de todas as leituras
Acesse no navegador:
http://localhost:3000/api/leituras
Cole abaixo parte do resultado exibido:
cole aqui parte do resultado da rota /api/leituras
---
# Parte 2 — Alteração da rota raiz e pesquisa por data
## 7. Comprovação da rota raiz alterada
Acesse no navegador:
http://localhost:3000/
Cole abaixo o resultado exibido:
cole aqui o resultado da rota /
O resultado deve mostrar as rotas disponíveis, incluindo:
GET /api/leituras
GET /api/leituras/data/2026-04-01
---
## 8. Teste da rota de pesquisa por data

Projeto Back-end — Trilha backend-em-insert

Material do aluno

Acesse no navegador:
http://localhost:3000/api/leituras/data/2026-04-01
Cole abaixo parte do resultado exibido:
cole aqui parte do resultado da rota /api/leituras/data/2026-04-01
---
## 9. Teste de data inválida
Acesse no navegador:
http://localhost:3000/api/leituras/data/01-04-2026
Cole abaixo o resultado exibido:
cole aqui o resultado da validação de data inválida
---
## 10. Código alterado na rota raiz
Cole abaixo o trecho da rota raiz alterada no arquivo src/server.js:
cole aqui o código da rota app.get('/')
---
## 11. Observação final
Consegui clonar, configurar, executar, testar, alterar a rota raiz, testar a pesquisa por data e
publicar o projeto no meu GitHub.