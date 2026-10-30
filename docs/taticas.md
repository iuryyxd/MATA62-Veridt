# Táticas Arquiteturais

As táticas utilizadas para cada característica da arquitetura. Para cada tática, descrever o seu principal objetivo.

## Segurança

Para garantir a segurança do Veridt, serão utilizados mecanismos de autenticação e autorização, verificando a identidade dos usuários e restringindo o acesso aos registros de acordo com suas permissões (REQ-01, REQ-03, REQ-04, REQ-12 e REQ-13). As credenciais serão protegidas por algoritmos de hash apropriados para senhas, como Argon2id, evitando seu armazenamento em texto puro (REQ-01 e REQ-02). Além disso, as requisições recebidas de serviços externos, especialmente as notificações de pagamento, deverão ter sua autenticidade verificada, impedindo que solicitações fraudulentas sejam utilizadas para adicionar créditos indevidamente (REQ-05 e REQ-06).

## Disponibilidade

A disponibilidade será favorecida pelo isolamento de falhas entre os componentes, de modo que a indisponibilidade de um serviço secundário, como o envio de e-mails (REQ-07, REQ-10 e REQ-11), não impeça a execução das demais funcionalidades, especialmente as capturas de conteúdo (REQ-08, REQ-09 e REQ-11). Para lidar com falhas persistentes em integrações externas, poderá ser utilizado o padrão Circuit Breaker, que interrompe temporariamente novas tentativas de comunicação com serviços que estejam apresentando problemas, evitando o esgotamento de recursos.

Embora o estilo arquitetural escolhido seja o monólito modular, isso não impede que a aplicação seja executada em múltiplas instâncias, distribuídas entre servidores diferentes. Dessa forma, caso seja necessário aumentar a disponibilidade, poderá ser adotada a redundância de instâncias associada ao balanceamento de carga, reduzindo a dependência de um único servidor. Então, essa abordagem exige que recursos compartilhados, como sessões, arquivos e dados persistentes, sejam gerenciados adequadamente, evitando inconsistências entre as instâncias.

## Interoperabilidade

Para facilitar a comunicação entre os componentes e as plataformas externas, serão utilizadas interfaces bem definidas e formatos padronizados de troca de dados. As integrações com serviços de terceiros ficarão concentradas em componentes específicos, como PaymentService e NotificationService, responsáveis pelas funcionalidades de pagamento e envio de notificações (REQ-06, REQ-07, REQ-10 e REQ-11). Essa separação reduz o impacto de possíveis mudanças nas APIs utilizadas. Também será necessária a confirmação das operações externas antes da atualização dos dados internos, principalmente nas transações financeiras, evitando que créditos sejam disponibilizados antes da confirmação do pagamento (REQ-05 e REQ-06).

## Recuperabilidade

A recuperabilidade será tratada por meio do salvamento incremental das gravações, permitindo que o conteúdo seja armazenado em partes durante a captura, sem depender exclusivamente de sua finalização (REQ-08 e REQ-09). Dessa forma, caso ocorra uma interrupção, os trechos já armazenados poderão ser preservados. O sistema também deverá manter informações sobre o estado das operações, identificando quais registros foram concluídos e quais foram interrompidos (REQ-09, REQ-11 e REQ-12). Complementarmente, serão realizados backups dos arquivos e metadados, permitindo sua restauração em situações de falha ou perda de dados (REQ-12 a REQ-15).

## Rastreabilidade e Auditabilidade

A rastreabilidade será obtida pelo registro dos eventos relevantes do sistema, incluindo informações como usuário responsável, data, horário, operação realizada e resultado (REQ-12, REQ-13 e REQ-14). Cada captura também deverá possuir um identificador único, associado aos seus respectivos metadados, permitindo relacionar os arquivos e relatórios à operação que os originou, conforme previsto no Apêndice A do documento de requisitos. Para verificar a integridade dos arquivos capturados, poderão ser utilizados hashes criptográficos, como SHA-256, que permitem identificar alterações posteriores no conteúdo, desde que os valores originais de referência sejam preservados de maneira confiável.

Entretanto, o uso de hashes isoladamente não garante que a evidência corresponde ao conteúdo efetivamente disponibilizado pelo site no momento informado. Para fortalecer a auditabilidade, poderão ser considerados mecanismos complementares, como assinaturas digitais, proteção dos registros de auditoria e carimbos de tempo emitidos por uma autoridade confiável. Esses mecanismos contribuem para a verificação da integridade, da origem e do momento de registro das informações, embora não seja garantida, por si só, a veracidade do conteúdo apresentado pela página original.

## Confiabilidade

Para garantir a consistência das informações, serão utilizadas operações transacionais nos processos que envolvem alterações relacionadas, especialmente na atualização dos créditos dos usuários (REQ-05 e REQ-06). Também será aplicada a idempotência, evitando que o processamento repetido de uma mesma operação produza efeitos duplicados (como a adição de créditos duas vezes para um único pagamento). Além disso, tarefas secundárias, como o envio de notificações de compra e conclusão de registros (REQ-07, REQ-10 e REQ-11), poderão ser processadas de maneira assíncrona, permitindo que eventuais falhas nessas atividades não comprometam operações principais já concluídas (REQ-06, REQ-09 e REQ-11).
