# Registro de Alterações

Todas as mudanças notáveis de benchmark, dados e visualizador são registradas neste arquivo.

## [2.0.1] - 2026-03-04

### Adicionado
- Adicionadas execuções de benchmark para `openai/gpt-5.3-chat` e `google/gemini-3.1-flash-lite-preview`.

### Alterado
- Definida data de lançamento de metadados para ambos modelos como `2026-03-04` e sincronizada em:
  - `data/model_metadata/model_launch_dates.csv`
  - `data/latest/model_launch_dates.csv`
  - `data/v2/latest/model_launch_dates.csv`
- Atualizado `data/latest/leaderboard_with_launch.csv` e `data/v2/latest/leaderboard_with_launch.csv` para mostrar a nova data de lançamento e idade do modelo (`0`) para ambos modelos.
- Atualizado [viewer/index.v2.html](viewer/index.v2.html) para carregar metadados de lançamento mesclando linhas embutidas com linhas CSV e buscar metadados com `cache: "no-store"` para que as novas datas de modelo apareçam de forma confiável em todos os gráficos de lançamento.

## [2.0.0] - 2026-03-01

### Destaques
- Adicionadas `100` novas perguntas absurdas v2.
- Adicionada cobertura por domínio em `5` domínios: `software` (40), `finanças` (15), `jurídico` (15), `medicina` (15), `física` (15).
- Adicionadas novas visualizações v2 (distribuição de detecção por modelo, panorama por domínio, tendências ao longo do tempo, dispersão por data de lançamento e dispersão de tokens/custo de raciocínio).

### Adicionado
- Novo conjunto de perguntas v2 em [questions.v2.json](questions.v2.json) com 100 prompts em 5 grupos de domínio e 13 técnicas.
- Nova configuração v2 em [config.v2.json](config.v2.json) com padrões de coleta de alto rendimento e conjunto de técnicas atualizado.
- Página dedicada do visualizador v2 em [viewer/index.v2.html](viewer/index.v2.html).
- Dataset v2 publicado dedicado em `data/v2/latest/*`.
- Script de construção de perguntas [scripts/build_questions_v2_from_draft.py](scripts/build_questions_v2_from_draft.py).

### Alterado
- Visualizador e documentação agora suportam versionamento lado a lado (`v1` e `v2`) sem sobrescrever dados antigos.
- Pipeline/documentação atualizada para publicação explícita v2 via `--config config.v2.json --viewer-output-dir data/v2/latest`.
- Pipeline de publicação agora limpa fragmentos de caminhos de máquina local de artefatos JSONL publicados.
- Política canônica do painel agora é fixa em exatamente três juízes (`panel_mode=full`) com agregação `mean` no pipeline principal.
- Categorização do visualizador agora usa `status` + `consensus_score` publicados como padrões canônicos (quando todos os juízes são selecionados), enquanto ainda permite visualizações exploratórias de subconjunto de juízes.
- Análise de CSV do `viewer/index.v2.html` agora reconhece aspas para metadados de lançamento e futuras extensões CSV.
- `viewer/index.v2.html` agora inclui rótulos amigáveis para chaves de técnica legadas v1.

### Removido / Limpo
- Removidos rascunhos obsoletos `v2_old` e artefatos de histórico de execução local.
- Removidos arquivos temporários/de depuração locais antes da publicação.

## [1.0.0] - 2026-02-25

### Adicionado
- Lançamento público inicial do benchmark (dataset v1 + visualizador).
