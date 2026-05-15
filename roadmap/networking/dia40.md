# 📚 Registro de Estudo — Cibersegurança

**Data:** 15/05/2026  
**Tema:** Módulo 5 da Cisco — Comunicação de Rede Sem Fio (Wireless)  
**Área:** Segurança de WLAN e Protocolos de Transmissão

---

## 🎯 Objetivo do Estudo

Compreender o funcionamento das redes sem fio (WLAN), identificar as ameaças específicas à transmissão de dados via rádio e analisar os protocolos de segurança (WPA2/WPA3) necessários para proteger redes domésticas e corporativas.

---

## 📖 Conceitos Fundamentais

- **Padrão 802.11:** Define como os dispositivos se conectam via Wi-Fi. Utiliza um formato de quadro semelhante ao Ethernet, mas com campos adicionais para gestão do meio sem fio.
- **CSMA/CA:** Ao contrário do cabo, o Wi-Fi não consegue detetar colisões perfeitamente, por isso usa a *Prevenção* de Colisões para determinar quando enviar dados.
- **Topologia WLAN:** Composta por Pontos de Acesso (AP) e Clientes. Em redes maiores, utiliza-se um **WLC** (Wireless LAN Controller) para gerir múltiplos APs de forma centralizada.

---

## 🧠 Explicação Técnica

### 📶 Processo de Ligação
Para se ligar a uma rede, um dispositivo passa por três estágios:
1.  **Descoberta:** Procura por um AP (via *Beacon frames*).
2.  **Autenticação:** O dispositivo prova a sua identidade à rede.
3.  **Associação:** O dispositivo ganha permissão para transmitir dados através do AP.

### 🏴‍☠️ Ameaças de WLAN
* **Interceção de Dados:** Como o sinal está no ar, qualquer pessoa com uma antena pode capturar pacotes se não houver criptografia.
* **Pontos de Acesso "Gémeo Mau" (Evil Twin):** Um atacante configura um AP com o mesmo SSID da rede legítima para capturar credenciais de utilizadores que se liguem a ele por engano.
* **AP Não Autorizado (Rogue AP):** Um funcionário instala um router barato na rede da empresa, criando uma porta aberta sem segurança para atacantes.
* **Ataques DoS:** Podem ser causados por dispositivos mal configurados ou por interferências intencionais (Jamming) para derrubar a comunicação.

---

## 🔬 Observação Prática (Foco em Segurança)

A segurança baseia-se em dois pilares fundamentais:
- **Camuflagem de SSID e Filtragem MAC:** São medidas básicas (e fracas) que escondem o nome da rede ou restringem dispositivos. Atacantes experientes contornam isto facilmente.
- **Protocolos de Criptografia:**
    - **WEP:** Antigo e vulnerável (nunca usar).
    - **WPA2:** Usa AES para criptografia forte. É o padrão atual mais comum.
    - **WPA3:** O mais recente e seguro, com proteção reforçada contra ataques de força bruta de dicionário.

---

## ⚠️ Problemas Encontrados

Dificuldade em distinguir entre um **Ataque MiTM** tradicional e um **Evil Twin** em redes sem fio.  
*Insight:* No Evil Twin, o atacante posiciona-se fisicamente entre as entidades legítimas usando hardware de rádio para clonar a rede, capturando o tráfego antes mesmo de este chegar ao router real.

---

## 🔐 Relação com Cibersegurança

- **Modelo AAA:** Em ambientes corporativos, usa-se um servidor **RADIUS** para Autenticação, Autorização e Contabilidade, garantindo que cada utilizador tenha credenciais únicas e rastreáveis.
- **Gestão Centralizada (WLC):** Permite detetar automaticamente "Rogue APs" e aplicar políticas de segurança em todos os pontos da empresa simultaneamente, reduzindo a superfície de ataque.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **SSID** | O nome da rede sem fio. |
| **AES** | Algoritmo de criptografia de alta segurança usado no WPA2/WPA3. |
| **TKIP** | Protocolo de segurança antigo usado no WPA original (atualmente desencorajado). |
| **Beacon** | Quadros enviados pelo AP para anunciar a presença da rede. |

---

## 🧩 Insight do Dia

> "Em redes cabeadas, a segurança começa na porta da sala. Em redes sem fio, a segurança começa no estacionamento, pois o sinal não respeita paredes."

---

## 📖 Próximo Passo

Avançar para o **Módulo 6 — Infraestrutura de Segurança de Rede** para ver como os firewalls e outros dispositivos protegem a borda da rede de todas estas ameaças combinadas.

---

## 📌 Resumo Final

O Módulo 5 mostrou que a conveniência do Wi-Fi traz riscos significativos. A transição do WPA2 para o WPA3 e a implementação de servidores AAA são passos vitais para transformar um meio de transmissão aberto e "caótico" num ambiente controlado e seguro para dados corporativos sensíveis.
