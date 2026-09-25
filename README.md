# Painel Contábil Ótica & RF

Site estático de consulta com os relatórios contábeis mensais (Simples Nacional) de duas empresas: **Ótica Vem Pra Cá** e **RF Consultoria**. Traz visão geral, DRE, balancete, apuração estimada do DAS e movimento agrupado por conta contábil.

- É um arquivo só (`index.html`), sem build e sem dependências para instalar.
- **Os dados ficam criptografados** (AES-GCM, chave derivada da senha por PBKDF2-SHA256 com 250.000 iterações). O que está no repositório é apenas texto cifrado. Sem a senha, o site mostra só a tela de acesso.
- Não há nomes de pessoas físicas: os lançamentos vão agrupados por conta contábil.
- Os valores vêm dos extratos bancários, em regime de caixa. O DAS é estimativa; o valor oficial é o do PGDAS-D.

## Publicação

Deploy no Vercel como projeto estático (Framework Preset: **Other**, sem comando de build, diretório de saída `.`).

## Atualização

A cada fechamento mensal, o `index.html` é regerado a partir do painel de trabalho e substituído aqui. O Vercel publica sozinho a cada commit.

A pasta `_local/` (senha e scripts de montagem) **não** vai para o repositório.
