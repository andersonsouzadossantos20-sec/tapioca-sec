# 📚 Registro de Estudo — Cibersegurança

**Data:** 11/04/2026  
**Tema:** Módulo 1 da Cisco — Design de Rede  
**Área:** Arquitetura de Redes e Fundamentos de Infraestrutura

---

## 🎯 Objetivo do Estudo

Compreender os pilares de uma rede confiável e a estrutura do **Modelo de Rede Hierárquica**, essencial para criar ambientes escaláveis, seguros e eficientes.

---

## 📖 Conceitos Fundamentais

- **Redes Confiáveis:** Devem atender a quatro características básicas: Tolerância a Falhas, Escalabilidade, Qualidade de Serviço (QoS) e Segurança.
- **Endereçamento Lógico (IP):** Composto pela porção de rede (identifica o "bairro") e pela porção de host (identifica a "casa").
- **Endereçamento Físico (MAC):** Identidade única e permanente gravada no hardware da placa de rede.
- **Projeto Hierárquico:** Divisão da rede em camadas para facilitar a gestão e reduzir o impacto de falhas.

---

## 🧠 Explicação Técnica

### 🏛️ As 4 Características de uma Rede Confiável
1.  **Tolerância a Falhas:** Capacidade de limitar o impacto de falhas. Utiliza caminhos redundantes para que o tráfego continue fluindo mesmo se um link cair.
2.  **Escalabilidade:** Capacidade de crescer rapidamente para suportar novos usuários e serviços sem comprometer o desempenho atual.
3.  **QoS (Qualidade de Serviço):** Mecanismo de priorização de tráfego. Garante que dados sensíveis ao tempo (Voz e Vídeo) passem à frente de dados menos críticos.
4.  **Segurança:** Proteção da infraestrutura e dos dados, baseada na Tríade CIA (Confidencialidade, Integridade e Disponibilidade).

### 🗼 Modelo de Rede Hierárquica
O projeto de rede profissional é dividido em três camadas:
* **Camada de Acesso:** Ponto de entrada dos dispositivos finais (PCs, APs, Impressoras) na rede.
* **Camada de Distribuição:** Interconecta as redes de acesso, controla o fluxo de dados e aplica políticas de segurança.
* **Camada de Núcleo (Core):** O "backbone" de alta velocidade, responsável pelo transporte massivo de dados entre as diferentes partes da rede.

---

## 🔢 Tabela de Segurança da Informação (Tríade CIA)

| Requisito | Definição no Design de Rede |
| :--- | :--- |
| **Confidencialidade** | Garantir que apenas usuários autorizados acessem os dados. |
| **Integridade** | Garantir que as informações não sejam alteradas durante o trânsito. |
| **Disponibilidade** | Garantir que a rede e os serviços estejam sempre acessíveis. |

---

## 💻 Conceitos Operacionais Importantes

- **Redundância:** É o "Plano B". Ter switches e roteadores extras interconectados para evitar que um único ponto de falha paralise toda a operação.
- **Convergência:** Redes modernas unem voz, vídeo e dados. Por isso, o **QoS** é vital para evitar atrasos (latência) que degradam a comunicação em tempo real.

---

## 🔬 Observação Prática (Foco em Segurança)

O design hierárquico é a base para a **segurança perimetral**:
- Na **Camada de Acesso**, focamos em *Port Security* (quem pode plugar o cabo).
- Na **Camada de Distribuição**, focamos em *VLANs* e *ACLs* (quem pode falar com quem).
- No **Núcleo**, focamos em velocidade e disponibilidade máxima.

---

## ⚠️ Problemas Encontrados

Confundir **Escalabilidade** com **Tolerância a Falhas**.  
*Solução:* Pense que a Escalabilidade olha para o **futuro** (crescimento), enquanto a Tolerância a Falhas olha para o **agora** (sobrevivência a erros).

---

## 🔐 Relação com Cibersegurança

- **Defesa em Profundidade:** A estrutura hierárquica permite isolar problemas. Se um atacante compromete a Camada de Acesso, ele ainda precisa passar pelas políticas da Camada de Distribuição para chegar aos servidores.
- **Disponibilidade:** Redes bem projetadas (Tolerância a Falhas) são naturalmente mais resistentes a ataques de DoS (Negação de Serviço).

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **MAC Address** | Endereço físico único (o "nome" imutável do hardware). |
| **IP Address** | Endereço lógico (a "localização" atual na rede). |
| **QoS** | Priorização de tráfego para garantir performance em serviços críticos. |
| **Hierarquia** | Organização em camadas para reduzir a complexidade. |

---

## 🧩 Insight do Dia

> "Uma rede sem design hierárquico é como uma cidade sem zoneamento: você pode até conseguir andar, mas nunca saberá onde estão as fronteiras de segurança."

---

## 📖 Próximo Passo

Prosseguir para o **Módulo 2 — Nuvem e Virtualização** para entender como essa infraestrutura física é espelhada e expandida em ambientes virtuais.

---

## 📌 Resumo Final

O Módulo 1 ensinou que a confiança de uma rede reside no seu design. Para a Cibersegurança, o modelo hierárquico e a Tríade CIA não são apenas conceitos teóricos, mas as ferramentas práticas para construir perímetros de defesa sólidos e resilientes.
