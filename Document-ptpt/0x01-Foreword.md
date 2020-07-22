# Prefácio

Por Bernhard Mueller, OWASP Mobile Project

Revoluções tecnologicas pode acontecer muito rápido. À menos de uma decada atrás, smartphones eram dispositivos desajeitos com pequenos teclados - briquedos caros para utilizadores de empresas altamente tecnológicas. Hoje os smartphones são uma parte essencial das nossas vidas. Tornamo-nos dependentes deles para aceder à informação, comunicar e nos desolocarmos, e passaram a estar sempre presentes na nossa vida tanto com social como profissional.

Toda nova tecnologia apresenta novos riscos de segurança e acompanhar essas mudanças é um dos principais desafios que a industria da segurança enfrenta. O lado defensivo está sempre uns passos atrás. Por exemplo, uma pratica comum para muitos foi aplicar formas ultrapassadas de fazer as coisas: os smartphones são como pequenos computadores, e as applicação móveis são como software clássico, então certamente os requisitos de segurança são similares? Não, não é assim que funciona. Os sistemas operativos dos smartphones são diferentes dos sistemas operativos dos computadores de secretária e as aplicaçãos móveis são diferentes da aplicações web. Por exemplo, o método classico de procura de virus baseado em assinaturas não faz sentido em ambientes de sistemas operativos móveis modernos, não é só incompativel com o modelo de distribuição de aplicações móveis, como também é tecnicamente impossivel devido a restrições de sandboxing. Algumas classes de vulnerabilidades tais com buffer overflows e XSS são menos relevantes no contexto das aplicações móvies do que o são em aplicações web ou em aplicações Desktop (existem exceções).

Com o tempo, a nossa industria percebeu melhor cenário das ameaças móvies. Como se vê, a segurança móvel tem tudo a ver com proteção de dados: as aplicações guardam a nossa informação pessoal, fotos, gravações, notas, dados de contas, informações de negócio, localização e muito mais. Elas atuam como clientes que nos ligam aos serviços que usamos diariamente e como centros de comunicação que processam toda e cada uma das mensagens que trocamos com os outros. Comprometer o smartphone de uma pessoa permite o acesso sem restrições à vida pessoa dessa pessoa. Quando consideramos a facilidade com que dispositivos móveis se perdem ou são roubados juntamente com a ascenção do malware móvel, a necessidade da proteção de dados torna-se mais evidente.  

Um padrão de segurança para aplicações móveis deve portanto focar-se na forma como as aplicações manipulam, guardam e protegem a informação sensivel. Embora os sistemas operativos móveis modernos, como iOS e Android ofereçam boas interfaces de programador (APIs) para o armazenamendo e comunicação seguros de dados, eles precisam der ser implementados e usados correctamente para serem eficazes. O armazenamento de dados, a comunicação entre aplicações, o uso adequado de APIs criptográficas e a comunicação de rede de forma segura são apenas alguns aspectos que requrem um especial cudidado.

Um questão importante que precisa de consenso da industria é até que ponto é que se deve ir para proteger a confidencialidade e integridade dos dados. Por exemplo, a maioria de nós iria concordar que as aplicações móveis devem verificar os certificados do servidor numa troca de TLS. Mas e a fixação de certificados SSL? O não faze-lo pode resultar numa vulnerabilidade? Isso deve ser um requsisito quando a aplicação lida com informação sensivel, ou é tavez até contra-producente? Precisamos de cifrar dados armazenados em bases de dados SQLite, mesmo que o SO execute a aplicação numa sandbox? O que é apropriado para uma aplicação pode não ser realista para outra. O MASVS é uma tentativa de padronizar esses requisitos usando niveis de verificação que se ajustam aos diferentes cenários de emeaças.

Além disso, o surgimento de root malware e ferramentas de administração remota criou a consciencialização para o facto de os próprios sistemas operativos móveis terem falhas exploráveis, portanto as estratéginas de conteinerização são cada vez mais usadas para se proporcionar proteção adicional aos dados sensiveis e prevenir a adulteração no lado do cliente.
É aqui que as coisas ficam complicadas. Recursos de segurança suportados por hardware e soluções de contentor no nível do SO, como Android for Work e Samsung Knox, existem, mas não estão disponíveis de forma consistente em dispositivos diferentes. Tal como um curativo, é possível implementar medidas de proteção baseadas em software - mas, infelizmente, não existem padrões ou processos de teste para verificar esses tipos de proteções.

Como resultado, os relatórios de testes de segurança de aplicações móveis estão por todo lado: por exemplo, alguns testadores relatam a falta de ofuscação ou detecção de root nas aplicações Andorid como uma "falha de segurança". Por outro lado, medidadas como encriptação de string, deteção de depuração ou ofuscação de control de fluxo não são consideradas obrigatórias. Contudo, essa forma binária de olhar para as coisas não faz sentido porque a resiliência não é uma porposição binária: depende das ameaças especificas do cliente que queremos defender. As proteções de software não são inúteis, mas podem eventualmente ser ultrapassadas, portanto nunca devem ser usadas como substituto de controlos de segurança.

O objectivo geral do MASVS é oferecer um ponto de partida para a segurança de aplicações móveis (MASVS-L1), ao mesmo tempo que permite a introdução de medidas de defesa em profundidade (MASVS-L2) e proteções contra ameaças do cliente (MASVS-R). O MASVS via atingtig o seguinte:

- Fornecer requesitos para arquitetos e programadores de software que procuram aplicações móveis seguras.
- Oferecer um padrão da industria que possa ser testado nas revisões de segurança de aplicações móveis.
- Esclarecer o papel dos mecanisms de proteção de software na segurança de aplicações móveis e fornecer requesitos para verificar a sua eficácia.

Estamos cientes que é impossivel atingir um consenso de 100% na industria. No entanto, esperamos que o MASVS seja útil para fornecer orientação em todas as fases do desenvolvimento e teste de aplicações móveis. Como um padrão de código aberto, o MASVS evoluirá com o tempo e agradecemos quaisquer contribuições e sugestões.