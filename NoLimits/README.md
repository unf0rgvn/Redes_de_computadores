#### Nesse diretório irei apresentar como foi o procedimento para desenvolver a estrutura de uma empresa fictícia, a NoLimits.

## Solicitação da Empresa
"A empresa NoLimits recebeu um aporte de capital de um investidor e criará uma nova estrutura computacional para atender às projeções de crescimento. Para viabilizar as atividades das áreas de produção e logística, dois endereços físicos, separados por 500 metros de distância, já estão em construção. As unidades de produção e logística devem compartilhar a mesma estrutura de comunicação (interna e externa), sendo que na produção estão previstos 120 computadores (distribuídos nos setores de P&D, qualidade e compras), enquanto na logística, por manter a estrutura administrativa e de desenvolvimento, contará com 75 computadores. Para garantir que a inauguração ocorra no dia 15/12, contratou uma renomada equipe de tecnologia para projetar a estrutura de redes, prevendo um ambiente seguro e de alta performance"

## Organizando a distribuição (Projeto Lógico)

Para organizar como ficará o projeto lógico, vamos começar escolhendo uma das Unidades, nesse caso vou escolher a Unidade de Produção.

"Na produção estão previstos 120 computadores(distribuídos nos setores de P&D, qualidade e compras)". Nesse caso, somando os 3 setores teremos um total de 120 computadores, se dividirmos esse total de computadores pelo número de setores teremos: `120 / 3 = 40 computadores em cada setor`. Certo, como são 40 computadores por setor, em cada setor teríamos que ter dois switches já que um switch(O que iremos utilizar) tem apenas 24 portas.

Colocando o que foi descrito acima no Packet Tracer, teremos a seguinte representação:
[Imagem]

Tendo essa parte já concluída precisamos pensar a rede ficará definida, como serão distribuídos os IPs entre os dipositivos e qual será a faixa de rede que eles estarão. Pense comigo... como nesse setor tem um total de 120 computadores, uma rede pode comportar até 254 dispositivos, logo uma rede já suficiente para o que queremos. 


