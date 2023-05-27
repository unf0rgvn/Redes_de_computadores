# Sub-rede no Cisco Packet Tracer
######  Basicamente, um sub-rede é uma divisão lógica de uma rede maior. Nesse repositório, estará descrito como é possível fazer essa divisão no Cisco Packet Tracer.

## Cálculo de sub-rede
###### Primeiro precisamos fazer esse cálculo de sub-rede para saber onde começa e onde termina uma rede. Aqui também é possível definir o endereço broadcast de cada sub-rede. 

Primeiramente, precisamos definir uma máscara de rede( Quantos bits identificarão a rede e quantos identificarão os host), para exemplo, vamos utilizar a máscara de rede /26 mas esse cálculo se aplica a qualquer máscara. Sendo /26, isso significa que 26 bits serão utilizados para identificar a rede e 6 bits identificarão os hosts.

Após definir qual será a máscara, precisamos definir o "Salto", esse definirá onde é o término e o início da próxima sub-rede. Nessa rede /26, o salto será 64, pois--> Cálculo: 2^(32 - máscara de sub-rede) = 2^(32-26) = 2^(6) = 64; Bem, com esse valor, sabemos que a cada 64 "saltos" começa uma nova rede. Dessa forma, teríamos 4 sub-redes: 

| Rede | Hosts | Broadcast
| ---- | ----- | ---------
192.168.0.0 | 192.168.0.1 -- 192.168.0.62 | 192.168.0.63
192.168.0.64 | 192.168.0.65 -- 192.168.0.126 | 192.168.0.127
192.168.0.128 | 192.168.0.129 -- 192.168.0.190 | 192.168.0.191
192.168.0.192 | 192.168.0.193 -- 192.168.0.254 | 192.168.0.255

Para reforçar o que fizemos: A rede /26, tem 26 bits que identificam a rede, logo tem 6 bits reservados para os HOSTs, se fizermos 2^6 = 64 --> esse número indica que a cada 64 endereços começa uma sub-rede.

## Implementação no Cisco Packet Tracer
###### Depois de ter uma noção do que seria uma sub-rede, vamos fazer sua implementação.

Como foi dito nos parágrafos anteriores, a máscara de rede(junto com o salto) define onde começa e termina uma rede, como o salto que descobrimos foi de 64, basta fazer 256 - 64 = 192 --> esse número é a representação em decimal dos 6 bits que foram destinados aos HOSTs. Juntando tudo o que foi dito na montagem da máscara de rede teríamos: 255.255.255.192.

Sabendo disso, basta aplicar no dispositivos.
[IMAGEM1]
[IMAGEM2]

Pronto! As sub-redes estão definidos, caso queiramos que elas se comuniquem precisaremos de um roteador pois ele faz o trabalho de comunicar redes diferentes. Obs: Em vários exemplos na internet é possível ver as pessoas utilizando dois roteadores para comunicar as duas redes, aqui utilizarei apenas um pois o foco não é mostrar o roteamente, apenas a criação da sub-rede e comunicação entre elas.

Utilizando o rotador, o esquema no Cisco Packet Tracer fica da seguinte forma:
[IMAGEM3]

O IP definido na porta GigabitEthernet0/0 foi o 192.168.0.62 e na porta GigabitEthernet0/1 foi o 192.168.0.190. Definindo esses IPs como Gateway em suas respectivas sub-rede, basta fazer um teste de ping entre os computaodores. O esquema final ficou da seguinte forma:
[IMAGEM4]

O arquivo que criei para apresentar esses conceitos está disponível para download, recomendo usar apenas para comparação, tente pegar o que aprendeu aqui e faça sozinho, usando outras máscaras de rede e métodos diferentes de comunicação entre as sub-redes 
