# 📚 Registro de Estudo — Consolidação e Revisão

**Data:** 03/05/2026  
**Período:** De 21/04/2026 até hoje  
**Tema:** Revisão Estratégica — Módulos 1 ao 9 (Cisco Networking Basics)  
**Status:** Refinamento de Base e Novas Anotações

---

## 🎯 Objetivo desta Etapa

Realizar um "Deep Dive" (mergulho profundo) nas aulas anteriores para reforçar conceitos que ficaram vagos e atualizar o caderno de estudos com insights práticos obtidos após uma segunda leitura do material oficial da Cisco.

---

## 📖 O que foi Revisado?

Neste período, decidi refazer as aulas principais para garantir que a base de **Cibersegurança** seja inabalável. O foco da revisão foi:

1.  **Fundamentos de Design (Módulo 1):** Relembrando a importância da redundância para a Disponibilidade (CIA).
2.  **Protocolos de Resolução (Módulo 7):** Reforço sobre o funcionamento do **ARP** e como ele é vulnerável a ataques de interceptação.
3.  **Endereçamento Lógico (Módulos 5 e 6):** Prática intensiva de cálculo de sub-redes e lógica binária (ANDing).
4.  **Camada de Transporte (Módulo 9):** Diferenciação clara entre o controle de fluxo do **TCP** e a agilidade do **UDP**.

---

## 🧠 Novas Anotações e Insights

### 🛡️ Visão de Segurança em Redes
Ao rever as aulas antigas com uma mentalidade mais crítica, surgiram novos pontos de atenção:
* **Segmentação:** Não basta criar sub-redes; é preciso garantir que o tráfego entre elas seja filtrado por ACLs no Gateway.
* **O perigo do Broadcast:** Reafirmei que redes com excesso de tráfego de broadcast não são apenas lentas, mas mais fáceis de serem mapeadas por atacantes.
* **Confiabilidade do TCP:** Durante a revisão do Módulo 9, ficou claro que o *Three-way Handshake* é a primeira barreira que um Firewall de estado analisa.

### 🛠️ Melhoria na Prática de CLI
Aproveitei a revisão para fixar comandos que antes eu precisava consultar:
- `ipconfig /displaydns`: Para ver o cache local de nomes.
- `arp -d *`: Para limpar a tabela e forçar um novo aprendizado (essencial em laboratórios).
- `netstat -ano`: Para identificar qual processo (PID) está usando uma porta específica.

---

## 🔢 Tabela de Progresso da Revisão

| Módulo | Assunto Principal | Status da Revisão | Novo Insight |
| :--- | :--- | :--- | :--- |
| **1-4** | Design, Nuvem e Ethernet | ✅ Concluído | Redundância ≠ Backup. |
| **5-7** | IP e ARP | ✅ Concluído | O ARP é o elo mais fraco da LAN. |
| **8-9** | DNS, DHCP e Transporte | ✅ Concluído | DNS é o alvo preferido para Phishing. |

---

## 🔬 Observação Prática (Evolução de Mentalidade)

Refazer as aulas me permitiu conectar os pontos. Agora, quando olho para um endereço IP, não vejo apenas números; vejo uma posição na hierarquia da rede e os possíveis protocolos (TCP/UDP) que estão sendo usados para sustentar as aplicações.

---

## ⚠️ Pontos que exigiram mais atenção

A transição entre o **IPv4** e o **IPv6** (vizinhos do Módulo 8).  
*Ação:* Dediquei um tempo extra para entender como o ICMPv6 substitui o ARP, eliminando broadcasts desnecessários e melhorando a eficiência da rede.

---

## 🔐 Conclusão da Revisão

Estudar Cibersegurança exige uma base de redes impecável. Esta revisão não foi um "atraso", mas sim um fortalecimento necessário. Com os conceitos de transporte (Módulo 9) agora bem frescos, estou pronto para avançar para a configuração prática e segurança de dispositivos.

---

## 🧩 Insight do Dia

> "Estudar redes uma vez te ensina como os dados viajam. Estudar redes duas vezes te ensina por onde os ataques entram."

---

## 📖 Próximo Passo

Retomar o cronograma oficial a partir do **Módulo 10 — A Linha de Comando do Cisco IOS**, aplicando todo o conhecimento de endereçamento e transporte na configuração real de equipamentos.
