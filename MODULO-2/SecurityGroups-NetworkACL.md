## SECURITY GROUPS & NETWORK ACLs
Security group - opera a nível de instância, como se fosse um **FIREWALL** da instância local (Firewall da maquina). Saida sempre permitida;  

Network ACL - Opera em nível de rede/sub-rede,associada no momento de criação, necessita liberações de entrada e saída, como IPTABLES, por exemplo. Assemelha-se a um firewall da ponta da rede.    

Esetas conficurações podem ser realizadas tanto no painel do EC2, quando das VPCs.  

*Quando se cria uma VPC, a AWS já cria uma ACL e um Security Group.
Por padrão, as ACLs criadas por default, estão com todos os tráfegos liberados (ALLOW).

### CRIAÇÂO DA ACL
Após a criação de uma ACL, deve-se associar uma subnet à ela. 
Por padrão, ao se criar uma ACL, todo tráfego é BLOQUEADO.

Obs..: lembrar de sempre liberar o outbound e inbound para as 'portas altas', no range 49152-65535.  

### CRIAÇÂO DO SECURITY GROUP
Por padrão, num Security Group todo tráfego de saída é liberado.
