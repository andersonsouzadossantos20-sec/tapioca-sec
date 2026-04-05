# 🌐 Infraestrutura e Protocolos de Rede

> "Você não pode proteger o que não consegue entender." 

### ❓ Para que serve esta pasta?
Esta pasta é o alicerce do meu aprendizado. Em Cibersegurança, a rede é o campo de batalha. Aqui eu documento como os dados são segmentados, endereçados e transmitidos. Se um hacker quer invadir um sistema, ele quase sempre passará pela rede primeiro. Entender os protocolos aqui listados é o que me permite detectar anomalias e fechar brechas.

### 🛡️ Redes na Cibersegurança: Por que estudar isso?
* **Análise de Tráfego:** Saber ler um cabeçalho IP no Wireshark para identificar um ataque.
* **Defesa de Perímetro:** Configurar Firewalls e Gateways para impedir acessos não autorizados.
* **Movimentação Lateral:** Entender como um invasor pula de um PC para outro dentro da mesma LAN (ARP/MAC).
* **Segurança de Protocolo:** Identificar por que protocolos como HTTP ou Telnet são perigosos (tráfego em texto claro).

## 🛠️ Matriz de Conhecimento (Modelo OSI)

| Camada | O que eu estudo | Relevância para Segurança |
| :--- | :--- | :--- |
| **7. Aplicação** | HTTP, DNS, DHCP | Onde ocorrem ataques de Phishing e sequestro de DNS. |
| **4. Transporte** | TCP, UDP, Portas | Identificação de Port Scanning e ataques de negação de serviço (DoS). |
| **3. Rede** | IPv4, IPv6, ICMP, ARP | Base para entender IP Spoofing e ataques Man-in-the-Middle. |
| **2. Enlace** | Ethernet, MAC, Switches | Onde ocorrem ataques de MAC Flooding e envenenamento de tabela ARP. |

## 🚀 Práticas e Laboratórios
* **Cisco Packet Tracer:** Construção de topologias seguras e segmentação de VLANs.
* **Wireshark Deep Dive:** Captura e inspeção de pacotes para perícia digital.
* **Curso de redes basica da cisco:** ensina o basico sobre redes.

---
