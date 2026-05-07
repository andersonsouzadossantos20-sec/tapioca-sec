# 🛡️ Registro de Estudo: Segurança de Endpoint

**Data:** 07/05/2026  
**Curso:** Cisco Endpoint Security  
**Módulo 1:** Ameaças, Vulnerabilidades e Ataques à Segurança Cibernética  
**Status:** Concluído ✅

---

## 🎯 Objetivo do Módulo
Compreender o cenário atual de ameaças digitais, identificando como os atacantes exploram vulnerabilidades técnicas e psicológicas para comprometer dispositivos finais (endpoints).

---

## 📖 1. Ameaças e Vulnerabilidades
A segurança cibernética não lida apenas com hackers, mas com diversas categorias de perigo:

* **Tipos de Ameaças:** Erros de software, sabotagem, roubo de propriedade intelectual, falhas de hardware e desastres naturais.
* **Ameaças Internas:** Originadas por pessoas com acesso legítimo (funcionários ou parceiros). São críticas pois ignoram muitas defesas de perímetro.
* **Ataques de Dia Zero (0-day):** Exploram falhas desconhecidas pelos programadores, onde não existe correção (patch) disponível no momento do ataque.
* **Vulnerabilidades de Camada 2:** Ataques que ocorrem na rede local, como *ARP Spoofing*, inundação de tabelas MAC e ataques de *Man-in-the-Middle* (MitM).

---

## 🎭 2. Engenharia Social (O Fator Humano)
A manipulação psicológica é usada para obter acesso sem precisar quebrar senhas complexas.

* **Pretexting:** Inventar um cenário (fingir ser do suporte técnico) para enganar a vítima.
* **Táticas de Persuasão:** Uso de autoridade, urgência, intimidação, consenso (prova social) ou escassez.
* **Ataques Físicos:**
    * **Dumpster Diving:** Vasculhar o lixo em busca de documentos ou senhas descartadas.
    * **Tailgating / Piggybacking:** Seguir alguém autorizado para entrar num edifício restrito.
* **Outras variações:** *Watering Hole* (infetar sites que o alvo visita) e *Typosquatting* (registar domínios com erros de escrita, ex: `gogle.com`).

---

## 💻 3. Malware e Ataques de Rede
Os endpoints são os principais alvos de softwares maliciosos:

* **Tipos de Malware:**
    * **Vírus:** Precisa de ação humana para se espalhar.
    * **Worm (Verme):** Autossuficiente, espalha-se sozinho explorando falhas de rede.
    * **Trojan (Cavalo de Troia):** Esconde código malicioso dentro de um programa legítimo.
    * **Ransomware:** Bloqueia o acesso aos dados (criptografia) e exige um resgate.
* **Ataques de Aplicação:**
    * **Injeção (SQL, XML, DLL):** Inserir comandos maliciosos em campos de entrada de dados.
    * **Cross-Site Scripting (XSS):** Injetar scripts em páginas web visualizadas por outros usuários.
    * **Buffer Overflow:** Enviar mais dados do que a memória pode suportar para executar comandos com privilégios elevados.
* **DoS e DDoS:** Inundar um sistema com tráfego para torná-lo indisponível.



---

## 📱 4. Segurança Móvel e Wireless
Dispositivos móveis introduzem vetores de ataque específicos:

* **Grayware:** Aplicações que não são vírus, mas são irritantes ou invasivas (como adware).
* **SMiShing:** Phishing via SMS (mensagens de texto).
* **Bluetooth:**
    * **Bluejacking:** Enviar mensagens não solicitadas.
    * **Bluesnarfing:** Roubo de dados via conexão Bluetooth.
* **Wi-Fi:** Ataques de *Evil Twin* (Ponto de acesso falso com o mesmo nome da rede legítima) para capturar tráfego.

---

## 🛡️ 5. Estratégias de Mitigação (Defesa)
Para proteger os endpoints, o módulo recomenda:

1.  **Gestão de Patches:** Manter todos os sistemas e apps atualizados.
2.  **Firewalls de Host:** Filtrar o tráfego que entra e sai do dispositivo.
3.  **Endpoint Security Suites:** Uso de Antivírus de Próxima Geração (NGAV) e EDR (Endpoint Detection and Response).
4.  **Consciencialização:** Treinar o utilizador para identificar engenharia social.
5.  **Criptografia:** Proteger dados em repouso e em trânsito (VPN).

---

## 🔬 Observação Prática (Cibersegurança)
Nesta fase do estudo, fica claro que a segurança de rede (que estudaste antes) precisa de ser complementada pela segurança do host. Se o atacante consegue enganar o utilizador (Engenharia Social), ele entra na rede por uma "porta aberta" legítima.

---

## 📚 Termos Chave

| Termo | Definição |
| :--- | :--- |
| **PDU** | Protocol Data Unit (Unidade de dados na rede). |
| **Exploit** | Código ou técnica que aproveita uma vulnerabilidade. |
| **Vishing** | Phishing feito através de chamadas de voz. |
| **WPA3** | Protocolo de segurança wireless mais moderno e seguro. |

---

## 🧩 Insight do Dia
> "O endpoint é o destino final de quase todos os ataques. Não importa quão forte é o teu Firewall se o teu utilizador clica num link de SMiShing ou permite que um estranho entre no escritório por Tailgating."

---

**Próximo Passo:** Módulo 2 — Proteção de Redes e Dispositivos de Segurança.
