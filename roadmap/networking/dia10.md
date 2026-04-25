# 📚 Registro de Estudo — Cibersegurança

**Data:** 30/03/2026  
**Tema:** Módulo 6 da Cisco — Mídia de Rede  
**Área:** Infraestrutura / Camada Física (OSI 1)

---

## 🎯 Objetivo do Estudo

Entender os meios físicos que transportam os dados. O foco é conhecer as características, vantagens e limitações dos cabos de cobre, fibra óptica e conexões sem fio.

---

## 📖 Conceitos Fundamentais

- **Mídia de Rede:** O caminho físico por onde os bits viajam.
- **Largura de Banda (Bandwidth):** A capacidade máxima de transmissão.
- **Throughput:** A velocidade real (o que sobra depois das perdas).
- **Interferência (EMI/RFI):** Ruídos externos que bagunçam o sinal no cobre.

---

## 🧠 Explicação Técnica

Os dados são transmitidos como **bits**, mas o meio físico não entende "0 e 1". Ele entende sinais:
1. **Cabo de Cobre (UTP/STP):** Transmite impulsos elétricos. É o mais comum em LANs, mas sofre com interferência de motores e lâmpadas.
2. **Fibra Óptica:** Transmite pulsos de luz. É imune a interferências, alcança distâncias enormes e é muito rápida, mas o custo e a instalação são mais complexos.
3. **Wireless (Sem Fio):** Transmite ondas de rádio (eletromagnéticas). Oferece mobilidade, mas o sinal pode ser bloqueado por paredes ou sofrer interferência de outros aparelhos.

---

## 🔧 Tecnologias / Ferramentas Relacionadas

- **Cabo UTP (Unshielded Twisted Pair):** O par trançado que usamos no dia a dia.
- **Fibra Monomodo vs. Multimodo:** Laser para longas distâncias vs. LED para curtas.
- **Padrão Wi-Fi (802.11):** A regra para conexões wireless.

---

## 💻 Comandos / Sintaxe Importante

*Conceito de cores de crimpagem (padrões TIA/EIA):*
- **T568B:** É o padrão mais usado hoje para fazer as pontas dos cabos RJ-45.

---

## 🔬 Experimento / Prática

Aprendi a diferenciar por que usamos fibra para conectar prédios (distância e isolamento) e cobre para conectar computadores dentro da sala (custo e flexibilidade).

---

## 📊 Resultados Observados

- **Cobre:** Barato, mas limitado a 100 metros e sensível a ruído.
- **Fibra:** Caro, mas imune a ruído e chega a quilômetros.
- **Wireless:** Prático, mas a segurança e a velocidade variam muito conforme o ambiente.

---

## ⚠️ Problemas Encontrados

Entender a diferença entre **Atenuação** (sinal ficando fraco com a distância) e **Crosstalk** (fios "conversando" um com o outro e gerando erro).

---

## 🛠️ Solução

Para evitar o Crosstalk, os cabos de rede têm os fios trançados em pares (por isso o nome "par trançado"), o que cancela o ruído magnético.

---

## 🔐 Relação com Cibersegurança

A segurança física é a primeira linha de defesa. 
- Um cabo de cobre pode sofrer **Eavesdropping** (alguém interceptar o sinal magnético sem nem tocar no fio). 
- Redes Wi-Fi precisam de criptografia forte (WPA3) porque o sinal está "voando" por aí e qualquer um pode tentar capturar. 
- Se a mídia física for cortada ou sofrer interferência proposital (Jamming), a rede para.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
|------|-------------|
| **RJ-45** | O conector padrão do cabo de rede. |
| **STP** | Cabo de cobre blindado (usado onde tem muita interferência). |
| **Latência** | O tempo de atraso para o dado percorrer a mídia. |

---

## 🧩 Insight do Dia

Não existe "nuvem" sem cabos. No final das contas, toda a internet depende de fios de cobre e vidro cruzando o mundo.

---

## 📖 Próximo Passo

Estudar o **Módulo 7 — A Camada de Acesso** (como os dados entram no cabo).

---

## 📌 Resumo Final

O Módulo 6 mostrou que a escolha da mídia certa define se a rede será estável ou um pesadelo de quedas e lentidão. Para cibersegurança, proteger o acesso físico a esses cabos é tão importante quanto ter uma senha forte.
