# 📚 Registro de Estudo — Cibersegurança

**Data:** 14/05/2026  
**Tema:** Módulo 4 da Cisco — Atacando o que Fazemos  
**Área:** Segurança de Serviços de Rede, Aplicações Corporativas e Mitigação

---

## 🎯 Objetivo do Estudo

Compreender como os atacantes exploram serviços essenciais de rede (ARP, DNS, DHCP), vulnerabilidades em aplicações Web/E-mail e quais as práticas recomendadas para mitigar essas ameaças comuns.

---

## 📖 Conceitos Fundamentais

- **Vulnerabilidades de Serviços de Infraestrutura:** Serviços básicos que fazem a rede funcionar (como mapeamento de nomes e IPs) carecem de autenticação nativa por padrão, tornando-os alvos fáceis de envenenamento e falsificação.
- **Ataques à Camada de Aplicação (Web e Mail):** Focam nas falhas de desenvolvimento de software (injeção de código) e na manipulação de usuários (phishing via e-mail).
- **Estratégia de Mitigação em Camadas:** A defesa de uma rede depende de políticas escritas, conscientização humana, criptografia e infraestrutura de hardware dedicada (Firewalls/IPS).

---

## 🧠 Explicação Técnica

### 🌐 1. Serviços de Rede (IP) Sob Ataque
* **ARP (Address Resolution Protocol):** Qualquer host pode enviar um "ARP gratuito" (não solicitado). Atacantes usam isso para **envenenar o cache ARP**, mapeando o IP do gateway para o seu próprio endereço MAC (Ataque Man-in-the-Middle).
* **DNS (Domain Name Service):** * *Envenenamento de Cache:* Injeção de registros falsos em resolvedores abertos para redirecionar tráfego.
    * *Técnicas Furtivas:* **Fast Flux** e **Double IP Flux** alteram rapidamente os IPs e servidores autoritativos para ocultar servidores maliciosos.
    * *Tunelamento DNS:* Colocar tráfego malicioso que não é DNS oculto dentro de consultas legítimas de porta 53 (frequentemente usado por botnets).
* **DHCP (Dynamic Host Configuration Protocol):** Um servidor DHCP invasor (Rogue DHCP) pode responder a requisições broadcast mais rápido que o servidor legítimo, fornecendo gateways falsos, servidores DNS maliciosos e IPs errados aos clientes.

### 💻 2. Serviços Corporativos (Web e E-mail)
* **Ataques Baseados na Web:** * *Drive-by Download:* Infecção de hosts simplesmente ao visitar uma página web legítima que foi comprometida.
    * *Injeções (SQLi):* Exploração de campos de entrada mal validados para extrair dados privados de bancos de dados.
    * *XSS (Cross-Site Scripting):* Execução de scripts maliciosos no navegador da vítima a partir de uma aplicação web vulnerável.
* **Ataques Baseados em E-mail:** Uso do protocolo SMTP para transportar cargas de malware ou e-mails de phishing.

---

## 🔬 Observação Prática e Mitigação (Foco em Segurança)

Para defender a infraestrutura contra as ameaças do módulo, utilizam-se os seguintes pilares:

### 🛡️ Mitigação de Ataques Comuns
- **Vírus e Cavalo de Tróia:** Uso de antivírus corporativo atualizado constantemente.
- **Worms (Vermes de Rede):** A resposta rápida exige 4 fases bem definidas: **Contenção**, **Inoculação**, **Quarentena** e **Tratamento**.
- **Ataques de Reconhecimento e Sniffing:** Implementar autenticação forte, infraestrutura comutada (switches em vez de hubs) e o uso indispensável de **criptografia** para invalidar capturas de pacotes por atacantes.
- **Ataques DoS/DDoS:** Utilização de ferramentas que detectam tráfego anômalo e bloqueio de IPs de origem falsificados na borda.

---

## ⚠️ Problemas Encontrados

Mitigar ataques de camada de aplicação exige entender o ecossistema. Negligenciar a análise do tráfego DNS achando que ele serve "apenas para resolver nomes" abre margem para vazamento de dados via tunelamento.  
*Solução:* Implementar firewalls com capacidade de inspeção profunda de pacotes (DPI) especificamente para tráfego DNS e HTTP/S.

---

## 🔐 Relação com Cibersegurança

- **OWASP Top 10:** Referência essencial citada no módulo para identificar e blindar aplicações web contra as falhas mais críticas (como SQLi e XSS).
- **Segurança de E-mail:** Uso de appliances de segurança dedicados a analisar o tráfego SMTP para bloquear spam, links maliciosos e anexos perigosos antes de chegarem à caixa de entrada do usuário.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **ARP Gratuito** | Uma resposta ARP não solicitada que atualiza a tabela ARP dos hosts vizinhos. |
| **Fast Flux** | Técnica onde botnets mudam rapidamente os registros de endereço IP associados a um domínio. |
| **Rogue DHCP** | Servidor DHCP não autorizado introduzido na rede para desviar ou paralisar o tráfego. |
| **Inoculação** | Fase de combate a worms que consiste em aplicar patches de correção nos hosts para impedir novas infecções. |

---

## 🧩 Insight do Dia

> "Os ataques mais perigosos não quebram o código do sistema; eles usam as funções legítimas de infraestrutura (como ARP e DNS) exatamente do modo como foram desenhadas, provando que a pior vulnerabilidade de uma rede é assumir que toda requisição interna é confiável."

---

## 📖 Próximo Passo

Avançar para o **Módulo 5 — Comunicação de Rede Sem Fio (Wireless)** para entender como os dados se propagam pelo ar e quais as vulnerabilidades de criptografia específicas do Wi-Fi.

---

## 📌 Resumo Final

O Módulo 4 deslocou o foco dos pacotes de rede brutos para os serviços corporativos diários. Proteger o endpoint e a rede contra ataques direcionados ao "que fazemos" exige um casamento perfeito entre patches de software, arquitetura de rede inteligente (como DHCP Snooping e inspeção dinâmica de ARP) e a eterna vigilância sobre o comportamento das aplicações.
