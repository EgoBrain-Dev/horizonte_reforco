# Teoria: Reforço do Nível 0 (glossário PT / EN)

**Tracked (seguido)**: ficheiro que o Git já regista. **Untracked (não seguido)**: o Git ainda
não o conhece. **Ignored (ignorado)**: o Git não o vê por causa do `.gitignore`.
Erro comum: achar que o `.gitignore` afecta ficheiros que já são seguidos. Não afecta.

**Staged (em staging)**: marcado para o próximo commit. Antes de cada commit:
`git status --short` (o que mudou) e `git diff --staged --stat` (o que vai ser guardado).
Erro comum: `git add pasta/` ou `git add .` guardam tudo o que lá estiver, incluindo ficheiros
que não pensavas.

**Audit (auditoria)**: verificar o que o Git segue **e o que alguma vez seguiu**.
- `git ls-files`: o que está seguido **agora**.
- `git log --all --name-only --pretty=format: | sort -u`: todos os caminhos que **alguma vez**
  entraram num commit, em qualquer branch.
Erro comum: verificar só o caminho onde esperavas o ficheiro. Uma cópia noutro caminho
passa despercebida.

**Leak (fuga de dados)**: dados privados que chegam a um sítio onde não deviam. Apagar o
ficheiro num commit novo não o remove dos commits antigos.

**Fast-forward (avanço rápido)**: um merge que só move o ponteiro da branch, sem criar
commit novo. O histórico fica recto e não se vê que houve uma branch.
**Merge commit (commit de junção)**: commit com dois pais, que regista a junção. Para o
forçar: `git merge --no-ff nome_da_branch`. Para o ver: `git log --graph --oneline --all`.

**Commit message (mensagem de commit)**: verbo no imperativo + ideia completa. Verbos:
*Add*, *Fix*, *Remove*, *Update*, *Rename*, *Move*.
Bom: `Add sample sales data`. Mau: `Add folder with all data of project` (vago),
`Add documentaction file` (gralha: *documentation*), mensagens com português a meio.
Uma ideia por commit.

**History (histórico dos comandos)**: `history | tail -200`. Cada janela do terminal tem o seu.
