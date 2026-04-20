# 📚 Registro de Estudo — Cibersegurança

**Data:** 20/04/2026  
**Tema:** Módulo 8 da Cisco — Serviços de Endereçamento IP  
**Área:** Serviços de Camada de Aplicação e Redes (DNS e DHCP)

---

## 🎯 Objetivo do Estudo

Compreender os serviços fundamentais que permitem a comunicação na rede de forma amigável ao ser humano (**DNS**) e automatizada para os dispositivos (**DHCP**).

---

## 📖 Conceitos Fundamentais

- **DNS (Domain Name System):** O serviço que traduz nomes de domínio (ex: `www.cisco.com`) em endereços IP para que os computadores possam se comunicar.
- **DHCP (Dynamic Host Configuration Protocol):** O serviço que atribui automaticamente endereços IP, máscaras de sub-rede e gateways aos dispositivos.

---

## 🧠 Explicação Técnica

### 🌐 DNS: O "Catálogo Telefônico" da Internet
Como os humanos preferem nomes e os computadores preferem números, o DNS faz o meio de campo:
1. O usuário digita uma URL no navegador.
2. O computador envia uma consulta DNS para um servidor.
3. O servidor responde com o endereço IP correspondente ao nome.



### ⚡ DHCP: Configuração Automática
O DHCP evita que o administrador precise configurar cada computador manualmente (o que geraria erros e conflitos):
* **Pool de Endereços:** O servidor DHCP possui um intervalo de IPs disponíveis.
* **Aluguel (Lease):** O IP é emprestado ao dispositivo por um tempo determinado.
* **Gateway e DNS:** Além do IP, o DHCP também informa ao computador quem é o roteador de saída e qual servidor DNS usar.

---

## 🔢 O Processo DHCP (DORA)

| Sigla | Etapa | Descrição |
| :--- | :--- | :--- |
| **D** | **Discover** | O cliente grita na rede: "Alguém pode me dar um IP?" |
| **O** | **Offer** | O servidor responde: "Eu tenho este IP disponível para você." |
| **R** | **Request** | O cliente diz: "Eu aceito esse IP, por favor reserve para mim." |
| **A** | **Acknowledge** | O servidor confirma: "Ok, o IP é seu por X horas. Pode usar." |

---

## 💻 Conceitos Operacionais Importantes

- **Hierarquia DNS:** O sistema DNS é organizado em níveis (Domínios de Nível Superior como `.com`, `.org`, `.br`).
- **Reserva de IP:** É possível configurar o DHCP para que um dispositivo específico (como uma impressora) receba sempre o mesmo IP, baseado no seu endereço MAC.
- **Cache DNS:** O computador guarda as traduções recentes localmente para não precisar perguntar ao servidor o tempo todo.

---

## 🔬 Observação Prática (Foco em Segurança)

Para um analista de cibersegurança, esses serviços são alvos críticos:
- **DNS Poisoning:** Um atacante "envenena" a resposta DNS para enviar o usuário a um site falso (Phishing).
- **Rogue DHCP Server:** Um atacante coloca um servidor DHCP falso na rede para se tornar o Gateway e interceptar dados (**Man-in-the-Middle**).
- **Exposição de Dados:** Analisar requisições DNS pode revelar quais sites um funcionário visita ou para onde um malware está tentando se conectar.

---

## ⚠️ Problemas Encontrados

O computador tem IP, mas não abre sites.  
*Solução:* Geralmente é uma falha no **DNS**. O computador consegue chegar no IP, mas não sabe qual é o IP do nome digitado. Tente pingar um IP direto (como `8.8.8.8`) para testar.

---

## 🔐 Relação com Cibersegurança

- **Filtragem de DNS:** Empresas usam servidores DNS seguros para bloquear automaticamente o acesso a sites conhecidos por hospedar vírus.
- **DHCP Snooping:** Configuração em switches que permite que apenas portas confiáveis enviem respostas DHCP, bloqueando servidores falsos.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **FQDN** | Nome de Domínio Totalmente Qualificado (ex: pc01.vendas.empresa.com). |
| **Recursive Query** | Quando um servidor DNS pergunta a outro servidor em nome do cliente. |
| **Default Gateway** | Informação entregue pelo DHCP que aponta o caminho para fora da rede. |
| **Dynamic IP** | Endereço que pode mudar toda vez que o dispositivo se conecta. |

---

## 🧩 Insight do Dia

> "O DNS é a memória da internet e o DHCP é a hospitalidade da rede. Sem um, você não sabe onde ir; sem o outro, você não tem onde sentar."

---

## 📖 Próximo Passo

Prosseguir para os módulos de **Transporte de Aplicação** para ver como esses endereços são usados pelos programas que usamos no dia a dia.

---

## 📌 Resumo Final

O Módulo 8 explicou os serviços que tornam a rede usável e escalável. Para a cibersegurança, proteger o DNS e o DHCP é proteger a identidade e o fluxo de tráfego de toda a organização.
