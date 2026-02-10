# OSI – Camada 1 (Física)

## 📖 Descrição
Neste estudo, entendi que a Camada Física é responsável por transmitir os dados em forma de sinais elétricos, ópticos ou de rádio. Sem essa camada funcionando corretamente, nenhuma comunicação em rede acontece.

Percebi que tudo começa aqui: cabos, Wi-Fi, sinal e energia.

## ⚙️ Funcionamento
Aprendi que essa camada converte dados digitais em sinais físicos, permitindo que a informação viaje entre dispositivos.

Ela define características como tipo de cabo, frequência, velocidade e potência do sinal.

## 🚨 Riscos de Segurança
Notei que os principais riscos nessa camada estão relacionados ao acesso físico e à interferência no sinal, como:
- Evil Twin
- Interferência (Jamming)
- Desconexão de cabos
- Roubo de equipamentos

Esses ataques não são comuns em bug bounty, mas são importantes em testes físicos.

## 🛠️ Exemplo
Durante a prática, utilizei os seguintes comandos:

```bash
ip link show
iwconfig
nmcli dev wifi list
