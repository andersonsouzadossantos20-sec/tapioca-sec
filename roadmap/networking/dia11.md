# 📚 Registro de Estudo — Cibersegurança

**Data:** 01/04/2026  
**Tema:** Módulo 7 da Cisco — A Camada de Acesso  
**Área:** Redes / Camada de Enlace (Layer 2)

---

## 🎯 Objetivo do Estudo

Entender como funciona a comunicação em redes Ethernet, focando no processo de **encapsulamento** e no papel fundamental da **Camada de Acesso** para organizar o tráfego de dados.

---

## 📖 Conceitos Fundamentais

- **Quadro Ethernet (Frame):** A unidade de dados da Camada 2.
- **Endereço MAC:** O endereço físico, "queimado" na placa de rede.
- **Encapsulamento Ethernet:** O processo de colocar o pacote IP dentro de um quadro com as informações de destino físico.
- **Camada de Acesso:** A interface entre o software da rede e o hardware físico.

---

## 🧠 Explicação Técnica

Neste módulo, o foco é o **Protocolo Ethernet**. Ele é o padrão mais usado no mundo para redes locais (LAN). 
A Camada de Acesso tem duas funções principais:
1.  **Encapsulamento de dados:** Pega o pacote que veio da Camada de Rede (IP) e adiciona um cabeçalho e um trailer, criando o **Quadro (Frame)**.
2.  **Controle de Acesso ao Meio:** Gerencia como os bits são colocados no cabo para evitar colisões e garantir que a mensagem chegue ao vizinho certo.


---

## 🔧 Tecnologias / Ferramentas Relacionadas

- **Switches de Rede:** Os dispositivos que operam nesta camada e "leem" os endereços MAC.
- **Placas de Rede (NIC):** Onde o endereço MAC reside.
- **Protocolo ARP:** O "tradutor" que descobre qual MAC pertence a qual IP.

---

## 💻 Comandos / Sintaxe Importante

*No terminal do Linux (Kali), é essencial saber verificar o endereço físico:*
- `ip link show` ou `ifconfig`: Para visualizar os endereços MAC das interfaces.

---

## 🔬 Experimento / Prática

Entender a anatomia de um quadro Ethernet:
- **Preâmbulo:** O aviso de "lá vai dado!".
- **Endereço MAC de Destino e Origem.**
- **Tipo/Tamanho:** Indica qual protocolo está lá dentro (geralmente IPv4 ou IPv6).
- **FCS (Frame Check Sequence):** O verificador de erros para garantir que o quadro não chegou "amassado".

---

## 📊 Resultados Observados

Compreendi que, enquanto o endereço IP serve para localizar dispositivos em redes diferentes (global), o **Endereço MAC** é quem faz a entrega final dentro da mesma rede local. Se o quadro chegar com erro no FCS, ele é simplesmente descartado.

---

## ⚠️ Problemas Encontrados

A confusão entre o que é um "Pacote" (Camada 3) e o que é um "Quadro" (Camada 2).

---

## 🛠️ Solução

Mentalizei a regra: O **Pacote (IP)** é a carta. O **Quadro (Ethernet)** é o envelope que o carteiro local usa para entregar na casa certa.

---

## 🔐 Relação com Cibersegurança

A Camada de Acesso é um prato cheio para ataques!
- **MAC Flooding:** Inundar o switch para ele agir como um hub burro e vazar dados.
- **ARP Spoofing:** Mentir sobre quem é o dono de um IP para interceptar o tráfego (Man-in-the-Middle).
- Entender o quadro Ethernet é o primeiro passo para conseguir ler logs no **Wireshark** de forma profissional.

---

## 📚 Termos Importantes Aprendidos

| Termo | O que eu entendi |
|------|-------------|
| **Frame (Quadro)** | O pacote "embrulhado" para viajar pelo cabo. |
| **MAC Address** | Endereço físico único de 48 bits (Hexadecimal). |
| **NIC** | Network Interface Card (Placa de Rede). |

---

## 🧩 Insight do Dia

O endereço IP te leva até a porta do prédio, mas é o endereço MAC que te leva até o apartamento certo.

---

## 📖 Próximo Passo

Estudar **modulo 08: protocolo de internet(IP)**

---

## 📌 Resumo Final

O Módulo 7 fecha o ciclo da entrega local. Agora eu sei que a rede não joga dados ao vento; tudo é meticulosamente empacotado em Quadros Ethernet para que o Switch saiba exatamente para qual porta enviar a informação.
