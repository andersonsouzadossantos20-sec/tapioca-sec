# 📚 Registro de Estudo — Cibersegurança

**Data:** 06/04/2026  
**Tema:** Módulo 14 da Cisco — Roteamento entre Redes  
**Área:** Camada de Rede / Encaminhamento de Pacotes (Layer 3)

---

## 🎯 Objetivo do Estudo

Compreender **por que o roteamento é necessário**, como os **roteadores tomam decisões** usando a **tabela de roteamento** e como a criação de **múltiplas LANs** impacta desempenho, organização e segurança da rede.

---

## 📖 Conceitos Fundamentais

- **Roteamento:** Processo de encaminhar pacotes entre redes diferentes com base no endereço IP de destino.
- **Tabela de Roteamento:** Lista de redes conhecidas e o melhor caminho para alcançá-las.
- **Gateway Padrão:** Endereço do roteador usado quando o destino não está na rede local.
- **Domínio de Broadcast:** Área onde um broadcast se propaga. Roteadores **quebram** esse domínio.
- **LAN (Local Area Network):** Rede local sob o mesmo controle administrativo.

---

## 🧠 Explicação Técnica

Quando dois hosts estão **na mesma rede**, a comunicação ocorre direto via ARP + MAC.

Quando estão **em redes diferentes**, muda tudo:

1. O host percebe que o IP de destino **não pertence à sua rede**.
2. Ele envia o pacote para o **Gateway Padrão** (roteador).
3. O roteador remove o quadro, analisa o **IP de destino**.
4. Consulta a **Tabela de Roteamento** para decidir **para onde encaminhar**.
5. Reencapsula o pacote em um novo quadro e envia pela interface correta.

> Switch decide pelo **MAC (Camada 2)**.  
> Roteador decide pelo **IP (Camada 3)**.

---

## 🗺️ A Tabela de Roteamento

A tabela contém:

- Redes diretamente conectadas
- Rotas aprendidas dinamicamente
- Rotas configuradas manualmente (estáticas)
- Interface de saída para cada rede

O roteador pode aprender rotas de duas formas:

- **Dinamicamente:** Por protocolos de roteamento
- **Estática:** Inserida manualmente pelo administrador

---

## 🧩 Por que dividir redes? (Criando múltiplas LANs)

Dividir uma rede grande em várias LANs permite:

- **Conter broadcasts** (menos tráfego desnecessário)
- **Aumentar a segurança** (separar grupos de usuários)
- **Organização lógica** (departamentos, setores)
- **Separação física** (locais geográficos diferentes)

Mas isso **obriga** o uso de roteamento.

---

## 💻 Conceitos Operacionais Importantes

- Cada interface do roteador pertence a **uma rede diferente**.
- Hosts usam o **Gateway Padrão** para falar com redes externas.
- O roteador usa **ARP** para descobrir o MAC do próximo salto.
- Se não existir rota na tabela → o pacote é descartado.

---

## 🔬 Experimento Mental (Essencial para Pentest)

Se um host não consegue acessar outra rede:

- O problema **não** está no ARP.
- O problema **não** está no cabo.
- O problema quase sempre está na **tabela de roteamento** ou no **gateway configurado errado**.

---

## 📊 Resultados Observados

- Roteadores **reduzem broadcasts** drasticamente.
- Introduzem **latência** por causa do processamento do pacote.
- Aumentam a **complexidade**, mas permitem **controle total** do tráfego.

---

## ⚠️ Problemas Encontrados

Entender que, ao separar redes, você melhora organização e segurança, **mas cria dependência total do roteador** para qualquer comunicação.

---

## 🛠️ Solução

Sempre validar:

- IP do host
- Máscara de rede
- Gateway padrão
- Presença da rota na tabela do roteador

---

## 🔐 Relação com Cibersegurança

Aqui nasce muita coisa importante para pentest:

- **VLAN Hopping**
- **Pivoting entre redes**
- **Enumeração de rotas internas**
- **Descoberta de topologia pela tabela de roteamento**
- **Ataques a gateways mal configurados**

Entender roteamento é entender **como atravessar redes internas** durante um teste de invasão.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
|------|-------------|
| **Roteamento** | Encaminhar pacotes entre redes diferentes |
| **Gateway Padrão** | Roteador usado para sair da rede local |
| **Tabela de Roteamento** | Mapa de caminhos para outras redes |
| **Domínio de Broadcast** | Limite onde broadcasts se propagam |
| **Interface de Saída** | Porta do roteador usada para enviar o pacote |

---

## 🧩 Insight do Dia

> “Quando você divide a rede, você ganha controle.  
> Mas todo controle passa a depender do roteador.”

---

## 📖 Próximo Passo

Estudar **Módulo 15 — TCP e UDP** para entender como os dados trafegam após o roteamento.

---

## 📌 Resumo Final

O módulo mostrou que redes modernas só funcionam porque os roteadores tomam decisões baseadas em IP usando a tabela de roteamento. Dividir redes melhora desempenho e segurança, mas torna o roteador o ponto central de toda comunicação entre LANs.
