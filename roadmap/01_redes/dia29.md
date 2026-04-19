# 📚 Registro de Estudo — Cibersegurança

**Data:** 19/04/2026  
**Tema:** Módulo 7 da Cisco — Resolução De Endereços
**Área:** Camada de Enlace e Rede (Comunicação L3 para L2)

---

## 🎯 Objetivo do Estudo

Entender como os dispositivos mapeiam endereços IP (Camada 3) para endereços MAC (Camada 2) usando o **ARP**, permitindo que os dados sejam encapsulados corretamente em quadros Ethernet para entrega local.

---

## 📖 Conceitos Fundamentais

- **ARP (Address Resolution Protocol):** Protocolo usado para descobrir o endereço MAC de um dispositivo quando apenas o endereço IPv4 é conhecido.
- **Tabela ARP (Cache ARP):** Uma lista mantida na memória RAM do dispositivo que armazena temporariamente os mapeamentos IP-para-MAC.
- **Mapeamento:** A ligação lógica entre o "quem" (IP) e o "ID físico" (MAC).

---

## 🧠 Explicação Técnica

### 🛠️ Como o ARP Funciona
Quando um host quer enviar dados para outro na mesma rede:
1. Ele verifica sua **Tabela ARP** para ver se já tem o MAC do IP de destino.
2. Se não tiver, ele envia um **ARP Request** (em Broadcast: `FF-FF-FF-FF-FF-FF`).
3. O dispositivo com o IP correspondente responde com um **ARP Reply** (Unicast), informando seu MAC.
4. O host de origem armazena esse dado e finalmente monta o quadro Ethernet.



### 🛰️ ARP e o Gateway Padrão
Se o destino estiver em uma **rede remota** (Internet):
- O host envia um ARP Request para o IP do **Roteador (Gateway Padrão)**.
- O roteador responde com seu próprio MAC.
- Os dados são enviados para o roteador, que então encaminha para a rede externa.

---

## 🔢 Diferenças no IPv6: Neighbor Discovery (ND)

O IPv6 não utiliza ARP. Ele utiliza o protocolo **ICMPv6** através do processo de **Neighbor Discovery (ND)** para realizar a mesma função de descoberta de vizinhos de forma mais eficiente.

---

## 💻 Conceitos Operacionais Importantes

- **Broadcast ARP:** Pode gerar tráfego excessivo se muitos dispositivos estiverem fazendo requisições ao mesmo tempo.
- **Timer de Cache:** As entradas na tabela ARP não são permanentes; elas expiram após alguns minutos de inatividade para garantir que a tabela não fique desatualizada.
- **Comando CLI:** No Windows ou Linux, use `arp -a` para visualizar sua tabela atual.

---

## 🔬 Observação Prática (Foco em Segurança)

O ARP é um protocolo baseado em **confiança implícita**, o que gera vulnerabilidades críticas:
- **ARP Spoofing / Poisoning:** Um atacante envia mensagens ARP falsas para dizer que o MAC dele pertence ao IP do Gateway. Isso permite interceptar todo o tráfego da vítima (**Man-in-the-Middle**).
- **Inspeção ARP Dinâmica (DAI):** Recurso de segurança em switches para validar pacotes ARP e impedir ataques de falsificação.

---

## ⚠️ Problemas Encontrados

O dispositivo tem o IP correto, mas não consegue pingar o vizinho.  
*Solução:* Verifique se a tabela ARP está vazia ou se o MAC associado ao IP está correto. Se houver dois MACs para o mesmo IP, você pode estar sob ataque ou com conflito de IP.

---

## 🔐 Relação com Cibersegurança

- **Interceptação:** Quase todos os ataques de rede local começam manipulando a tabela ARP.
- **Visibilidade:** Analisar o tráfego ARP com o Wireshark permite identificar scanners de rede e dispositivos não autorizados tentando se comunicar.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **ARP Request** | Pergunta em broadcast: "Quem tem este IP?" |
| **ARP Reply** | Resposta unicast: "Eu tenho este IP e meu MAC é X." |
| **Static ARP** | Entrada manual na tabela ARP que não expira (raro, mas seguro). |
| **Gratuitous ARP** | Mensagem ARP enviada sem ser solicitada, geralmente para anunciar um IP. |

---

## 🧩 Insight do Dia

> "O ARP é o tradutor da rede. Sem ele, o seu computador saberia para onde enviar a carta (IP), mas não saberia como escrever o nome do destinatário no envelope físico (MAC)."

---

## 📖 Próximo Passo

Prosseguir para o **Módulo 8 —Serviço de Endereçamento IP** para entender como o Neighbor Discovery substitui o ARP e melhora a eficiência da rede.

---

## 📌 Resumo Final

O Módulo 7 focou na "cola" que une a Camada 2 e a Camada 3. Para a cibersegurança, dominar o ARP é fundamental, pois é uma das camadas mais frágeis e exploradas em ataques internos de rede.
