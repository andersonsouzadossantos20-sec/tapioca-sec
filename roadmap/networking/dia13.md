# 📚 Registro de Estudo — Cibersegurança

**Data:** 02/04/2026  
**Tema:** Módulo 9 da Cisco — IPv4 e Segmentação de Rede  
**Área:** Camada de Rede / Endereçamento

---

## 🎯 Objetivo do Estudo

Entender como os dados são entregues (Unicast, Broadcast e Multicast) e aprender a importância de dividir uma rede grande em pedaços menores (Subnets) para melhorar a performance e a segurança.

---

## 📖 Conceitos Fundamentais

- **Tipos de Transmissão:** Unicast (um para um), Broadcast (um para todos) e Multicast (um para um grupo).
- **Endereços IPv4 Públicos vs. Privados:** O que viaja na internet vs. o que fica só na sua LAN.
- **Endereços Especiais:** Loopback (127.0.0.1) e APIPA (169.254.x.x).
- **Segmentação (Subnetting):** Dividir domínios de broadcast para evitar lentidão.

---

## 🧠 Explicação Técnica

### 1. Formas de Transmissão
- **Unicast:** Comunicação direta. Só quem envia e quem recebe processa o pacote.
- **Broadcast:** O pacote vai para todo mundo na rede local (final `.255`). Útil para o protocolo ARP e DHCP, mas em excesso vira um problema.
- **Multicast:** Economiza banda enviando um pacote para um grupo específico (intervalo `224.0.0.0` a `239.255.255.255`).

### 2. Classes de Endereço (Legado)
Embora hoje usemos o CIDR (sem classe), é essencial conhecer a base:
- **Classe A:** Redes gigantes (ex: grandes ISPs).
- **Classe B:** Redes médias (empresas).
- **Classe C:** Redes pequenas (casa/escritório).

### 3. Por que Segmentar?
Em uma rede grande, o tráfego de **broadcast** (como o ARP) atinge todos os dispositivos. Isso consome processamento de máquinas que não tinham nada a ver com a conversa. Segmentar (criar sub-redes) reduz esses domínios de broadcast, melhora a segurança e facilita a gestão.

---

## 🔧 Tecnologias / Ferramentas Relacionadas

- **DHCP:** Atribui IPs automaticamente enviando broadcasts.
- **NAT:** Traduz endereços privados em públicos para navegar na web.
- **Calculadoras de Subnet:** Ferramentas para planejar a divisão da rede.

---

## 💻 Comandos / Sintaxe Importante

*No Kali Linux, para ver broadcasts e tráfego de rede:*
- `tcpdump -i eth0 -n broadcast`: Captura pacotes de broadcast na interface eth0.
- `ping 224.0.0.1`: Pingo multicast para todos os nós na sub-rede (se estiver habilitado).

---

## 🔬 Experimento / Prática

Análise de por que meu PC às vezes pega o IP `169.254.x.x`: descobri que isso é o **APIPA**, o que significa que meu dispositivo não conseguiu falar com o servidor DHCP. É um sinal clássico de erro na camada física ou no servidor de IPs.

---

## 📊 Resultados Observados

- Redes muito grandes sem segmentação ficam lentas devido ao excesso de "ruído" (broadcast).
- Usar endereços privados (como `192.168.x.x`) é a primeira camada de defesa, pois eles não são roteáveis na internet pública.

---

## ⚠️ Problemas Encontrados

Confundir os limites de classe de IP e as máscaras padrão.

---

## 🛠️ Solução

Focar na **Máscara de Sub-rede**. Ela é quem manda. Se a máscara for `/24` (255.255.255.0), eu sei que os primeiros 3 octetos são a rede e o último é o host.

---

## 🔐 Relação com Cibersegurança

- **Isolamento:** Se um atacante infecta uma sub-rede, a segmentação impede (ou dificulta) que ele se mova lateralmente para outras partes sensíveis da empresa.
- **Prevenção de DoS:** Reduzir domínios de broadcast mitiga alguns tipos de ataques de negação de serviço interno.
- **Reconhecimento:** Entender as classes de IP ajuda a identificar onde estão os servidores e onde estão os usuários durante um teste de invasão.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
|------|-------------|
| **Loopback** | Endereço `127.0.0.1` usado para testar se a pilha TCP/IP do próprio PC está ok. |
| **RFC 1918** | O documento que define os intervalos de IPs privados. |
| **Domínio de Broadcast** | A área da rede onde um pacote de broadcast é propagado. |

---

## 🧩 Insight do Dia

"Dividir para conquistar." No mundo das redes, segmentar não é apenas organizar, é garantir que a rede sobreviva ao seu próprio tráfego.

---

## 📖 Próximo Passo

Estudar **Módulo 10 — Formatos e regras de endereçamento IPv6**.

---

## 📌 Resumo Final

O Módulo 9 ensina que não basta dar um IP para cada um; é preciso agrupar os dispositivos de forma inteligente. Dominar o Unicast/Broadcast e saber quando usar IPs privados é fundamental para qualquer profissional de segurança.
