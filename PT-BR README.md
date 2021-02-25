# apex-specialist
Abstração e resolução da superbadge Apex Specialist - TrailHead
È necessário que você deixe sua Org de Desenvolvimento / Playground em inglês para melhor entendimento.
Caso não saiba como fazer isso, aqui está o tutorial abaixo


1 [PT-BR] - Crie uma nova Org Prática em seu Trailhead para a resolução e validação dessa superbadge, isso evitara problemas de conflitos com outros exercicios. Você precisará instalar o package disponível no passo 2 para todos os usuários em sua org.</br>
2 [PT-BR] - Instale o novo package (package ID: 04t6g000008av9iAAA). Esse package contem os metadadados e configurações básicas para a conclusão desse desafio. Se você encontrar algum problema ou não souber como instalar, procure no Trailhead como instalar um Package ou App no Trailhead.</br>
3 [PT-BR] - Após concluir os passos 1 e 2, você precisará adicionar adicionar mais 2 valores no Objeto 'Case', que serão 'Repair' e 'Routine Maintenace'</br>
4 [PT-BR] - Após adicionar os valores de picklist no objeto 'Case', você precisará atualizar o layout para o seu profile/as pessoas que teriam acesso a este layout.</br>
5 [PT-BR] Renomeie o nome da Aba/Nome do Objeto Case para 'Maintenace Request'.</br>
6 [PT-BR] Faça o update do layout da pagina 'Product' para Product(HowWeRoll) para o seu profile/as pessoas que teriam acesso a este layout</br>
7 [PT-BR] Remomeie a Aba/Nome do objeto de 'Product' para 'Equipment'</br>
8 [PT-BR] Agora use o App Launcher para navegar até 'Create Default Data'. E clique em 'Create Data', para gerar os dados necessários para continuarmos este modulo.</br>

## Casos de Uso. PT-BR

Existem dois tipos de pessoas neste mundo: aquelas que viajam em um veículo alugado/recreativo (RV) e aquelas que não fazem este tipo de coisa. A comunidade de veículos recreativos estáa aumentando exponencialmente em todo o mundo. Nos ultimos anos, a HowWeRoll Rentals, a maior empresa de aluguel de veículos recretivos do mundo, aumentou sua presença global e sua frota de trailers em dez vezes. HowWeRoll oferece aos viajantes aluguel de veículos recreativos de qualidade superior e serviços de assistência rodoviária. Seu slogam é: "Temos um ótimo serviço, por que é assim que fazemos!" Sua frota de aluguel inclui todos os estilos de veículos de campo, desde trailersque parecem mansões luxuosas até um simples trailer para pescar.

Você foi contratado como desenvolvedor líder Salesforce, para automatizar e dimensionar o alcance do HowWeRoll. Par aos viajantes, nem todas as viagens acontecem de acordo com o planejado. Infelizmente, é provavel que haja um buraco na estrada em algum ponto ao longo do caminho e caso o veículo sofra algum problema precisamos estar de prontidão. Felizmente, HowWeRoll tem uma equipe incrível de reparos para os veículos que pode atender a qualquer solicitação de manutenção, não importa como for e onde esteja. Esses reparos abordam uma variedade de dificuldades técnicas mas para HowWeRoll isso não é um problema.

Conforme a empresa cresce, também cresce a frota de alguel. Embora seja ótimo para os negócios, o processo atual do serviço e manutenção é desafiador para escalar. Alem das solicitações de serviço para equipamentos quebrados ou com defeito, as solicitações de manutenção de rotina tem crescido exponencialmente. Necessitamos dessas manutenções pois sem isso a frota ficara vunerável e sucetíveis a problemas terríveis os quais podem ser evitados.

È agora que aparece sua oportunidade de brilhar! HowWeRoll precisa que você automatize o seu sistema de manuteção de rotina baseado em Salesforce. Você deverá garantir que qualquer coisa que possa causar danos desnecessários ao veículo, ou pior, colocar o cliente em perigo, seja sinalizada. Você também integrará o Salesforce com o sistema de back-office da HowWeRoll, que mantém o controle do estoque do armazém. Este sistema completamente separado precisa ser sincronizado regularmente com o Salesforce. A sincronização garante que a sede da HowWeRoll(Matriz) saiba exatamente quanto equipamentoe estará disponivel ao fazer uma solicitação de manutenção e os alertas quando precisam soliciar mais equipamentos.

Objetos Padrão
Você trabalhará com os seguintes objetos padrão:

Maintenance Request (foi renomeado 'Case') - solicitações de serviço para veículos quebrados, avarias e manutenção de rotina.
Equipamento (renomeado Produto) - Peças e itens no depósito usados para consertar ou manter RVs.

Objetos Personalizados
Vehicle - Veículos da frota de aluguel da HowWeRoll.
Equipment Maintenance Item - une um registro de equipamento a um registro de solicitação de manutenção, indicando o equipamento necessário para a solicitação de manutenção.


Entity Diagram -- img

Requisitos de negócio
Esta seção representa o ponto culminante de suas reuniões com as principais partes interessadas do HowWeRoll. É o seu plano automatizar programaticamente o suporte e a manutenção de seus negócios.


