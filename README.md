# 
1. Divisão da Aplicação (Microsserviços e Desacoplamento)

Microsserviço 1 (Função Crítica):
Pagamentos e Assinaturas — Responsável por gerenciar os planos e pagamentos dos usuários, além de verificar se o jogador tem permissão para jogar. Caso este serviço falhe, o jogo continua funcionando normalmente; apenas novas compras ou renovações ficam temporariamente indisponíveis.

Microsserviço 2 (Função Crítica):
Chat e Amigos — Permite que os jogadores conversem e visualizem quem está online. Se esse serviço parar, o jogo continua operando, apenas o chat e as interações sociais ficam fora do ar.

Mecanismo de Comunicação:
Para garantir o desacoplamento e evitar que a falha de um microsserviço afete os outros, seria utilizado um serviço de mensageria em nuvem, como filas de mensagens (Message Queues).
Esse mecanismo permite uma comunicação assíncrona, onde os serviços trocam informações sem depender de respostas imediatas, garantindo maior estabilidade e resiliência ao sistema.

2. Alta Resiliência e Disponibilidade (Geografia)

Conceito de Distribuição:
Utilização de Regiões e Zonas de Disponibilidade distribuídas globalmente na infraestrutura em nuvem.

Justificativa:
Essa estratégia garante alta disponibilidade e resiliência, pois, se uma zona ou região apresentar falhas, o sistema continua funcionando em outra. Além disso, melhora a latência, já que os jogadores se conectam à região mais próxima, garantindo uma experiência de jogo mais rápida e estável.

3. Escalabilidade de Tráfego (Entrada)

Serviço Necessário:
Balanceador de Carga (Load Balancer)

Função:
O balanceador de carga é o primeiro componente a receber as conexões dos usuários. Ele distribui o tráfego de forma equilibrada entre os servidores de aplicação, evitando sobrecarga em apenas um deles.
Além disso, detecta falhas automaticamente e redireciona o tráfego para servidores ativos, permitindo que o sistema suporte milhões de acessos simultâneos com estabilidade e desempenho.

4. Segurança por Design (Identity and Access)

Pilar de Segurança (Conceito):
Autenticação e Autorização entre Microsserviços

Por que é Crucial:
Esse pilar garante que apenas microsserviços autenticados e autorizados possam se comunicar entre si, prevenindo acessos indevidos e protegendo informações sensíveis.
Cada serviço precisa comprovar sua identidade digital antes de trocar dados, o que reforça a segurança, integridade e confiabilidade da arquitetura do GameStream.