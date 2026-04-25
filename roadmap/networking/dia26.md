# 📚 Registro de Estudo — Cibersegurança

**Data:** 13/04/2026  
**Tema:** Módulo 4 da Cisco — Comutação Ethernet  
**Área:** Camada de Enlace de Dados e Infraestrutura de Rede Local (LAN)

---

## 🎯 Objetivo do Estudo

Compreender o funcionamento do protocolo **Ethernet**, a estrutura de seus quadros, o endereçamento físico (**MAC**) e como os switches operam na Camada 2 para encaminhar dados de forma eficiente.

---

## 📖 Conceitos Fundamentais

- **Ethernet:** Principal tecnologia de rede local com fio, operando nas Camadas 1 (Física) e 2 (Enlace) do modelo OSI.
- **Quadro (Frame) Ethernet:** A unidade de dados da Camada 2. Ele encapsula o pacote da Camada 3 e adiciona endereços MAC de origem e destino.
- **Endereço MAC:** Endereço binário de 48 bits, expresso em 12 valores hexadecimais, usado para identificar dispositivos de forma exclusiva em uma rede Ethernet.
- **Tabela de Endereços MAC (Tabela CAM):** Banco de dados interno do switch que mapeia endereços MAC às portas físicas correspondentes.

---

## 🧠 Explicação Técnica

### 📦 Estrutura e Subcamadas Ethernet
O Ethernet é definido pelos padrões IEEE 802.2 e 802.3 e divide-se em duas subcamadas:
* **Subcamada LLC (802.2):** Comunica-se com o software de rede nas camadas superiores e identifica qual protocolo da Camada 3 está sendo usado.
* **Subcamada MAC (802.3):** Implementada em hardware (NIC), é responsável pelo encapsulamento de dados, controle de acesso ao meio e detecção de erros.


### 🔌 Operação do Switch
Diferente de um hub, o switch toma decisões inteligentes de encaminhamento:
1. **Aprendizado:** O switch examina o MAC de origem de cada quadro recebido e o registra em sua tabela junto com a porta de entrada.
2. **Encaminhamento:** Se o MAC de destino estiver na tabela, o switch envia o quadro apenas para a porta específica.
3. **Inundação (Flooding):** Se o MAC de destino for desconhecido (Unicast desconhecido) ou um Broadcast, o switch envia o quadro para todas as portas, exceto a de origem.

---

## 🔢 Tipos de Transmissão Ethernet

| Tipo | Endereço MAC de Destino | Comportamento do Switch |
| :--- | :--- | :--- |
| **Unicast** | MAC exclusivo do dispositivo | Envia apenas para a porta do destinatário. |
| **Broadcast** | `FF-FF-FF-FF-FF-FF` | Inunda todas as portas ativas (exceto a de entrada). |
| **Multicast** | `01-00-5E` (IPv4) ou `33-33` (IPv6) | Inunda as portas, a menos que esteja configurado para filtragem específica. |

---

## 💻 Conceitos Operacionais Importantes

- **Full-Duplex:** Switches modernos permitem que os dispositivos enviem e recebam dados simultaneamente, eliminando colisões.
- **Tamanho do Quadro:** O tamanho mínimo é de 64 bytes e o máximo é de 1518 bytes. Quadros fora desses limites são descartados.
- **Encapsulamento:** Inclui preâmbulo, delimitador, endereços MAC, tipo/comprimento, dados e a sequência de verificação de quadro (FCS) para detecção de erros.

---

## 🔬 Observação Prática (Foco em Segurança)

Para um analista de cibersegurança, o Módulo 4 destaca pontos críticos:
- **MAC Spoofing:** Atacantes podem falsificar endereços MAC para enganar a tabela do switch e interceptar dados.
- **Segurança de Porta (Port Security):** É vital configurar switches para aceitarem apenas MACs autorizados, evitando conexões de dispositivos maliciosos.
- **Análise de Broadcast:** Excesso de tráfego de broadcast pode indicar um ataque de negação de serviço (DoS) ou um loop na rede.

---

## ⚠️ Problemas Encontrados

Confundir o papel do **Switch** com o do **Roteador**.  
*Solução:* Lembre-se que o switch olha para o **Endereço MAC** (Camada 2) para mover dados dentro da mesma rede local, enquanto o roteador olha para o **IP** (Camada 3) para mover dados entre redes diferentes.

---

## 🔐 Relação com Cibersegurança

- **Isolamento de Tráfego:** Switches aumentam a segurança ao enviar dados unicast apenas para o destinatário correto, dificultando a "escuta" de tráfego (sniffing) por outros usuários na mesma rede.
- **Monitoramento:** Ferramentas como o Wireshark capturam quadros Ethernet. Entender o campo **FCS** ajuda a identificar se os dados foram corrompidos ou alterados durante o percurso.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **FCS (Frame Check Sequence)** | Campo usado para verificar se o quadro chegou sem erros de bit. |
| **Tabela CAM** | Outro nome para a Tabela de Endereços MAC do switch. |
| **IEEE 802.3** | O padrão oficial que define as redes Ethernet com fio. |
| **NIC (Placa de Rede)** | Onde o endereço MAC está permanentemente gravado. |

---

## 🧩 Insight do Dia

> "O switch é o 'guarda de trânsito' da rede local. Ele aprende quem é quem apenas observando de onde vêm os dados, garantindo que a conversa permaneça privada entre os envolvidos sempre que possível."

---

## 📖 Próximo Passo

Prosseguir para o **Módulo 5 — Camada de Rede** para entender como os pacotes são roteados entre diferentes redes usando o protocolo IP.

---

## 📌 Resumo Final

O Módulo 4 detalhou a mecânica da entrega de dados local. Para a Cibersegurança, entender como o switch gerencia o tráfego e como os endereços MAC são estruturados é o primeiro passo para garantir a integridade e a confidencialidade das comunicações dentro do perímetro organizacional.
