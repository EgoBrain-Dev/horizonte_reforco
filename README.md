# Reforço do Nível 0 (novo cenário)

## Cenário
A **MicroCrédito Horizonte** (fictícia, Matola) concede pequenos empréstimos. Quer um projecto
organizado para analisar os empréstimos. Há uma lista de **clientes confidencial**: nunca pode
chegar a um repositório partilhado, em nenhum caminho e em nenhum commit.

## Regras
- **Sem pistas minhas.** Permitido: `--help`, `man`, documentação oficial, o `teoria.md`
  e as tuas notas.
- O projecto chama-se **`horizonte_reforco`**, em `~/PycharmProjects/`, **fora** do
  `DataAnalysis`, com o seu próprio Git.
- Mensagens de commit em inglês simples: verbo no imperativo + ideia completa, sem gralhas.
- Antes de cada commit, confirma o que vai ser guardado.

## Dados (`data/raw/emprestimos.csv`, exactamente este conteúdo)
```
id,data,cliente_id,valor_mzn,estado
L001,2026-05-02,C01,15000,pago
L002,2026-05-03,C02,8000,em_atraso
L003,2026-05-05,C03,22000,pago
L004,2026-05-06,C01,5000,em_atraso
L005,2026-05-09,C02,12000,pago
L006,2026-05-10,C03,9000,em_atraso
```

## Tarefas
1. Cria `horizonte_reforco` com o uv, a usar **Python 3.12**, e abre-o no PyCharm
   (confirma o interpretador).
2. Dependências: **`tabulate`** (normal) e **`pytest`** (só desenvolvimento).
3. Estrutura: `src/`, `data/raw/`, `data/processed/`, `docs/`, `tests/`.
   O Git tem de guardar todas.
4. Protege o projecto: o Git tem de ignorar `.venv`, `.idea` e `data/confidencial/`.
   As regras têm de ficar guardadas **antes** de qualquer ficheiro de dados.
5. Cria `data/raw/emprestimos.csv` (conteúdo acima). Os dados em `raw` nunca se alteram.
6. Cria `data/confidencial/clientes.csv` com 3 clientes fictícios (cabeçalho
   `cliente_id,nome,telefone`). **Não pode ficar no Git nem no histórico, em nenhum caminho.**
7. Cria 2 ficheiros `.tmp` em `data/processed/` e limpa-os com segurança.
8. Numa branch `analise`, com **pelo menos 2 commits**, cria `docs/analise.md` e depois
   `docs/notas.md` (um título e uma frase tua em cada). Junta-a à `master` de forma a
   **ficar um commit de junção visível**.
9. **Pelo menos 7 commits** no total, pequenos e claros.
10. **Auditoria.** No fim, com comandos do Git (não de memória), escreve em
    `DataAnalysis/reforco_n0/auditoria.txt` (pelo terminal), uma linha por valor:
    `linhas_emprestimos=<linhas do CSV, cabeçalho incluído>`
    `emprestimos_em_atraso=<número>`
    `tabulate_versao=<versão que o uv instalou>`
    `ficheiros_seguidos=<número de ficheiros que o Git segue>`
    `commits=<número de commits na master>`
    `merge_visivel=<sim ou nao>`
11. **Erros em inglês.** Para cada um, diz em português o que significa e o que farias:
    - `Automatic merge failed; fix conflicts and then commit the result.`
    - `error: Your local changes to the following files would be overwritten by checkout`
12. **Documentação.** Na documentação oficial do Git (`git-scm.com/docs/git-merge`),
    encontra a opção `--no-ff` e explica numa frase, em português, o que faz.
13. A partir da raiz do `DataAnalysis`: `uv run reforco_n0/verificar.py`. Corrige uma falha
    de cada vez, faz commit dos ficheiros de `reforco_n0` (mensagem em inglês) e o push.

## Critérios de avaliação
- Resultado (estado do projecto e respostas): 50%
- Método (commits claros, ver antes de guardar, sem dados privados no histórico): 20%
- Explicação do raciocínio (tarefas 11 e 12 e as 3 respostas finais): 20%
- Autonomia (sem pedir pistas): 10%
- Aprovação: 70% no total e 60% em cada componente.

## O que colar no chat (tudo, à primeira)
1. `find ~/PycharmProjects/horizonte_reforco -not -path '*/.git/*' -not -path '*/.venv/*' | sort`
2. `cat ~/PycharmProjects/horizonte_reforco/pyproject.toml`
3. O que o PyCharm mostra em Python Interpreter
4. `git --no-pager log --oneline --graph --all`
5. `git --no-pager ls-files`
6. `git --no-pager log --all --name-only --pretty=format: | sort -u`
7. `git status --short`
8. O output de `uv run reforco_n0/verificar.py` e o `cat reforco_n0/auditoria.txt`
9. As tuas respostas das tarefas 11 e 12
10. `history | tail -200` de **cada janela do terminal** onde trabalhaste
11. Três respostas curtas, com as tuas palavras:
    (a) porque é que `git ls-files` sozinho não prova que o ficheiro confidencial nunca
    esteve no Git;
    (b) o que significa um merge não deixar commit de junção e porque o queremos visível;
    (c) escreve duas mensagens de commit em inglês: uma para guardar as regras de ignorar e
    outra para guardar o ficheiro de empréstimos.
