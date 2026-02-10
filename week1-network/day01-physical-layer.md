# OSI – Camada 1 (Física)

## 📖 Descrição
A Camada Física é responsável por transmitir bits (0 e 1) através de meios físicos como cabos, sinais de rádio (Wi-Fi) e fibra óptica. Ela é a base de toda comunicação em redes.

Sem essa camada funcionando corretamente, nenhuma outra camada do modelo OSI opera.

## ⚙️ Funcionamento
Essa camada converte dados digitais em sinais elétricos, ópticos ou de rádio, permitindo que a informação seja transportada entre dispositivos.

Ela define características como:
- Tipo de cabo
- Frequência
- Velocidade
- Potência do sinal

## 🚨 Riscos de Segurança
Os principais riscos nessa camada envolvem ataques físicos ou ao sinal, como:
- Interferência (Jamming)
- Criação de pontos de acesso falsos (Evil Twin)
- Desconexão física de cabos
- Roubo de equipamentos

## 🛠️ Exemplo
Comandos para visualizar interfaces e sinais:

```bash
ip link show
iwconfig
nmcli dev wifi list
