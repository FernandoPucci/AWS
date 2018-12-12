## REGIOES
 São regiões geográficas no mundo onde a Amazon possui disponibilidade de serviços.

 Nem toda região possui todos os serviços. - Durante o curso será utilizada a região da Virgínia.

### ZONAS DE DISPONIBILIDADE	
 A exemplo da Datacenters na mesma região. São interligados, entretanto, são independentes em energia, rede, etc.

 Na implantação de aplicações de alta disponibilidade, pode-se implantar mais de uma instância da aplicação na mesma região, entretanto **não se deve usasr a mesma zona de disponibilidade**, que por sua vez deve ser configurada com __load balancer__ por exemplo, garantindo a manutenção da alta disponibilidade. 

 O tráfego entre zonas de disponibildade não tem custo, exceto para banco de dados.

### PONTOS DE PRESENÇA
 Pontos de presença, são como __caches__ espalhados pelo mundo. São utilizados por exemplo pelo CDN (Cloud front) e serviços de DNS.
