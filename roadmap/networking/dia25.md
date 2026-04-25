# 📚 Registro de Estudo — Cibersegurança

**Data:** 12/04/2026  
**Tema:** Módulo 3 da Cisco — Sistemas Numéricos  
**Área:** Fundamentos de Dados e Endereçamento de Rede

---

## 🎯 Objetivo do Estudo

Compreender as bases numéricas fundamentais (**Binário** e **Hexadecimal**) utilizadas em redes de computadores para representar endereços lógicos (IPv4), físicos (MAC) e de próxima geração (IPv6).

---

## 📖 Conceitos Fundamentais

- **Sistema Binário (Base 2):** Sistema de numeração que utiliza apenas os dígitos **0** e **1** (chamados de bits). É o idioma nativo de hosts, servidores e dispositivos de rede.
- **Sistema Decimal (Base 10):** Sistema utilizado por humanos para facilitar a leitura; os endereços IPv4 são geralmente expressos em notação decimal com pontos para as pessoas.
- **Sistema Hexadecimal (Base 16):** Utiliza os dígitos de **0 a 9** e as letras **A a F** para representar valores. É a base principal para endereços IPv6 e endereços MAC Ethernet.

---

## 🧠 Explicação Técnica

### 🔢 Sistemas de Números Binários
* Endereços IPv4 são compostos por uma sequência de 32 bits, mas exibidos em formato decimal para facilidade humana.
* O sistema binário usa potências de base 2 para definir o valor posicional de cada dígito.
* **Conversão:** Uma ferramenta essencial é a tabela de valores posicionais binários, comumente usada com 8 espaços (8 bits equivalem a **1 byte** ou um octeto no IPv4).


### 🔡 Sistema de Numeração Hexadecimal
* O hexadecimal e o binário funcionam bem juntos porque é fácil expressar um valor de **quatro bits binários** como um único dígito hexadecimal.
* **IPv6:** Endereços de 128 bits de comprimento. Cada 4 bits é representado por um único dígito hexadecimal, totalizando 32 valores hexadecimais.
* Endereços IPv6 não diferenciam maiúsculas de minúsculas.

---

## 🔢 Tabela de Correspondência Rápida

| Decimal | Binário (4 bits) | Hexadecimal |
| :--- | :--- | :--- |
| 0 | 0000 | 0 |
| 9 | 1001 | 9 |
| 10 | 1010 | A |
| 11 | 1011 | B |
| 12 | 1100 | C |
| 13 | 1101 | D |
| 14 | 1110 | E |
| 15 | 1111 | F |

---

## 💻 Conceitos Operacionais Importantes

- **Notação Decimal com Pontos:** No IPv4, cada um dos quatro octetos é convertido de binário para um número entre 0 e 255.
- **Simplificação Hexadecimal:** Em vez de ler `1111 1111`, usamos `FF`. Isso torna a análise de logs de rede e cabeçalhos de pacotes muito mais rápida para o analista.

---

## 🔬 Observação Prática (Foco em Segurança)

A compreensão desses sistemas é vital para a análise de tráfego:
- **Análise de Malware:** Muitas strings maliciosas são ofuscadas em hexadecimal ou base64 para evitar detecção simples por antivírus.
- **Análise de Pacotes (Wireshark):** Os dados brutos da rede são exibidos em hexadecimal. Saber que um campo específico começa com `0x` indica que o valor a seguir é hexa.

---

## ⚠️ Problemas Encontrados

Dificuldade inicial em converter números decimais altos (como 240) para binário rapidamente.  
*Solução:* Praticar com a tabela de potências de 2 ($128, 64, 32, 16, 8, 4, 2, 1$). Se o número for maior ou igual ao valor da posição, subtraia e coloque "1", caso contrário, "0".

---

## 🔐 Relação com Cibersegurança

- **Máscaras de Sub-rede:** Entender binário é obrigatório para compreender como as máscaras de sub-rede isolam partes de uma rede, o que é fundamental para a segurança e segmentação de tráfego.
- **Identificação de Dispositivos:** O endereço MAC (hexadecimal) pode ser clonado (*MAC Spoofing*). Reconhecer o formato hexadecimal ajuda a identificar anomalias em ferramentas de monitoramento.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **Bit** | A menor unidade de dados (0 ou 1). |
| **Byte / Octeto** | Conjunto de 8 bits. |
| **Base 16** | Outro nome para o sistema hexadecimal. |
| **Valor Posicional** | O valor que um dígito representa dependendo de sua posição na sequência. |

---

## 🧩 Insight do Dia

> "Computadores não entendem nomes, sites ou cores; eles só entendem se a energia está passando (1) ou não (0). Todo o resto é apenas uma tradução matemática para nós."

---

## 📖 Próximo Passo

Avançar para o **Módulo 4 — Comutação Ethernet** para ver como esses endereços físicos (MAC) e sistemas numéricos são aplicados na prática para movimentar dados dentro de uma rede local.

---

## 📌 Resumo Final

O Módulo 3 forneceu a base matemática para a comunicação digital. Para cibersegurança, não se trata apenas de fazer contas, mas de ganhar a habilidade de ler os dados brutos que trafegam na rede, permitindo identificar padrões e anomalias que seriam invisíveis em interfaces gráficas comuns.
