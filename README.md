# Projeto Mininet

## Criar a Topologia com Mininet

1. O comando a seguir cria uma topologia do tipo árvore (tree) com:

- Profundidade de 4 níveis (depth=4)
- Dois ramos por nível (fanout=2)
- Largura de banda de 25 Mbps para os links
- Endereços MAC padronizados para cada nó
- Controlador padrão do Mininet

```sh
    sudo mn --topo tree,depth=4,fanout=2 --mac --link=tc,bw=25
```

![Criar_topologia_mininet](./imagens/Criar_topologia_mininet.png)

## Inspeção das interfaces, endereços MAC, IP e portas

2. informações das interfaces de rede, endereços MAC, IP e tabela ARP para ver a correspondência de endereços IP e MAC.

```sh
    h1 ifconfig
```

![info_host_1](./imagens/info_host_1.png)

```sh
    h2 ifconfig
```

![info_host_2](./imagens/info_host_2.png)

```sh
    nodes
```

![tabela_ARP_host_1](./imagens/nodes.png)

```sh
    net
```

![tabela_ARP_host_1](./imagens/net.png)

```sh
    dump
```

![tabela_ARP_host_1](./imagens/dump.png)

```sh
    h1 arp -n
```

![tabela_ARP_host_2](./imagens/tabela_ARP_host_1.png)

```sh
    h2 arp -n
```

![tabela_ARP_host_2](./imagens/tabela_ARP_host_2.png)

## Testar Conectividade com Ping

3. testando a conectividade entre Host 1 e Host 2 e entre todos os nós da topologia.

```sh
    h1 ping h2
```

![ping_host_1_e_host_2](./imagens/ping_host_1_e_host_2.png)

```sh
    pingall
```

![pingall](./imagens/pingall.png)

## Configuração do servidor e cliente TCP com iperf

```sh
    h1 iperf -s -p 5555
```

![pingall](./imagens/h1_iperf.png)

```sh
    h2 iperf -c h1 -p 5555 -i 1 -t 10 -b 25M
```

![pingall](./imagens/h2_iperf.png)

