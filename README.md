# Veridt

Trabalho solicitado pelo professor Eduardo Santana de Almeida, como requisito avaliativo do componente curricular Engenharia de Software I (MATA62).

- **Instituição:** Universidade Federal da Bahia (UFBA), Instituto de Computação
- **Disciplina:** Engenharia de Software I (MATA62)
- **Semestre:** 2026.2
- **Professor:** Eduardo Santana de Almeida
- **Discentes:** Dante Teles Ferreira, Guilherme Souza d'Afonseca, Henrique Ceita Adaes, Iury Silva de Sena

## Sobre o sistema

O Veridt é uma plataforma web para captura e gravação de conteúdo de páginas da internet, com o objetivo de produzir evidências digitais rastreáveis e verificáveis. O sistema é voltado para advogados e usuários comuns, que podem registrar capturas de tela ou vídeos de navegação de um site, consultar os registros realizados, gerar relatórios e exportar os arquivos capturados em formato ZIP.

As capturas consomem créditos, adquiridos em pacotes (básico, médio e premium) com pagamento pelo Mercado Pago ou via Pix. O usuário é notificado por e-mail sobre a confirmação das compras e a conclusão dos registros.

Os requisitos completos estão no [documento de requisitos](docs/referencias/veridit-req.pdf).

## O que foi feito

Este repositório reúne a entrega do **Trabalho II**, que consiste na definição da arquitetura do Veridt a partir do documento de requisitos. O enunciado está em [docs/referencias/trabalhoII.pdf](docs/referencias/trabalhoII.pdf). Foram produzidos:

- A lista de características arquiteturais do sistema, com a justificativa de cada uma.
- A seleção das 4 principais características arquiteturais, justificada via ADR.
- A lista de componentes candidatos, com suas responsabilidades.
- O diagrama de componentes, com a especificação interna de 30% dos componentes mais críticos.
- A escolha do estilo arquitetural (monólito modular), justificada via ADR.
- O diagrama de módulos da arquitetura (diagrama de pacotes UML).
- As táticas utilizadas para cada característica arquitetural.
- O conjunto de decisões arquiteturais (ADRs).
- O conjunto de telas da aplicação e os diagramas no Figma.

## Estrutura do repositório

```
.
├── README.md
├── assets/
│   ├── Veridt.fig
│   ├── diagrama-componentes-candidatos.png
│   └── diagrama-componentes-30porcento.png
└── docs/
    ├── adrs/
    │   ├── ADR-0001.md
    │   ├── ADR-0002.md
    │   ├── ADR-0003.md
    │   └── modelo.md
    ├── referencias/
    │   ├── trabalhoII.pdf
    │   └── veridit-req.pdf
    ├── caracteristicas-arquiteturais.md
    ├── componentes.md
    ├── diagrama-pacotes.puml
    └── taticas.md
```

### Documentação

| Arquivo | Descrição |
|---|---|
| [docs/caracteristicas-arquiteturais.md](docs/caracteristicas-arquiteturais.md) | Lista das características arquiteturais do sistema (segurança, disponibilidade, interoperabilidade, recuperabilidade, rastreabilidade, auditabilidade e confiabilidade) e a justificativa de cada uma. |
| [docs/componentes.md](docs/componentes.md) | Componentes candidatos e suas responsabilidades, o diagrama de componentes e a especificação interna de 30% dos componentes (PaymentService, CaptureService e RecordsService). |
| [docs/taticas.md](docs/taticas.md) | Táticas arquiteturais adotadas para cada característica e o objetivo de cada uma. |
| [docs/diagrama-pacotes.puml](docs/diagrama-pacotes.puml) | Diagrama de pacotes UML em PlantUML, com os módulos do sistema e as dependências entre eles. |

### Decisões arquiteturais (ADRs)

| Arquivo | Descrição |
|---|---|
| [docs/adrs/ADR-0001.md](docs/adrs/ADR-0001.md) | Escolha do estilo arquitetural: monólito modular. |
| [docs/adrs/ADR-0002.md](docs/adrs/ADR-0002.md) | Top 4 características arquiteturais. |
| [docs/adrs/ADR-0003.md](docs/adrs/ADR-0003.md) | Particionamento por domínio. |
| [docs/adrs/modelo.md](docs/adrs/modelo.md) | Modelo padronizado usado na escrita das ADRs (contexto, decisão, alternativas consideradas, justificativa, consequências e referência). |

### Referências

| Arquivo | Descrição |
|---|---|
| [docs/referencias/veridit-req.pdf](docs/referencias/veridit-req.pdf) | Documento de requisitos do Veridt (REQ-01 a REQ-15, decisões D1 e D2 e Apêndice A). |
| [docs/referencias/trabalhoII.pdf](docs/referencias/trabalhoII.pdf) | Enunciado do Trabalho II da disciplina. |

### Assets

| Arquivo | Descrição |
|---|---|
| [assets/diagrama-componentes-candidatos.png](assets/diagrama-componentes-candidatos.png) | Diagrama com os sete componentes candidatos e suas dependências. |
| [assets/diagrama-componentes-30porcento.png](assets/diagrama-componentes-30porcento.png) | Especificação interna dos componentes mais críticos. |
| [assets/Veridt.fig](assets/Veridt.fig) | Arquivo do Figma com as telas da aplicação e os diagramas. |

## Figma

As telas da aplicação e os diagramas estão disponíveis no [Figma do Veridt](https://www.figma.com/design/D4vDhuk1DBAJY9knexl7Hs/Veridt?node-id=0-1&t=YgLGf4RsxAjWx53e-1).
