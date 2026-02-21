# ONG Vida Plena

Banco de Dados Visual No-Code com Airtable

## Descricao do Projeto

ONG Vida Plena e uma solucao no-code desenvolvida para centralizar e organizar dados de beneficiarios e eventos de uma ONG que enfrentava dificuldades com planilhas dispersas e comunicacao descentralizada. O sistema utiliza o **Airtable** como banco de dados visual relacional, permitindo cadastro de beneficiarios, gestao de eventos, inscricoes e automacoes, tudo sem necessidade de programacao.

A solucao foi modelada com principios de banco de dados relacional adaptados para um ambiente visual, incluindo uma estrutura muitos-para-muitos implementada por meio de tabela associativa.

## Objetivo do Projeto

Este projeto foi desenvolvido para fins academicos na disciplina de **Banco de Dados Visual e Ferramentas Integradas** (UniFECAF + Rocketseat), com o objetivo de demonstrar como ferramentas no-code podem ser aplicadas para resolver problemas reais de organizacao de dados, com modelagem relacional, automacoes e boas praticas de seguranca da informacao.

## Funcionalidades Principais

- Cadastro de beneficiarios via formulario no-code
- Gestao de eventos com visualizacao em calendario
- Inscricao de beneficiarios em multiplos eventos
- Historico de participacao visivel e rastreavel
- Automacao de notificacao por e-mail apos nova inscricao
- Visualizacoes organizadas (Grid View e Calendar View)
- Campos lookup para acesso a dados relacionais

## Tecnologias Utilizadas

| Tecnologia | Finalidade |
|---|---|
| **Airtable** | Banco de dados visual e relacional |
| **Automations (Airtable)** | Automacao nativa de envio de e-mails |
| **Formularios visuais** | Cadastro e inscricao sem exposicao da base |

## Estrutura Relacional

O banco foi modelado com tres entidades principais e um relacionamento muitos-para-muitos:

```
Beneficiaries (Beneficiarios)
  - Nome, idade, telefone, regiao, e-mail

Events (Eventos)
  - Nome do evento, data, descricao

Registrations (Inscricoes)
  - Tabela associativa que vincula beneficiarios aos eventos
```

### Relacionamento

```
Beneficiaries  <──  N:M  ──>  Events
                    |
              Registrations
```

Um beneficiario pode participar de diversos eventos e cada evento pode ter multiplos participantes. A tabela **Registrations** implementa essa relacao, garantindo historico rastreavel e organizado sem redundancia de dados.

## Automacao

Quando uma nova inscricao e criada na tabela Registrations:

1. O sistema identifica o beneficiario vinculado
2. Busca o e-mail do beneficiario via campo lookup
3. Envia notificacao automatica por e-mail com o nome do evento

## Etica e Seguranca da Informacao

- Coleta minima de dados pessoais (principio de minimizacao)
- Uso de formularios para evitar exposicao direta da base
- Controle de acesso gerenciado pela plataforma
- Separacao entre cadastro e inscricao para reduzir inconsistencias
- Alinhamento com principios da LGPD (minimizacao, transparencia e responsabilidade)

## Validacao

O sistema foi testado com dados simulados, verificando:

- Inscricoes em multiplos eventos funcionando corretamente
- Historico de participacao visivel nas tabelas
- Automacao de envio de e-mail operando apos nova inscricao

## Potencial de Expansao

- Integracao com WhatsApp para notificacoes
- Dashboards analiticos para acompanhamento de metricas
- Integracoes com APIs externas
- Relatorios automatizados

## Estrutura do Repositorio

```
conteudo/
  parte-teorica.pdf    -> Documento teorico completo do projeto
  parte-teorica.docx   -> Versao editavel do documento teorico
  video-pitch.mkv      -> Video de apresentacao do projeto
```

## Autor

**Mauricio Valente Martins**

Projeto academico com foco em aplicacoes no-code para impacto social.