Automatizar solicitações de manutenção
Com o aumento exponencial na popularidade de veiculos recreativos em todo o mundo, a HowWeRoll está fornecendo mais centenas de veículos de luxo e econômicos. Junto comm esse aumento em seu estoque de aluguel, vem um aumento inevitável de falhas de equipamentos. HowWeRoll tem um processo existente para lidar com essas falhas, mas eles querem que você contrua uma automação para sua manutenção de rotina. Você criará um processo programático que programa automaticamente verificações regulares no equipamento com base na data em que o equipamento foi instalado

Quando uma solicitação de manutenção existente do tipo Reparo ou Manutenção de Rotina for fechada, crie uma nova solicitação de manutenção para uma futura verificação de rotina. Essa nova solicitação de manutenção está vinculada aos mesmos Registros de Veículos e Equipamentos da solicitação original fechada. Este novo tipo de solicitação deve ser definido como Manutenção de Rotina. O Assunto não deve ser nulo e o campo Data do Relatório reflete o dia em que a solicitação foi criada. Lembre-se de que todo equipamento possui ciclos de manutenção. Portanto, calcule as datas de vencimento da solicitação de manutenção usando o ciclo de manutenção definido nos registros de equipamentos relacionados. Se vários equipamentos forem usados ​​na solicitação de manutenção, defina a data de vencimento aplicando o ciclo de manutenção mais curto para a data de hoje.

Projete este processo automatizado para funcionar tanto para solicitações de manutenção individuais quanto em massa. Aumente o sistema para processar com êxito aproximadamente 300 registros de solicitações de manutenção offline que estão programadas para serem importadas juntas. Por enquanto, não se preocupe com as mudanças que ocorrem no próprio registro do equipamento.

Exponha também a lógica para outros usos na organização. Separe a trigger (denominado MaintenanceRequest) da lógica do aplicativo no manipulador (denominado MaintenanceRequestHelper). Essa configuração torna mais simples delegar ações e estender o aplicativo no futuro.

Sincronizar gerenciamento de estoque
Além da manutenção do equipamento, automatize a sincronização dos dados de inventário do HowWeRoll com o sistema externo no armazém do equipamento. Embora todo o escritório central use o Salesforce, a equipe do warehouse ainda trabalha em um sistema legado separado. Com essa integração, o estoque no Salesforce é atualizado depois que o equipamento é retirado do depósito para atender um veículo.

Escreva uma classe que faça um callout REST para um sistema de warehouse externo para obter uma lista de equipamentos que precisam ser atualizados. A resposta JSON da chamada retorna os registros de equipamento que você transferiu no Salesforce. Além do estoque, certifique-se de que outras mudanças potenciais no armazém sejam transferidas para o Salesforce. Sua classe mapeia os seguintes campos: peça de reposição (sempre verdadeiro), custo, estoque atual, vida útil, ciclo de manutenção e SKU do armazém. Use o SKU do warehouse como o ID externo para identificar quais registros de equipamento atualizar no Salesforce.

Embora a HowWeRoll seja uma empresa internacional, os escritórios remotos seguem o cronograma de trabalho do HQ. Portanto, todas as solicitações de manutenção são processadas durante o horário comercial normal do HQ. Você precisa atualizar os dados do Salesforce fora do horário comercial (às 1:00). Essa lógica é executada diariamente para que o inventário seja atualizado todas as manhãs na sede.

Criar testes de unidade
Teste seu código para garantir que ele seja executado corretamente antes de implantá-lo na produção.

Primeiro, teste o acionador para garantir que funciona conforme o esperado. Siga as práticas recomendadas testando casos de uso positivos (quando o gatilho precisa ser acionado) e casos de uso negativos (quando o gatilho não deve ser acionado). Claro, passar em um teste não significa necessariamente que você acertou tudo. Portanto, adicione asserções em seu código para garantir que você não obtenha falsos positivos. Para o seu teste positivo, afirme que tudo foi criado corretamente, incluindo as relações com o veículo e equipamento, bem como a data de vencimento. Para seu teste negativo, afirme que nenhuma ordem de serviço foi criada.

Conforme mencionado anteriormente, a enorme onda de solicitações de manutenção pode ser carregada de uma vez. O número provavelmente será em torno de 200, mas para contabilizar os picos potenciais, preencha sua classe para lidar com pelo menos 300 registros. Para testar isso, inclua um caso de uso positivo para 300 solicitações de manutenção e certifique-se de que seu teste foi executado conforme o esperado.

Quando você tiver 100% de cobertura de código em seu gatilho e manipulador, escreva casos de teste para sua chamada e classes Apex agendadas. Você precisa ter 100% de cobertura de código para todos os Apex em sua organização.

Certifique-se de que seu código opere conforme o esperado no contexto agendado, validando que ele é executado após Test.stopTest () sem exceção. Afirme também que um trabalho assíncrono agendado está na fila. As aulas de teste para o serviço de callout e teste agendado também devem ter 100% de cobertura de teste.
