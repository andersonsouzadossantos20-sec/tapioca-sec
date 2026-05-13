# 📚 Registro de Estudo — Cibersegurança

**Data:** 13/05/2026  
**Tema:** Módulo 3 da Cisco — Atacando a Fundação  
**Área:** Segurança de Endpoint e Vulnerabilidades de Protocolo

---

## 🎯 Objetivo do Estudo

Analisar as vulnerabilidades inerentes aos protocolos das camadas de Rede (IP) e Transporte (TCP/UDP), compreendendo como as deficiências de design no IPv4, IPv6, TCP e UDP são exploradas por atores de ameaças para comprometer sistemas.

---

## 📖 Conceitos Fundamentais

- **Protocolo IP (Internet Protocol):** Projetado como um protocolo de Camada 3 "sem conexão". O cabeçalho IPv4 é complexo e propenso a manipulações, enquanto o IPv6, embora simplificado, mantém desafios de segurança específicos de transição e roteamento.
- **Protocolo ICMP:** Criado para diagnóstico. É a "ferramenta de eco" da rede, mas é frequentemente abusado para mapeamento de topologia (reconhecimento) e ataques de negação de serviço.
- **TCP vs. UDP:** * **TCP:** Focado em confiabilidade; vulnerável em seu processo de conexão (handshake).
    * **UDP:** Focado em velocidade; vulnerável por não possuir verificação de recepção (fácil de inundar).

---

## 🧠 Explicação Técnica

### 🛡️ Vulnerabilidades de IP e ICMP
* **DoS e DDoS:** Uso de pacotes ICMP para ataques de amplificação, visando paralisar o alvo.
* **Falsificação (Spoofing):** Manipulação do endereço IP de origem para mascarar a identidade do atacante ou contornar filtros de segurança.
* **Ataques Man-in-the-Middle (MiTM):** Interceptação e possível alteração do tráfego entre dois pontos legítimos sem que eles percebam.

### ⚡ Vulnerabilidades de Transporte (TCP/UDP)
* **SYN Flood:** Ataque que interrompe o handshake TCP, deixando o servidor com milhares de conexões "meio abertas", esgotando sua memória.
* **Sequestro de Sessão (Session Hijacking):** O ato de prever o próximo número de sequência TCP para assumir uma conexão ativa.
* **Inundação UDP:** Como não há confirmação de entrega, o atacante sobrecarrega a rede com datagramas, forçando respostas de "Porta Inalcançável" que consomem todo o processamento do host.

---

## 🔬 Observação Prática (Foco em Segurança)

O analista deve monitorar padrões fora do comum:
- **Port Scanning:** Se um único IP tenta conectar-se a centenas de portas em segundos, é um batedor inimigo testando os muros.
- **Flags TCP Anômalas:** Pacotes com flags RST (Reset) ou FIN (Finish) injetados podem ser usados para derrubar conexões legítimas de forma abrupta.

---

## ⚠️ Problemas Encontrados

Confusão recorrente entre **Falsificação de Endereço IP** (Lógica) e **Falsificação de Endereço MAC** (Física).
* *Correção:* IP Spoofing é usado para ataques que atravessam roteadores; MAC Spoofing é limitado ao mesmo segmento de rede local (Wi-Fi ou Switch comum).

---

## 🔐 Relação com Cibersegurança

- **Filtragem de Entrada/Saída:** Configuração de ACLs (Listas de Controle de Acesso) para impedir que pacotes com IPs forjados entrem ou saiam da rede interna.
- **Inspeção de Estado (Stateful Inspection):** Capacidade do firewall de entender se um pacote faz parte de uma conversa legítima ou se é um intruso tentando "pular a janela".

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **Best-Effort** | Entrega de "melhor esforço" (IP/UDP), sem garantia de que os dados chegarão. |
| **PDU** | Protocol Data Unit. No IP chamamos de Pacote; no TCP, Segmento; no UDP, Datagrama. |
| **Three-Way Handshake** | O aperto de mão em três passos (SYN, SYN-ACK, ACK) que estabelece o TCP. |
| **Amplificação ICMP** | Uso de mensagens de erro para gerar um volume de tráfego maior que a capacidade do alvo. |

---

## 🧩 Insight do Dia

> "Em redes, 'confiança' é uma vulnerabilidade. Protocolos feitos para serem eficientes em 1980 não previram que o mundo estaria conectado em 2026. Segurança hoje é, em grande parte, consertar o que foi desenhado para ser apenas funcional."

---

## 📖 Próximo Passo

Prosseguir para o **Módulo 4 — Atacando o que fazemos**, focando em ataques de camada de aplicação e serviços específicos como DNS e HTTP.

---

## 📌 Resumo Final

O Módulo 3 é o alicerce. Sem entender como o IP e o TCP podem ser distorcidos, o analista é apenas um espectador. Dominar esses ataques de "fundação" permite que você antecipe o movimento do atacante antes mesmo dele chegar à aplicação final.
