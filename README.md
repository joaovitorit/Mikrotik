# Scripts Mikrotik

########## Aplicando configuração de bloqueio no acesso externo aos roteadores dos clientes ##########

/ip firewall filter

add action=drop chain=forward comment=Dropar-Acesso-Externo dst-address-list=\
    
    rede-asn dst-port=8292 protocol=tcp src-address-list=!rede-local
                
Explicação da regra:

add = Adiciona um regra na tabela do mikrotik

action = Ação aplicada na regra

chain = Cadeia de regra do firewall do Mikrotik (Mikrotik Usa Iptables com Firewall)

comment = Apenas um texto para identificar a regra

dst-address-list= Rede de destino que vai ser aplicado a regra (Nesse caso foi criado uma address list que no mikrotik é uma lista de ips)

dst-port = Qual porta vai ser aplicado a regra

protocolo = Qual protocolo vai ser aplicado na regra EX: tcp/udp/icmp/gre dentre outros

src-address-list = Rede de origem que deve ser aplicado a regra (Aqui temos uma particularidade adicionamos uma excesão representado por o sinel "!" com esse sinal 
na frente da regra estamos informando que a regra vai ser aplicado com origem de qualquer rede exceto a que está na lista de ip Address-list)

