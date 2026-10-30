# Características Arquiteturais

Lista de características arquiteturais para o sistema, juntamente com a justificativa para a escolha.

## 1. Segurança

O Veridt exige autenticação e autorização de usuários (REQ-03), de modo que somente usuários cadastrados acessem o conteúdo correspondente. Além disso, o sistema trata dados pessoais (REQ-01), como o CPF, número da OAB e endereço, estando sujeitos à LGPD, além do processamento de pagamentos (REQ-05 e REQ-06). Dessa forma, esses pontos exigem que o sistema tenha proteção contra invasões, vazamentos, fraudes e adulteração dos registros obtidos, uma vez que esses registros são a própria evidência que será utilizada pelo usuário.

## 2. Disponibilidade

A disponibilidade do sistema é outro ponto relevante, pois se o usuário precisa fazer alguma captura (REQ-08, REQ-09 e REQ-11), mas o sistema está indisponível, o usuário perde a oportunidade de realizar aquela captura. O mesmo ocorre se o sistema cair durante uma gravação ou captura, deixando o registro incompleto, ou se a compra de créditos (REQ-05 e REQ-06) estiver fora do ar.

## 3. Interoperabilidade

Como o sistema envia e-mails para confirmar a compra de créditos (REQ-07) e a conclusão da gravação ou captura de conteúdo (REQ-10 e REQ-11), além de oferecer o pagamento pelo Mercado Pago (REQ-06), é necessária a integração com esses serviços externos. Por isso, é fundamental que o sistema tenha a capacidade de lidar com eventuais falhas de comunicação com esses serviços, a fim de evitar, por exemplo, que um pagamento aprovado não resulte nos créditos para o usuário.

## 4. Recuperabilidade

Se o sistema ficar indisponível durante uma gravação ou captura de conteúdo (REQ-08, REQ-09 e REQ-11), ele deve ser capaz de retornar, preservando o que já foi registrado, permitindo que o usuário acesse o registro feito até a interrupção. Enquanto a disponibilidade busca reduzir a ocorrência dessas quedas, a recuperabilidade permite que, quando elas ocorrerem, o usuário não perca toda a evidência já capturada.

## 5. Rastreabilidade

A rastreabilidade é fundamental para o Veridt, pois permite identificar a origem e o histórico de cada evidência registrada (REQ-08, REQ-09 e REQ-11). O sistema deve manter informações sobre quem realizou uma captura, quando ela ocorreu, qual conteúdo foi registrado e quais operações foram realizadas posteriormente. Essas informações também são necessárias para a apresentação dos detalhes e relatórios (REQ-13 e REQ-14), permitindo relacionar cada arquivo ao seu respectivo registro.

## 6. Auditabilidade

Além de registrar o histórico das operações, o sistema deve permitir que a integridade das evidências e a consistência das informações apresentadas sejam verificadas. A auditabilidade possibilita examinar os arquivos, metadados e eventos associados a um registro, identificando eventuais alterações ou inconsistências (REQ-13, REQ-14 e REQ-15). Diferentemente da rastreabilidade, que permite reconstruir o histórico das operações, a auditabilidade busca fornecer meios para verificar a confiabilidade desse histórico e das evidências armazenadas. Para isso, são necessários mecanismos de verificação de integridade e proteção dos registros de auditoria contra alterações indevidas.

## 7. Confiabilidade

A confiabilidade consiste no sistema consistentemente produzir os resultados corretos, não perdendo ou corrompendo informações. Se, por exemplo, os relatórios gerados a partir da evidência (REQ-14 e REQ-15) diferem do que foi capturado/gravado (REQ-09 e REQ-11), a evidência pode perder o valor, causando prejuízo ao usuário e reduzindo a confiança na plataforma.

Para alcançar essa característica, devem ser consideradas tanto medidas de prevenção de falhas quanto mecanismos de tolerância a falhas. Enquanto as primeiras buscam reduzir a ocorrência de erros, as últimas procuram limitar suas consequências quando eles inevitavelmente ocorrerem. Portanto, essas abordagens são complementares, pois um sistema confiável não deve apenas evitar falhas, mas também preservar a consistência das operações diante de situações inesperadas.
