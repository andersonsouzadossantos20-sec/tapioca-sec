# 📚 Registro de Estudo — Cibersegurança

**Data:** 04/04/2026  
**Tema:** Módulo 11 da Cisco — Endereçamento Dinâmico com DHCP  
**Área:** Camada de Rede / Serviços de Infraestrutura

---

## 🎯 Objetivo do Estudo

Entender a diferença entre configurar um IP na mão (estático) e deixar o sistema fazer isso sozinho (dinâmico), além de dominar o processo de funcionamento do protocolo DHCPv4.

---

## 📖 Conceitos Fundamentais

- **Endereçamento Estático:** Configuração manual pelo administrador. Dá controle total, mas é demorado e gera erros de digitação.
- **Endereçamento Dinâmico (DHCP):** Atribuição automática de IPs. Reduz a carga de suporte e elimina erros de entrada.
- **Aluguel (Lease):** O IP não é do host para sempre; ele é "alugado" por um período determinado.
- **Pool de Endereços:** O intervalo de IPs que o servidor tem disponível para distribuir.

---

## 🧠 Explicação Técnica

### Estático vs. Dinâmico
No **Estático**, você precisa manter uma lista precisa de quem usa qual IP para não dar conflito. No **Dinâmico**, o protocolo DHCP gerencia isso. Quando um dispositivo entra na rede (tipo seu notebook no Wi-Fi), ele grita por um servidor DHCP para receber as configurações.

### O Processo DHCP (DORA)
Embora o resumo foque na configuração, o processo ocorre assim:
1. **Discover:** O cliente envia um broadcast procurando um servidor.
2. **Offer:** O servidor responde oferecendo um IP.
3. **Request:** O cliente pede para usar aquele IP específico.
4. **Acknowledgment (ACK):** O servidor confirma e "aluga" o endereço.


---

## 🔧 Tecnologias / Ferramentas Relacionadas

- **Servidor DHCP:** Pode ser um servidor dedicado ou o próprio roteador da sua casa.
- **Roteadores Wireless:** Geralmente já vêm com o serviço DHCP ativado por padrão para facilitar a vida do usuário.
- **Endereço MAC:** Usado no processo de descoberta para identificar quem está pedindo o IP.

---

## 💻 Comandos / Sintaxe Importante

*Comandos para forçar a renovação do "aluguel" do IP:*
- **Windows:** `ipconfig /release` seguido de `ipconfig /renew`.
- **Linux:** `dhclient -r` seguido de `dhclient`.

---

## 🔬 Experimento / Prática

Observei que em redes domésticas, o roteador atua como o Gateway Padrão e o Servidor DHCP ao mesmo tempo, entregando IPs como `192.168.0.x` ou `192.168.1.x` automaticamente para todos os dispositivos.

---

## 📊 Resultados Observados

- O DHCP é vital para a **mobilidade**. Sem ele, você teria que reconfigurar o IP do seu celular toda vez que entrasse em um café ou na casa de um amigo.
- O uso de endereçamento dinâmico permite que os IPs retornem ao "pool" quando os dispositivos saem da rede, otimizando o uso dos endereços disponíveis.

---

## ⚠️ Problemas Encontrados

O perigo do **Conflito de IP**, que acontece quando alguém configura um IP estático que o DHCP já deu para outra pessoa.

---

## 🛠️ Solução

A melhor prática é reservar um intervalo do Pool (ex: do `.1` ao `.20`) apenas para IPs estáticos (servidores e impressoras) e deixar o resto para o DHCP.

---

## 🔐 Relação com Cibersegurança

- **Rogue DHCP Server:** Um ataque onde o hacker coloca um servidor DHCP falso na rede para distribuir IPs e se tornar o Gateway (Man-in-the-Middle).
- **DHCP Starvation:** O atacante pede todos os IPs do pool até esgotá-los, causando negação de serviço (DoS) para novos usuários.
- Entender o DHCP ajuda a identificar dispositivos estranhos na rede através dos logs de concessão.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
|------|-------------|
| **Broadcast de Destino** | Endereço `255.255.255.255` usado pelo cliente para achar o servidor. |
| **Gateway Padrão** | A saída da rede, informada pelo DHCP junto com o IP. |
| **DHCP Acknowledgment** | A confirmação final do servidor que fecha o contrato de aluguel. |

---

## 🧩 Insight do Dia

"O DHCP é o garçom da rede: você chega, ele te dá um lugar e as informações do menu sem você precisar pedir nada especificamente."

---

## 📖 Próximo Passo

Estudar **Módulo 12 — Gateways para outras redes** (Como sair da rede local).

---

## 📌 Resumo Final

O Módulo 11 mostrou que a automação é a alma das redes modernas. O DHCP não apenas facilita o trabalho do administrador, mas é o que permite que a internet seja plug-and-play para bilhões de pessoas.
