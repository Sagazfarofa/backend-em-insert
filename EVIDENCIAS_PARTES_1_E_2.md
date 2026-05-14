# Evidências — Partes 1 e 2
## Identificação
Nome do aluno: Luiz Gustavo Almeida Rosa
Turma: 3° A
Data: 14/05/2026
---
## 1. Link do meu repositório GitHub
Cole abaixo o link do seu repositório:
https://github.com/Sagazfarofa/backend-em-insert
---
# Parte 1 — Clonagem, configuração e publicação
## 2. Comprovação do remote configurado
Execute no terminal:
git remote -v
Cole abaixo o resultado:
origin  https://github.com/Sagazfarofa/backend-em-insert.git (fetch)
origin  https://github.com/Sagazfarofa/backend-em-insert.git (push)
cole aqui o resultado do comando
---
## 3. Comprovação dos commits
Execute no terminal:
git log --oneline
Cole abaixo o resultado:
56398ac (HEAD -> main, origin/main) Adiciona evidencias das partes 1 e 2
b97af41 Atualiza rota raiz com pesquisa por data
8b29fdb Configura projeto insert
4ffe899 Rename project section from 'Parte 2' to 'Insert'
ea330b7 Inserção de 3 registros de leituras
dba6585 Filtra Leituras por data
ba38040 Update DB_PASSWORD in .env-exemplo
3a9d2b0 Commit inicial
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
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   EVIDENCIAS_PARTES_1_E_2.md

cole aqui o resultado do comando
---
## 5. Comprovação da execução do projeto
Execute no terminal:
npm run dev
Cole abaixo a mensagem exibida no terminal:
Banco db_em já existe.
Conexão com PostgreSQL realizada com sucesso.
Tabela sincronizada com sucesso.
Tabela leituras já possui dados.
Servidor rodando em http://localhost:3000
cole aqui o resultado do terminal
---
## 6. Teste da rota de todas as leituras
Acesse no navegador:
http://localhost:3000/api/leituras
Cole abaixo parte do resultado exibido:
[
  {
    "id": 1,
    "station_id": "EM-ARACATUBA-01",
    "timestamp": "2026-04-01T11:00:00.000Z",
    "temperature_c": 24.5,
    "humidity_pct": 72.1
  },
  {
    "id": 2,
    "station_id": "EM-ARACATUBA-01",
    "timestamp": "2026-04-01T12:00:00.000Z",
    "temperature_c": 25.8,
    "humidity_pct": 69.4
  },
  {
    "id": 3,
    "station_id": "EM-ARACATUBA-01",
    "timestamp": "2026-04-01T13:00:00.000Z",
    "temperature_c": 27.2,
    "humidity_pct": 65.8
  },
  {
    "id": 4,
    "station_id": "EM-ARACATUBA-01",
    "timestamp": "2026-04-02T11:00:00.000Z",
    "temperature_c": 23.9,
    "humidity_pct": 74.3
  },
  {
    "id": 5,
    "station_id": "EM-ARACATUBA-01",
    "timestamp": "2026-04-02T12:00:00.000Z",
    "temperature_c": 25.1,
    "humidity_pct": 70.6
  },
  {
    "id": 6,
    "station_id": "EM-ARACATUBA-01",
    "timestamp": "2026-04-02T13:00:00.000Z",
    "temperature_c": 26.7,
    "humidity_pct": 67.2
  }
]
cole aqui parte do resultado da rota /api/leituras
---
# Parte 2 — Alteração da rota raiz e pesquisa por data
## 7. Comprovação da rota raiz alterada
Acesse no navegador:
http://localhost:3000/
Cole abaixo o resultado exibido:
{"mensagem":"API Estação Meteorológica","descricao":"API para consulta de leituras meteorológicas armazenadas no PostgreSQL.","rotasDisponiveis":{"listarTodasAsLeituras":"GET /api/leituras","pesquisarLeiturasPorData":"GET /api/leituras/data/2026-04-01"},"formatoDaData":"YYYY-MM-DD","exemploDeUso":"http://localhost:3000/api/leituras/data/2026-04-01"}
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
Cole abaixo parte do resultado exibido:{
  "dataPesquisada": "2026-04-01",
  "total": 3,
  "leituras": [
    {
      "id": 1,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-01T11:00:00.000Z",
      "temperature_c": 24.5,
      "humidity_pct": 72.1
    },
    {
      "id": 2,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-01T12:00:00.000Z",
      "temperature_c": 25.8,
      "humidity_pct": 69.4
    },
    {
      "id": 3,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-01T13:00:00.000Z",
      "temperature_c": 27.2,
      "humidity_pct": 65.8
    }
  ]
}
cole aqui parte do resultado da rota /api/leituras/data/2026-04-01
---
## 9. Teste de data inválida
Acesse no navegador:
http://localhost:3000/api/leituras/data/01-04-2026
Cole abaixo o resultado exibido:
{
  "mensagem": "Formato de data inválido. Use o formato YYYY-MM-DD.",
  "exemplo": "2026-05-11"
}
cole aqui o resultado da validação de data inválida
---
## 10. Código alterado na rota raiz
Cole abaixo o trecho da rota raiz alterada no arquivo src/server.js:
pp.get('/', (req, res) => {
  return res.json({
    mensagem: 'API Estação Meteorológica',
    descricao: 'API para consulta de leituras meteorológicas armazenadas no PostgreSQL.',
    
    rotasDisponiveis: {
      listarTodasAsLeituras: 'GET /api/leituras',
      pesquisarLeiturasPorData: 'GET /api/leituras/data/2026-04-01'
    },

    formatoDaData: 'YYYY-MM-DD',

    exemploDeUso: 'http://localhost:3000/api/leituras/data/2026-04-01'
  });
});
cole aqui o código da rota app.get('/')

---
## 11. Observação final
Consegui clonar, configurar, executar, testar, alterar a rota raiz, testar a pesquisa por data e
publicar o projeto no meu GitHub.