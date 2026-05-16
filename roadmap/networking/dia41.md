# 🛡️ Registro de Estudo: Infraestrutura de Segurança de Rede

**Data:** 16/05/2026  
**Curso:** Cisco Endpoint Security  
**Módulo 6:** Infraestrutura de Segurança de Rede  

---

## 🎯 Objetivo do Módulo
Compreender o funcionamento, a aplicação e a importância dos principais dispositivos e serviços de segurança utilizados para proteger a infraestrutura de rede corporativa e gerenciar o tráfego de dados.

---

## 🧱 1. Dispositivos de Segurança (Firewalls e Sensores)
Os dispositivos de segurança atuam como barreiras e sensores que monitoram o tráfego da rede contra acessos não autorizados.

* **Tipos de Firewalls:**
    * **Filtragem de Pacotes (Sem Estado/Stateless):** Opera nas Camadas 3 e 4 do modelo OSI, permitindo ou negando pacotes com base em origem, destino e tipo de tráfego.
    * **Inspeção com Estado (Stateful):** Monitora o estado das conexões ativas para decidir se bloqueia ou permite o tráfego de forma dinâmica.
    * **Gateway de Aplicativo (Firewall Proxy):** Filtra informações nas Camadas 3, 4, 5 e 7.
    * **Next-Generation Firewalls (NGFW):** Vão além do básico, oferecendo prevenção integrada de intrusões, controle granular de aplicações e acesso a feeds de ameaças em tempo real.
* **IDS e IPS:**
    * **IDS (Detecção de Intrusão):** Monitora o tráfego para detectar e alertar sobre potenciais riscos.
    * **IPS (Prevenção de Intrusão):** Além de detectar, tem a capacidade de parar o tráfego inseguro ativamente. Ambos podem ser baseados em *host* ou em *rede*.
* **Appliances Especializados (Cisco):** * **AMP:** Advanced Malware Protection (Proteção avançada contra malware).
    * **WSA / ESA:** Web Security Appliance e Email Security Appliance, respectivamente. Todos integrados ao ecossistema de inteligência global do **Cisco Talos**.

---

## ⚙️ 2. Serviços de Segurança de Rede
Conjunto de protocolos e tecnologias essenciais para o controle, monitoramento e integridade dos dados e dispositivos na rede.

* **ACLs (Listas de Controle de Acesso):** Instruções que determinam se um dispositivo descarta ou encaminha pacotes com base no cabeçalho do pacote.
* **NTP (Network Time Protocol):** Sincroniza a hora em todos os dispositivos da rede, garantindo que os carimbos de data/hora nos logs sejam consistentes e precisos.
* **Syslog:** Servidor centralizado que compila e fornece acesso às mensagens de log geradas pelos dispositivos de rede.
* **SNMP (Simple Network Management Protocol):** Permite aos administradores monitorar, gerenciar o desempenho, localizar problemas e planejar o crescimento da rede.
* **NetFlow:** Coleta estatísticas detalhadas sobre os pacotes IP que passam por roteadores e switches Cisco.
* **Espelhamento de Porta (Port Mirroring):** Recurso de switch que duplica o tráfego de uma porta e o envia para outra porta conectada a um monitor de rede.
* **VPNs (Virtual Private Networks):** Redes privadas criptografadas criadas sobre uma infraestrutura de rede pública.

---

## 🔑 3. O Framework AAA (Autenticação, Autorização e Contabilidade)
Uma estrutura robusta para controle de acesso de usuários aos recursos da rede.

* **Conceito:**
    * **Autenticação:** Quem é o usuário? (Validação de identidade).
    * **Autorização:** O que o usuário pode fazer? (Definição de privilégios e comandos permitidos).
    * **Contabilidade (Accounting):** O que o usuário fez? (Registro e auditoria de ações realizadas).
* **Protocolos Utilizados:** O AAA normalmente utiliza servidores dedicados rodando protocolos como **TACACS+** ou **RADIUS**.

---

## 🔬 Observação Prática (Cibersegurança)
Neste módulo fica evidente que a segurança de rede é composta por camadas. Enquanto os firewalls barram o tráfego indesejado na borda, ferramentas de monitoramento como NetFlow, Syslog e SNMP garantem visibilidade total do que acontece internamente, e o AAA assegura que apenas pessoas autorizadas mexam na configuração dos equipamentos.

---

## 📚 Termos Chave

| Termo | Definição |
| :--- | :--- |
| **NGFW** | Next-Generation Firewall (Firewall de Próxima Geração com recursos avançados). |
| **AAA** | Authentication, Authorization, and Accounting (Estrutura de controle de acesso). |
| **RADIUS / TACACS+** | Protocolos utilizados para comunicação com servidores AAA. |
| **Cisco Talos** | Maior rede privada de detecção e correlação de ameaças do mundo. |

---

## 🧩 Insight do Dia
> "Não se pode proteger aquilo que não se pode ver. Dispositivos como Firewalls seguram o perímetro, mas serviços como Syslog, NTP e NetFlow são os olhos do administrador para entender o comportamento real da rede e responder a incidentes a tempo."

---

**Próximo Passo:** Módulo 7 — O Sistema Operacional Windows.
