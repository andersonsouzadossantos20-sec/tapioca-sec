# 📚 Registro de Estudo — Cibersegurança

**Data:** 05/04/2026  
**Tema:** Módulo 13 da Cisco — O Processo de ARP  
**Área:** Camada de Rede / Resolução de Endereços

---

## 🎯 Objetivo do Estudo

Entender como os dispositivos mapeiam endereços IPv4 para endereços MAC através do protocolo ARP, permitindo que a comunicação ocorra dentro de uma rede local.

---

## 📖 Conceitos Fundamentais

- **ARP (Address Resolution Protocol):** O "tradutor" que descobre o endereço MAC de um dispositivo quando só conhecemos o seu IP.
- **Tabela ARP (ARP Cache):** Uma lista temporária na memória do dispositivo que guarda os pares IP/MAC já descobertos.
- **Broadcast ARP:** O grito que o PC dá na rede: "Quem tem o IP 192.168.1.10? Me mande seu MAC!".
- **Resolução de Endereço:** O processo de vincular a Camada 3 (IP) à Camada 2 (MAC).

---

## 🧠 Explicação Técnica

Quando um PC quer enviar um dado, ele sabe o IP de destino. Mas o **Quadro Ethernet** (Camada 2) precisa obrigatoriamente de um MAC de destino para viajar pelo cabo. 

O processo funciona assim:
1. O host verifica sua **Tabela ARP**. Se o MAC já estiver lá, ele envia o dado.
2. Se não estiver, ele envia um **ARP Request** (Broadcast). Todos na rede recebem, mas só o dono do IP responde.
3. O dono responde com um **ARP Reply** (Unicast) contendo seu MAC.
4. O host guarda essa info na tabela e finalmente envia os dados.


---

## 🔧 Tecnologias / Ferramentas Relacionadas

- **IPv4:** O ARP é exclusivo para o mundo IPv4 (No IPv6, quem faz isso é o ICMPv6).
- **Switches:** Eles não leem o ARP, mas aprendem os MACs que passam por eles para organizar as portas.

---

## 💻 Comandos / Sintaxe Importante

*Essenciais para investigar a rede no Kali ou Windows:*
- `arp -a`: Mostra a tabela ARP atual (vê quem o seu PC "conhece" no momento).
- `arp -d *` (Windows) ou `ip -s neigh flush all` (Linux): Limpa a tabela ARP para forçar novas descobertas.

---

## 🔬 Experimento / Prática

Percebi que o ARP só funciona para a **Rede Local**. Se o destino estiver na internet, o meu PC faz um ARP para descobrir o MAC do **Gateway Padrão** (roteador), e não o MAC do servidor remoto.

---

## 📊 Resultados Observados

- O ARP economiza banda: ele só pergunta uma vez e guarda a resposta por alguns minutos.
- É um protocolo baseado na "confiança": ele acredita na resposta que recebe sem verificar se é verdade.

---

## ⚠️ Problemas Encontrados

Entender que o ARP é um protocolo de "baixo nível" que acontece antes mesmo do primeiro pacote de dados ser enviado.

---

## 🛠️ Solução

Se o `ping` falha com "Host inacessível", o primeiro lugar que eu olho agora é a tabela ARP para ver se houve resposta física do dispositivo.

---

## 🔐 Relação com Cibersegurança

Aqui o perigo é real! Como o ARP confia em qualquer um:
- **ARP Spoofing / Poisoning:** O atacante envia um ARP Reply falso dizendo: "Eu sou o roteador!". O seu PC acredita, limpa a tabela antiga e passa a enviar todos os seus dados (senhas, fotos) para o hacker. 
- É a base para ataques de **Man-in-the-Middle (MitM)**. Ferramentas como `Ettercap` ou `Bettercap` no Kali exploram exatamente essa falha de design.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
|------|-------------|
| **ARP Request** | Pergunta em broadcast: "De quem é esse IP?". |
| **ARP Reply** | Resposta direta: "O IP é meu e meu MAC é esse". |
| **Static ARP** | Configurar o MAC manualmente na tabela para evitar ataques de Spoofing. |

---

## 🧩 Insight do Dia

"O ARP é o aperto de mão inicial da rede local. Se você conseguir enganar esse aperto de mão, você controla toda a conversa."

---

## 📖 Próximo Passo

Estudar **Módulo 14 — **Roteamento entre redes** 

---

## 📌 Resumo Final

O Módulo 13 mostrou que a rede é baseada em confiança, e que o IP sozinho não faz nada sem o MAC. Para cibersegurança, dominar o ARP é essencial para entender como interceptar tráfego e proteger redes locais contra invasores.
