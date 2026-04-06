# 📚 Registro de Estudo — Cibersegurança

**Data:** 06/04/2026  
**Tema:** Módulo 15 da Cisco — TCP, UDP e Números de Porta  
**Área:** Camada de Transporte (Layer 4)

---

## 🎯 Objetivo do Estudo

Entender **como os dados realmente viajam** após o roteamento, diferenciando o funcionamento do **TCP** e **UDP**, e como os **números de porta** identificam serviços e conversas entre cliente e servidor.

---

## 📖 Conceitos Fundamentais

- **TCP (Transmission Control Protocol):** Confiável, orientado à conexão, garante entrega e ordem.
- **UDP (User Datagram Protocol):** Rápido, sem confirmação, melhor esforço.
- **Segmentação:** O TCP divide dados grandes em segmentos numerados.
- **Portas:** Identificadores numéricos que apontam qual serviço deve receber os dados.
- **Socket:** Combinação de IP + Porta que identifica uma comunicação.

---

## 🧠 Explicação Técnica

### 🔵 UDP — Velocidade acima de tudo

- Não confirma recebimento
- Não retransmite
- Ideal para **voz, vídeo, streaming, VoIP**
- Perda de pacotes é aceitável, atraso não

### 🟢 TCP — Confiabilidade acima de tudo

1. Estabelece conexão (Three-way handshake)
2. Numera segmentos
3. Aguarda confirmação (ACK)
4. Retransmite apenas o que foi perdido
5. Entrega ordenada ao aplicativo

> TCP controla **fluxo**, **ordem** e **integridade**.  
> UDP entrega e esquece.

---

## 🔢 Números de Porta (Onde mora a inteligência)

Quando um host envia dados, ele não manda só para um IP. Ele manda para:


IP + PORTA


Isso permite que um servidor rode **vários serviços ao mesmo tempo**.

### Classificação das portas (IANA)

| Tipo | Intervalo | Uso |
|-----|-----------|-----|
| **Bem conhecidas** | 0 – 1023 | Serviços padrão (HTTP, FTP, SSH) |
| **Registradas** | 1024 – 49151 | Aplicações específicas |
| **Dinâmicas/Privadas** | 49152 – 65535 | Portas temporárias do cliente |

- Cliente escolhe **porta de origem aleatória**
- Servidor escuta em **porta fixa conhecida**

---

## 💻 Conceitos Operacionais Importantes

- Cada conexão TCP é identificada por:  
  **IP origem + Porta origem + IP destino + Porta destino**
- Múltiplas conexões simultâneas são possíveis graças às portas.
- O servidor usa a porta para saber **qual serviço** deve tratar o pacote.

---

## 🔬 Observação Prática (Muito importante)

Conexões TCP abertas revelam muito sobre o sistema.

Ferramentas como:

- `netstat`
- `ss`
- `lsof -i`

Mostram:
- Portas abertas
- Serviços rodando
- Conexões ativas
- Estado das conexões

Isso é **ouro em reconhecimento de rede**.

---

## 📊 Resultados Observados

- UDP sacrifica confiabilidade para ganhar velocidade.
- TCP sacrifica velocidade para garantir entrega.
- Portas são o que realmente permitem múltiplos serviços em um único IP.

---

## ⚠️ Problemas Encontrados

Entender que **IP sozinho não identifica um serviço**.  
Sem a porta, o pacote chega no host… e fica sem destino.

---

## 🛠️ Solução

Sempre analisar tráfego como:


IP → PORTA → SERVIÇO


Nunca apenas o IP.

---

## 🔐 Relação com Cibersegurança

Aqui começa o pentest de verdade:

- **Port Scanning (Nmap)** enumera portas abertas
- Descoberta de serviços expostos
- Identificação de versões vulneráveis
- Enumeração de superfície de ataque
- Análise de conexões suspeitas

Sem entender portas, você não entende **ataque em rede**.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
|------|-------------|
| **TCP Handshake** | Processo de abertura de conexão confiável |
| **ACK** | Confirmação de recebimento |
| **Socket** | IP + Porta identificando comunicação |
| **Porta de Origem** | Porta temporária escolhida pelo cliente |
| **Porta de Destino** | Porta fixa do serviço no servidor |

---

## 🧩 Insight do Dia

> “O IP leva você até a casa.  
> A porta diz em qual sala você deve bater.”

---

## 📖 Próximo Passo

Estudar **Módulo 16 — Serviços da Camada de Aplicação** para entender o que realmente roda por trás dessas portas.

---

## 📌 Resumo Final

O módulo mostrou que TCP e UDP definem **como** os dados são entregues, enquanto as portas definem **quem** deve recebê-los. Para cibersegurança, isso é a base de varredura, enumeração e identificação de serviços expostos.
