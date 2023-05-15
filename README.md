# Sub-rede no Cisco Packet Tracer
######  Basicamente, um sub-rede é uma divisão lógica de uma rede maior. Nesse repositório, estará descrito como é possível fazer essa divisão no Cisco Packet Tracer.

## Cálculo de sub-rede
###### Primeiro precisamos fazer esse cálculo de sub-rede para saber onde começa e onde termina uma rede. Aqui também é possível definir o endereço broadcast de cada sub-rede. 

Primeiramente, precisamos definir uma máscara de rede( Quantos bits identificarão a rede e quantos identificarão os host), para exemplo, vamos utilizar a máscara de rede /26 mas esse cálculo se aplica a qualquer máscara. Sendo /26, isso significa que 26 bits serão utilizados para identificar a rede e 6 bits identificarão os hosts.

Após definir qual será a máscara, precisamos definir o "Salto", esse definirá onde é o término e o início da próxima sub-rede. Nessa rede /26, o salto será 64, pois--> Cálculo: 2^(32 - máscara de sub-rede) = 2^(32-26) = 2^(6) = 64; Bem, com esse valor, sabemos que a cada 64 "saltos" começa uma nova rede. Dessa forma, teríamos 4 redes: 

* Rede 1: 192.168.0.0 -- 192.168.0.63
* Rede 2: 192.168.0.64 -- 192.168.0.127
* Rede 3: 192.168.0.128 -- 192.168.0.191
* Rede 4: 192.168.0.192 -- 192.168.0.255

## Implementação no Cisco Packet Tracer
###### Depois de ter uma noção do que seria uma sub-rede, vamos fazer sua implementação. Considere a imagem.
[IMAGEM]

