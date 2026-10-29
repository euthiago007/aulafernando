Trabalho 1 — Changelog e Release com GitHub Actions

Aluno: Thiago Duarte

1. Descrição do projeto

Este projeto demonstra a utilização do GitHub Actions para automatizar duas tarefas importantes no desenvolvimento de software: o registro das alterações realizadas no código e a publicação de versões do projeto.

Foram criados dois workflows independentes: um responsável por atualizar o changelog com base nas mensagens dos commits e outro responsável por gerar um pacote ZIP e publicá-lo na seção Releases do GitHub.

2. Tecnologias utilizadas

- Git: controle de versão do projeto.
- GitHub: hospedagem do repositório e gerenciamento das versões.
- GitHub Actions: execução automatizada dos workflows.
- YAML: definição das configurações das automações.
- ZIP: formato do pacote disponibilizado nas Releases.

3. Action de Changelog

O workflow de Changelog automatiza o registro das alterações realizadas no projeto a partir das mensagens dos commits.

Quando executado, o workflow reúne as informações das alterações e atualiza o arquivo "CHANGELOG.md", mantendo um histórico documentado do desenvolvimento.

Essa automação facilita o acompanhamento das modificações realizadas ao longo do tempo, sem exigir que o histórico seja atualizado manualmente.

4. Action de Release

O workflow de Release é responsável por empacotar os arquivos do projeto em um arquivo ZIP e publicar uma nova versão na seção Releases do GitHub.

A automação é acionada por tags que seguem o padrão "v*", como "v1.0.0".

O processo inclui:

1. Identificar a versão marcada no repositório.
2. Gerar o pacote "release-package.zip" com os arquivos do projeto.
3. Criar a Release correspondente no GitHub.
4. Disponibilizar o arquivo ZIP como um dos recursos para download da versão publicada.

Esse processo facilita a distribuição do projeto e permite consultar as versões publicadas diretamente pelo GitHub.

5. Como utilizar as automações

Changelog

1. Realizar alterações nos arquivos do projeto.
2. Criar commits com mensagens que descrevam as modificações.
3. Enviar as alterações para o GitHub.
4. Consultar o arquivo "CHANGELOG.md" para verificar o histórico atualizado.

Release

1. Criar e enviar uma tag de versão seguindo o padrão "v*", como "v1.0.0".
2. Aguardar a execução do workflow na aba Actions.
3. Acessar a seção Releases do repositório.
4. Baixar o arquivo "release-package.zip" disponibilizado na versão publicada.

6. Testes e validação

Os workflows foram executados e testados no GitHub Actions. As execuções foram corrigidas até apresentarem resultado de sucesso, e a publicação da Release foi confirmada no repositório.

Os resultados podem ser consultados nas abas Actions e Releases do GitHub.

7. Considerações finais

O projeto demonstra como o GitHub Actions pode automatizar o registro de alterações e a publicação de versões de um projeto.

A Action de Changelog facilita a documentação do desenvolvimento, enquanto a Action de Release permite gerar e disponibilizar pacotes do projeto de forma organizada e automatizada.
