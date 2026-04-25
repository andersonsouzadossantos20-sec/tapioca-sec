# 📚 Registro de Estudo — Cibersegurança

**Data:** 03/04/2026  
**Tema:** Módulo 10 da Cisco — Formatos e Regras de Endereçamento IPv6  
**Área:** Camada de Rede / Endereçamento de Próxima Geração

---

## 🎯 Objetivo do Estudo

Compreender a necessidade da transição para o IPv6, seu formato hexadecimal de 128 bits e as regras de compressão para tornar esses endereços gigantes mais legíveis.

---

## 📖 Conceitos Fundamentais

- **Esgotamento do IPv4:** O motivo principal da migração. O IPv4 não aguenta mais tanto dispositivo conectado.
- **Estrutura IPv6:** 128 bits divididos em 8 quartetos (hextetos) escritos em hexadecimal.
- **Coexistência:** Como IPv4 e IPv6 vivem juntos através de Pilha Dupla, Tunelamento e Tradução.
- **Regras de Abreviação:** Técnicas para encurtar o endereço sem perder a validade.

---

## 🧠 Explicação Técnica

### 1. Por que IPv6?
O IPv4 só tem 4,3 bilhões de endereços. O IPv6 tem **340 undecilhões**. É endereço que não acaba mais. Além disso, ele já traz melhorias nativas de segurança e autoconfiguração.


### 2. Regras de Compressão (Essencial!)
Escrever um endereço de 128 bits é um pesadelo, por isso usamos duas regras:
* **Regra 1 - Omitir zeros à esquerda:** Você pode remover os zeros que vêm na frente de um hexteto. Ex: `01AB` vira `1AB`.
* **Regra 2 - Dois pontos duplos (::):** Você pode substituir uma sequência contínua de hextetos compostos só por zeros por `::`. 
    * *Atenção:* Só pode usar o `::` **uma única vez** por endereço!

### 3. Técnicas de Migração
* **Pilha Dupla (Dual Stack):** O dispositivo fala as duas línguas ao mesmo tempo.
* **Tunelamento:** O pacote IPv6 viaja "disfarçado" dentro de um pacote IPv4.
* **NAT64:** Traduz o IPv6 para IPv4 para que eles consigam se entender.

---

## 🔧 Tecnologias / Ferramentas Relacionadas

- **Hexadecimal:** A base numérica (0-9 e A-F) usada no IPv6.
- **ICMPv6:** Versão atualizada do ICMP que agora faz o papel do antigo ARP (Neighbor Discovery).
- **IANA:** Organização que gerencia a distribuição desses endereços globalmente.

---

## 💻 Comandos / Sintaxe Importante

*No Kali Linux para testar a conectividade IPv6:*
- `ip -6 addr`: Mostra seus endereços IPv6.
- `ping6 google.com`: Testa se a rede está roteando IPv6 corretamente.

---

## 🔬 Experimento / Prática

Pratiquei a compressão de endereços. 
Exemplo: `2001:0db8:0000:1111:0000:0000:0000:0200`
1. Omitindo zeros: `2001:db8:0:1111:0:0:0:200`
2. Usando `::`: `2001:db8:0:1111::200`

---

## 📊 Resultados Observados

- O IPv6 elimina a necessidade de NAT complexo em muitos casos, permitindo conectividade ponta a ponta real.
- A leitura hexadecimal assusta no começo, mas as regras de compressão facilitam muito a vida do administrador.

---

## ⚠️ Problemas Encontrados

Tentar usar o `::` duas vezes no mesmo endereço. Isso invalida o IP porque o roteador não saberia quantos zeros colocar em cada lugar.

---

## 🛠️ Solução

Sempre usar o `::` na maior sequência de zeros possível. Se as sequências forem iguais, use na primeira.

---

## 🔐 Relação com Cibersegurança

- **Varredura de Rede (Recon):** No IPv4, um hacker varre uma rede em minutos. No IPv6, o espaço de endereçamento é tão vasto que varrer por "força bruta" é praticamente impossível.
- **IPSec:** O suporte ao protocolo de segurança IPSec é mandatório/nativo no design do IPv6, tornando a comunicação mais segura por padrão.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
|------|-------------|
| **Hexteto** | Cada um dos 8 blocos de 16 bits do IPv6. |
| **Heads-up** | O cabeçalho IPv6 é mais simples que o do IPv4, o que torna o roteamento mais rápido. |
| **Link-Local** | Endereço que começa com `fe80::`, usado para comunicação apenas dentro da rede local. |

---

## 🧩 Insight do Dia

IPv6 não é apenas "mais endereços", é uma internet mais inteligente. Aprender a dominar a abreviação é o primeiro passo para não se perder na próxima geração das redes.

---

## 📖 Próximo Passo

Estudar **Módulo 11 — Endereçamento dinâmico com DHCP** (Como o IP chega sozinho na máquina).

---

## 📌 Resumo Final

O Módulo 10 matou o medo do IPv6. Entendi que a transição é necessária e que as regras de compressão são nossas melhores amigas para lidar com esse novo mundo de 128 bits.
