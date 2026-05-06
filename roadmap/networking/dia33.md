# 📚 Registro de Estudo — Cibersegurança

**Data:** 04/05/2026  
**Tema:** Módulo 10 da Cisco — A Linha de Comando do Cisco IOS  
**Área:** Configuração e Operação de Dispositivos de Rede

---

## 🎯 Objetivo do Estudo

Dominar o sistema operacional dos dispositivos Cisco (**IOS**) e aprender a navegar em seus diferentes modos de comando para configurar roteadores e switches de forma profissional e segura.

---

## 📖 Conceitos Fundamentais

- **Cisco IOS (Internetwork Operating System):** O sistema operacional proprietário usado na maioria dos dispositivos Cisco.
- **CLI (Command Line Interface):** A interface de linha de comando baseada em texto para configuração e monitoramento.
- **Acesso ao Console:** Conexão física direta ao dispositivo para configuração inicial (geralmente via cabo console).
- **Acesso Remoto:** Conexão via rede usando **SSH** (Seguro) ou **Telnet** (Inseguro).

---

## 🧠 Explicação Técnica

### 📂 Hierarquia de Modos do IOS
O IOS utiliza uma estrutura de modos para proteger as configurações de alterações acidentais:

1.  **User EXEC Mode (`Switch>`):** Modo de visualização limitada. Permite apenas comandos básicos de monitoramento.
2.  **Privileged EXEC Mode (`Switch#`):** Também conhecido como modo *Enable*. Permite visualizar todas as configurações e entrar nos modos de configuração.
3.  **Global Configuration Mode (`Switch(config)#`):** Onde as alterações que afetam o dispositivo como um todo são feitas.
4.  **Submodos de Configuração:** Usados para configurar interfaces específicas (`config-if`) ou linhas de acesso (`config-line`).


### ⌨️ Comandos de Navegação Essenciais
* `enable`: Entra no modo privilegiado.
* `configure terminal`: Entra no modo de configuração global.
* `exit`: Volta um nível na hierarquia.
* `end` ou `Ctrl+Z`: Volta diretamente para o modo Privileged EXEC.

---

## 🔢 Tabela de Atalhos da CLI

| Tecla / Comando | Função |
| :--- | :--- |
| **Tab** | Completa um comando parcial automaticamente. |
| **?** (Interrogação) | Ajuda contextual (mostra quais comandos podem ser usados). |
| **Seta para Cima** | Recupera o último comando digitado. |
| **show running-config** | Exibe a configuração que está rodando na RAM no momento. |
| **copy run start** | Salva a configuração atual na memória permanente (NVRAM). |

---

## 💻 Conceitos Operacionais Importantes

- **Configuração Volátil vs. Não Volátil:** Tudo o que você digita vai para a **Running-Config** (RAM). Se o switch desligar, você perde tudo, a menos que salve na **Startup-Config** (NVRAM).
- **Nomes de Dispositivo:** O primeiro passo da configuração deve ser o comando `hostname [NOME]` para identificar o equipamento na rede.

---

## 🔬 Observação Prática (Foco em Segurança)

Na perspectiva de Cibersegurança, a CLI é o "coração" do dispositivo:
- **Proteção de Modos:** É obrigatório configurar senhas para o modo *Enable* (`enable secret`) para evitar que qualquer pessoa com acesso físico altere as configurações.
- **Acesso Remoto Seguro:** Nunca use Telnet, pois os dados (incluindo senhas) viajam em texto simples. Use sempre **SSH**, que é criptografado.

---

## ⚠️ Problemas Encontrados

Esquecer de salvar as configurações antes de reiniciar o dispositivo.  
*Solução:* Criar o hábito de digitar `write` ou `copy running-config startup-config` após qualquer alteração importante.

---

## 🔐 Relação com Cibersegurança

- **Banner MOTD:** Configurar uma mensagem de aviso (`banner motd`) para informar que o acesso não autorizado é proibido. Isso tem valor legal em auditorias.
- **Criptografia de Senhas:** Usar o comando `service password-encryption` para que as senhas não apareçam em texto simples ao dar um `show run`.

---

## 📚 Termos Importantes Aprendidos

| Termo | Significado |
| :--- | :--- |
| **IOS** | Internetwork Operating System. |
| **NVRAM** | Memória onde a configuração de inicialização é salva. |
| **RAM** | Memória temporária onde a configuração ativa reside. |
| **Console Port** | Porta física para gerenciamento "out-of-band". |

---

## 🧩 Insight do Dia

> "A CLI da Cisco é como um diálogo: se você não souber o que dizer, o `?` te responde o que é possível. O segredo não é decorar comandos, mas entender em qual modo você precisa estar para agir."

---

## 📖 Próximo Passo

Prosseguir para o modulo 11 **imcp**

---

## 📌 Resumo Final

O Módulo 10 abriu as portas para o controle total do hardware. Para a Cibersegurança, a CLI é onde as políticas de defesa são implementadas "no ferro". Dominar a navegação e a hierarquia de modos é o que separa um usuário comum de um administrador de redes focado em segurança.
