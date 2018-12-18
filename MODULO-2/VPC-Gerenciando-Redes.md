## VPC GERENCIANDO REDES
NETWORKING & CONTENT DELIVERY > VPC

Um dos conceitos mais importantes da AWS.  

VPC - Virtual Private Cloud, nossa própria rede virtual na nuvem.  

Pode-se criar mais de uma VPC, uma rede totalmente isolada.  

Cada VPC é composta de diversas sub-nets. As subnets sim, são VLANs.  

Uma VPC é uma rede propriamente dita, não uma VLAN. Uma estrutura de VPC não se comunica com outra VPC.  

Pode se criar VPCs com subnets, separando dominios, para o mundo exterior e interior da nuvem.  

Ex.: Maquina de Banco de dados não possui acesso externo, somente o servidor Web possui acesso externo.  
Então separa-se sub-nets, uma pública para o web server e uma privada, para o Banco de dados. Ambas na mesma VPC comunicando entre si.  
Podemos por exemplo conectar a uma subnet através de tunel de VPN.  
Esta instância privada, não possui acesso a internet. Para a necessidade de se desejar atualizar um pacote ou imagem, por exemplo, cria-se uma instancia NAT, que garante este acesso.  

No curso será criado VPC, com subnets separadas em Zonas de disponibilidade, cada ZD com duas subnets, uma publica (servidor web) e outra privada (banco de dados).  

Sugere-se que na AWS se trabalhe com o minimo de duas ZDs, para permitir o balanceamento e melhor disponibilidade da aplicação.  

## CRIAÇÂO VPC
>- 1. Cria-se a VPC `10.10.0.0/16`;  
>- 2. Cria-se duas sub-nets publicas (`10.10.1.0/24` [ZD-1a] e `10.10.2.0/24`[ZD-1b]) e 2 subnets privadas (`10.10.3.0/24`[ZD-1a], `10.10.4.0/24`[ZD-1b]);   
>-      Obs.: O que diferencia uma subnet publica de uma subnet privada, é que a privada não possui Gateway Default, não possui uma rota (Route Tables).  
>- 3. Cria-se as Route Table (Tabela de Roteamento) Para as redes públicas (RT-CURSO-PUBLIC e RT-CURSO-PRIV).  
>- 4. Adiciona-se um Internet Gateway, para a tabela de roteamento publica.  
>-      Obs.: O IG deve ser 'atachado' a uma VPC, no nosso caso VPC-CURSO.  
>- 5. novamente em Route Tables, associa-se `0.0.0.0/0` ao IG criado anteriormente, na rota publica.  
      5.1 Associa-se a Rota Publica às subnets publicas e a Rota privadas às subnets privadas.  


### OUTRAS NOMENCLATUREAS  
Elastic IP - Utilizado nas EC2. vide aulas EC2;  
Endpoints - Forma de intercomunicação entre instâncias de rede privada e o serviço S3 (Scalable Storage), sem necessidade de NAT para a rede exterior;  
NAT - Permite criação de uma forma para que uma instancia privada acesse a Internet;  
Peering - Permite comunicação entre outras ZDs ou VPCs.  

