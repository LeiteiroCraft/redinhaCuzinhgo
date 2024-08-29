import ipaddress

ipClasseCFirst = ipaddress.ip_address('192.168.0.0')
ipClasseBFirst = ipaddress.ip_address('172.16.0.0')
ipClasseAFirst = ipaddress.ip_address('10.0.0.0')

ipClasseCLast = ipaddress.ip_address('192.168.10.0')
ipClasseBLast = ipaddress.ip_address('172.31.255.255')
ipClasseALast = ipaddress.ip_address('10.255.255.255')


print(ipClasseCFirst)

ip_incremmentC = ipClasseCFirst + 256 - 1      
ip_incremmentB = ipClasseBFirst + 256 - 1
ip_incremmentA = ipClasseAFirst + 256 - 1


redeTestC = ipaddress.ip_network('192.168.0.0/24', strict=False)
redeTestB = ipaddress.ip_network("172.16.0.0/16", strict=False)
redeTestA = ipaddress.ip_network("10.0.0.0/8", strict=False)

redeHostC = ipaddress.ip_interface('192.0.2.1/24')
redeHostB = ipaddress.ip_interface('172.16.0.0/16')
redeHostA = ipaddress.ip_interface('10.0.0.1/8')

redeTestA.num_addresses
redeTestB.num_addresses
redeTestC.num_addresses

mascara_cidrC = redeHostC.network.prefixlen
mascara_decimalC = redeHostC.network.netmask

mascara_cidrB = redeHostB.network.prefixlen
mascara_decimalB = redeHostB.network.netmask

mascara_cidrA = redeHostA.network.prefixlen
mascara_decimalA = redeHostA.network.netmask



print("Digite que tipo de rede você deseja listar: ")

x = int(input("Digite 1 para classe A, 2 para B e 3 para C"))

if x == 3:
    for ip_incremmentC in redeTestC:
        print(f" listando hosts em classe C:{ip_incremmentC}")
        print("\n")
        
        print(f"a mascara CIDR é:{mascara_cidrC}")
        print("\n")
        
        print(f"e a mascara de Rede em decimal é:{mascara_decimalC}")        
elif x == 2:
    for ip_incremmentB in redeTestB:
        print(f" listando hosts em casse B:{ip_incremmentB}")
        print("\n")
        
        print(f"a mascara CIDR é: {mascara_cidrB}")
        print("\n")
        
        print(f"e a mascara de rede em decimal é {mascara_decimalB}")
    
elif x == 1:
    for ip_incremmentA in redeTestA:
        print(f"looping classe A for the hosts{ip_incremmentA}")
        print("\n")
        
        print(f"a mascara CIDR é: {mascara_cidrA}")
        print("\n")
        
        print(f"a mascara em decimal é: {mascara_decimalA}")    
        
        
        
        
        
        
