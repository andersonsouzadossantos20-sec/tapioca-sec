# 📚 Registro de Estudo — Cibersegurança

**Data:** 13/04/2026  
**Tema:** Módulo 5 da Cisco — Camada de Rede  
**Área:** Roteamento e Endereçamento Lógico (Camada 3)

---

## 🎯 Objetivo do Estudo

Compreender como a **Camada de Rede** (Layer 3) permite a comunicação entre diferentes redes através do endereçamento IP e do roteamento, garantindo que os dados cheguem ao destino correto além da rede local.

---

## 📖 Conceitos Fundamentais

- **Camada de Rede:** Responsável pela troca de seções de dados (pacotes) entre hosts em redes diferentes.
- **Endereçamento IP:** Fornece um identificador lógico exclusivo para cada dispositivo na rede.
- **Encapsulamento:** Processo onde a Camada de Rede recebe a PDU da Camada de Transporte e adiciona informações de cabeçalho IP.
- **Roteamento:** O processo de selecionar o melhor caminho para enviar pacotes em direção ao host de destino.

---

## 🧠 Explicação Técnica

### 📦 Características do Protocolo IP
O IP (Internet Protocol) possui três características principais que o tornam eficiente:
1.  **Sem Conexão (Connectionless):** Não estabelece uma conexão prévia com o destino antes de enviar o pacote.
2.  **Melhor Esforço (Best Effort):** O IP não garante a entrega; ele não tem mecanismos para recuperar pacotes perdidos ou corrompidos.
3.  **Independente de Meio:** Funciona independentemente do tipo de cabo ou conexão física (fibra, cobre, Wi-Fi).



### 🛣️ O Papel do Roteador
Roteadores são os dispositivos que operam na Camada 3. Eles mantêm uma **Tabela de Roteamento** para decidir para onde encaminhar os pacotes com base no endereço IP de destino.
* **Gateway Padrão (Default Gateway):** É o roteador que conecta a rede local à internet ou a outras redes remotas.
* **Desencapsulamento:** Quando o pacote chega ao destino, o host remove o cabeçalho IP para processar os dados nas camadas superiores.

---

## 🔢 IPv4 vs. IPv6

| Característica | IPv4 | IPv6 |
| :--- | :--- | :--- |
| **Comprimento** | 32 bits | 128 bits |
| **Formato** | Decimal com pontos | Hexadecimal |
| **Disponibilidade** | Esgotado/Limitado | Praticamente ilimitado |
| **Segurança** | Adicional (IPsec opcional) | Nativa (IPsec integrado) |

---

## 💻 Conceitos Operacionais Importantes

- **PDU (Unidade de Dados de Protocolo):** Na Camada 3, a PDU é chamada de **Pacote**.
- **Segmentação de Rede:** Dividir uma rede grande em sub-redes menores para melhorar o desempenho e a segurança.
- **Encaminhamento:** Se o destino não estiver na rede local, o host envia o pacote para o seu *Gateway Padrão*.

---

## 🔬 Observação Prática (Foco em Segurança)

Para um profissional de segurança, a Camada 3 é onde aplicamos:
- **ACLs (Listas de Controle de Acesso):** Filtros baseados em endereços IP para permitir ou bloquear tráfego específico.
- **Firewalls de Camada de Rede:** Analisam o cabeçalho IP para detectar tentativas de invasão ou tráfego de redes suspeitas.
- **Prevenção de IP Spoofing:** Técnicas para evitar que atacantes falsifiquem o endereço IP de origem para ganhar acesso não autorizado.

---

## ⚠️ Problemas Encontrados

Confundir o endereço de rede com o endereço de host.  
*Solução:* O endereço IP sempre contém duas partes; a máscara de sub-rede é o que define onde termina a rede e onde começa o host.

---

## 🔐 Relação com Cibersegurança

- **Visibilidade:** O endereço IP de origem é a primeira pista em uma investigação de incidente.
- **Integridade do Cabeçalho:** Se o campo TTL (Time to Live) de um pacote for manipulado, ele pode indicar técnicas de mapeamento de rede por hackers.
- **Isolamento:** Configurar corretamente o roteamento garante que redes sensíveis (como RH ou Financeiro) fiquem isoladas do restante da empresa.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **Encapsulamento** | Adicionar informações de roteamento aos dados. |
| **Gateway** | A "porta de saída" de uma rede local. |
| **TTL (Time to Live)** | Limita o tempo de vida de um pacote para evitar loops infinitos. |
| **Subnet Mask** | Define qual parte do IP pertence à rede e qual ao dispositivo. |

---

## 🧩 Insight do Dia

> "Se o endereço MAC é o seu CPF (quem você é), o endereço IP é o seu CEP (onde você está). Sem o IP, os correios da internet nunca saberiam em qual cidade entregar o seu pacote."

---

## 📖 Próximo Passo

Avançar para o **Módulo 6 — Estrutura do Endereço IPv4** para detalhar como as sub-redes e as classes de endereçamento funcionam na prática.

---

## 📌 Resumo Final

O Módulo 5 ensinou que o IP é o protocolo "carregador" da internet. Para a cibersegurança, entender como o roteamento funciona é fundamental para criar perímetros de defesa e entender como os dados atravessam as fronteiras digitais do mundo todo.
