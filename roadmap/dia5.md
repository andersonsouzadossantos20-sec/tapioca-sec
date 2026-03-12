# 📚 Registro de Estudo — Cibersegurança

**Data:**  
**Tema:** Camada 3 — Rede (IP)  
**Área:** Redes

---

# 🎯 Objetivo do Estudo

Entender como funciona o protocolo IP e como os pacotes viajam entre diferentes redes na internet.

---

# 📖 Conceitos Fundamentais

- IP address  
- pacotes IP  
- roteador  
- TTL  
- DNS  
- IP público e privado  

---

# 🧠 Explicação Técnica

O IP (Internet Protocol) é o endereço que identifica um dispositivo na rede.

Exemplo:

192.168.1.10

Ele possui:

- 32 bits
- 4 octetos

Formato:

X.X.X.X

Exemplo em binário:

11000000.10101000.00000001.00001010

Cada octeto pode ir de:

0 até 255

O IP funciona como um **endereço para entregar pacotes pela rede**.

Quando acessamos um site como:

google.com

O DNS converte isso para um IP, como por exemplo:

142.250.79.78

Assim os roteadores conseguem saber para onde enviar os pacotes.

---

# 🔧 Tecnologias / Ferramentas Relacionadas

- IP  
- DNS  
- roteadores  
- NAT  

---

# 💻 Comandos / Sintaxe Importante


ip a

ping 8.8.8.8

traceroute google.com


---

# 🔬 Experimento / Prática

1. Observei meu endereço IP usando `ip a`
2. Testei conexão com outro host usando `ping`
3. Usei `traceroute` para ver o caminho dos pacotes na internet
4. Analisei como o DNS converte domínio em endereço IP

---

# 📊 Resultados Observados

Consegui ver meu endereço IP na rede e entender como os pacotes passam por vários roteadores até chegar ao destino.

Também observei os saltos (hops) usando traceroute.

---

# ⚠️ Problemas Encontrados

Nenhum problema encontrado durante o estudo.

---

# 🛠️ Solução

Nenhuma ação corretiva foi necessária.

---

# 🔐 Relação com Cibersegurança

Conhecer a camada de rede ajuda a entender ataques como:

- IP spoofing
- network scanning
- descoberta de hosts

Ferramentas como nmap usam esse conhecimento para mapear redes.

---

# 📚 Termos Importantes Aprendidos

| Termo | Significado |
|------|-------------|
| IP Address | endereço que identifica um host na rede |
| TTL | limite de saltos de um pacote |
| Router | dispositivo que encaminha pacotes entre redes |
| DNS | sistema que converte domínio em IP |

---

# 🧩 Insight do Dia

Os dados não vão direto para o destino. Eles passam por vários roteadores na internet até chegar ao servidor.

---

# 📖 Próximo Passo

Estudar **sub-redes, máscara de rede e CIDR**.

---

# 📌 Resumo Final

O protocolo IP é responsável por identificar dispositivos e permitir o roteamento de pacotes entre redes. Cada pacote possui informações como IP de origem, destino e TTL, e os roteadores utilizam essas informações para encaminhar os dados até o destino final.
