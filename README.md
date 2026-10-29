# Trabalho 1 — Changelog e Release com GitHub Actions

**Aluno:** Thiago Duarte

---

## 1. Descrição do projeto

Este projeto demonstra a utilização do **GitHub Actions** para automatizar duas tarefas importantes no desenvolvimento de software: o registro das alterações realizadas no código e a publicação de versões do projeto.

Foram desenvolvidos dois workflows independentes:

- **Changelog:** atualiza automaticamente o histórico de alterações.
- **Release:** gera um pacote ZIP e publica uma nova versão na seção Releases do GitHub.

## 2. Tecnologias utilizadas

| Tecnologia | Finalidade |
|---|---|
| Git | Controle de versão do projeto. |
| GitHub | Hospedagem do repositório e gerenciamento das versões. |
| GitHub Actions | Execução automatizada dos workflows. |
| YAML | Definição e configuração das automações. |
| ZIP | Formato do pacote disponibilizado nas Releases. |

## 3. Action de Changelog

O workflow de Changelog automatiza o registro das alterações realizadas no projeto com base nas mensagens dos commits.

Quando executado, reúne os últimos commits e utiliza suas mensagens e identificadores para gerar ou atualizar o arquivo `CHANGELOG.md`, mantendo um histórico organizado do desenvolvimento.

### Detalhamento das etapas

**Gerar CHANGELOG**

Essa etapa utiliza o comando `git log -20` para consultar os últimos 20 commits do repositório, recuperando suas mensagens e identificadores abreviados. Os comandos `echo` organizam essas informações, adicionando o título e a estrutura do arquivo. Por fim, o operador `>` direciona o conteúdo gerado para o `CHANGELOG.md`, atualizando seu registro de alterações.

**Salvar alterações**

Com o arquivo gerado, essa etapa utiliza `git config` para configurar a identificação do GitHub Actions e `git add` para preparar o `CHANGELOG.md` para ser registrado. Em seguida, `git diff --cached --quiet` verifica se existem alterações pendentes. Caso existam, `git commit` cria um novo registro no histórico e `git push` envia as atualizações ao GitHub.

**Fluxo entre as etapas**

Primeiro, o workflow consulta os commits e gera o arquivo com o histórico atualizado. Depois, a etapa seguinte verifica se o conteúdo mudou e, caso necessário, registra e publica a atualização no repositório. Assim, as duas etapas trabalham em sequência para manter o changelog atualizado automaticamente.

## 4. Action de Release

O workflow de Release é responsável por empacotar os arquivos do projeto em um arquivo ZIP e publicar uma nova versão na seção Releases do GitHub.

A automação é acionada por tags que seguem o padrão `v*`, como `v1.0.0`.

### Etapas do processo

1. Identificar a versão marcada no repositório.
2. Gerar o pacote `release-package.zip` com os arquivos do projeto.
3. Criar a Release correspondente no GitHub.
4. Disponibilizar o arquivo ZIP para download na versão publicada.

Esse processo facilita a distribuição do projeto e permite consultar suas versões diretamente pelo GitHub.

## 5. Como utilizar as automações

### Changelog

1. Realizar alterações nos arquivos do projeto.
2. Criar commits com mensagens que descrevam as modificações.
3. Enviar as alterações para o GitHub.
4. Consultar o arquivo `CHANGELOG.md` para verificar o histórico atualizado.

### Release

1. Criar e enviar uma tag de versão seguindo o padrão `v*`, como `v1.0.0`.
2. Aguardar a execução do workflow na aba **Actions**.
3. Acessar a seção **Releases** do repositório.
4. Baixar o arquivo `release-package.zip` disponibilizado na versão publicada.

## 6. Testes e validação

Os workflows foram executados e testados no GitHub Actions. As configurações foram ajustadas até que as execuções apresentassem resultado de sucesso.

Também foi confirmada a publicação da Release no repositório.

Os resultados podem ser consultados nas abas **Actions** e **Releases** do GitHub.

## 7. Considerações finais

O projeto demonstra como o GitHub Actions pode simplificar e automatizar tarefas importantes do desenvolvimento de software.

A Action de Changelog facilita a documentação das alterações realizadas, enquanto a Action de Release permite gerar e disponibilizar pacotes de versões de maneira organizada e automatizada.

---

**Desenvolvido por Thiago Duarte**
