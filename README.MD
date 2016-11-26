Projeto de Portão Eletrônico Automático
===================

####  O Projeto

A ideia é a de criar um mecanismo que controle a abertura de um portão eletrônico de garagem de acordo com a aproximação do usuário. Um arduino seria conectado ao controle da garagem para que o mesmo possa ser acionado a partir de um impulso do controlador. 

Uma aplicação Android foi criada, que ao usuário entrar em um raio predefinido, um assistente de voz pergunta se usuário deseja abrir o portão. A resposta do usuário é feita através de um comando de voz e, caso o comando seja "Sim", o aplicativo envia uma requisição para a nuvem, que por sua vez comunica com o Arduino.

O Arduino faz comunicação com o serviço IOT Hub da Azure, utilizando o padrão publish-subscribe, de forma que posso receber impulsos para acionar a abertura do portão. O IOT Hub, por sua vez, possui um mapeamento do microcontrolador, e recebe comandos de uma aplicação Node.js, também implantada no Azure. A aplicação Node.js é responsável por expor a api utilzada pelo aplicativo Android, assim como enviar comando para o IOT Hub.

####  Limitações
Como o grupo não possui conhecimento de eletrônica, foi acordado que, ao invés de acionar o controle do portão, apenas acenderíamos um led no arduíno. 
