# 📚 Registro de Estudo — Cibersegurança

**Data:** 01/04/2026  
**Tema:** Módulo 8 da Cisco — Protocolo de Internet (IP)  
**Área:** Camada de Rede (OSI Layer 3)

---

## 🎯 Objetivo do Estudo

Entender como o IPv4 funciona para identificar dispositivos de forma única e permitir que os dados viajem por diferentes redes até chegar ao destino final.

---

## 📖 Conceitos Fundamentais

- **Endereço IPv4:** O RG digital do dispositivo na rede.
- **Hierarquia do IP:** Dividido em parte de **Rede** e parte de **Host**.
- **Máscara de Sub-rede:** O que define onde termina a rede e começa o host.
- **Comunicação Remota:** Como o IP permite que você fale com um servidor do outro lado do mundo.

---

## 🧠 Explicação Técnica

O IPv4 é um endereço lógico de **32 bits**, escrito em formato decimal (ex: `192.168.10.5`). Ele é hierárquico:
1. **Porção de Rede:** Identifica em qual "bairro" (rede) o dispositivo está.
2. **Porção de Host:** Identifica o dispositivo específico dentro daquele "bairro".

Os roteadores amam o IP porque eles não precisam saber onde cada PC do mundo está; eles só precisam saber como chegar na **rede** de destino. É igual ao sistema de correios: o carteiro da central só olha a cidade e o CEP, não o seu nome.


---

## 🔧 Tecnologias / Ferramentas Relacionadas

- **IPv4:** O padrão atual (mas que está acabando).
- **Roteadores:** Os "maestros" que leem o endereço IP para decidir o melhor caminho.
- **NIC (Placa de Rede):** Onde o endereço IP é configurado.

---

## 💻 Comandos / Sintaxe Importante

*Essenciais para o dia a dia no Kali ou Windows:*
- `ip address` ou `ifconfig`: Ver seu IP no Linux.
- `ipconfig`: Ver seu IP no Windows.
- `ping <ip>`: Testar se o destino está alcançável na Camada 3.

---

## 🔬 Experimento / Prática

Análise de endereçamento: Entendi que se dois PCs têm a mesma porção de rede, eles se falam direto. Se as redes forem diferentes, precisamos de um roteador (Gateway) para mediar a conversa.

---

## 📊 Resultados Observados

- O IP é essencial para a **escalabilidade** da internet.
- Sem o endereçamento hierárquico, os roteadores travariam tentando processar bilhões de endereços individuais.

---

## ⚠️ Problemas Encontrados

Confundir o endereço IP (Lógico/Mutável) com o endereço MAC (Físico/Fixo).

---

## 🛠️ Solução

Mentalizei: O **MAC** é quem você é (seu nome). O **IP** é onde você está sentado agora (seu endereço). Se você mudar de mesa, seu nome continua o mesmo, mas seu endereço muda.

---

## 🔐 Relação com Cibersegurança

Na segurança, o IP é a base de tudo:
- **Firewalls:** Bloqueiam ou liberam tráfego com base no IP de origem/destino.
- **IP Spoofing:** Ataque onde o hacker finge ter um IP confiável para enganar a rede.
- **Scanner de Rede (Nmap):** Usado para descobrir IPs ativos e portas abertas em um alvo.

---

## 📚 Termos Importantes Aprendidos

| Termo | O que eu entendi |
|------|-------------|
| **Octeto** | Cada uma das 4 partes do IP (8 bits cada). |
| **Gateway Padrão** | O roteador que leva seus dados para fora da sua rede local. |
| **Host** | Qualquer dispositivo com um IP na rede (PC, Celular, IoT). |

---

## 🧩 Insight do Dia

O endereço IP é a peça que conecta o mundo. Aprender a ler um IP e sua máscara é como aprender a ler as coordenadas de um mapa de guerra: sem isso, você está cego.

---

## 📖 Próximo Passo

Estudar **Módulo 9 — IPv4 e Segmentação de Rede** (Subnetting).

---

## 📌 Resumo Final

O Módulo 8 deu o poder de entender como a localização lógica funciona. Agora sei que um pacote IP tem "pernas" para atravessar o mundo, desde que os roteadores saibam ler a porção de rede no cabeçalho dele.
