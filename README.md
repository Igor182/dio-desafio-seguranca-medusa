# 🛡️ Desafio DIO: Força Bruta com Medusa e Kali Linux

## 🎯 Objetivo do Projeto

Este projeto documenta a implementação de ataques simulados de força bruta utilizando o **Kali Linux** e a ferramenta **Medusa** em um ambiente controlado e vulnerável (**Metasploitable 2**). O principal objetivo é exercitar a auditoria de segurança em serviços como FTP e SMB, validar a quebra de credenciais e, crucialmente, propor medidas de **mitigação** e defesa.

## 📚 Recursos e Ferramentas Utilizadas

Lista das principais ferramentas e tecnologias que tornaram a execução e a documentação deste projeto possível:

* **Kali Linux:** Distribuição Linux focada em segurança e pentesting.
* **VirtualBox:** Plataforma de virtualização para criação de ambiente isolado (Host-Only).
* **Metasploitable 2:** Máquina virtual deliberadamente vulnerável (alvo).
* **Medusa:** Ferramenta de força bruta rápida e modular, utilizada para testar FTP, SMB e HTTP.
* **enum4linux:** Ferramenta de enumeração de informações SMB (Samba).
* **GitHub/Markdown:** Utilizado para hospedar o portfólio e formatar o relatório técnico.

## ⚙️ Configuração do Ambiente

O ambiente de teste foi configurado no VirtualBox para garantir o isolamento, seguindo as diretrizes de ética de segurança (**pentest em ambiente controlado e autorizado**).

* **Atacante:** Kali Linux (IP:`192.168.56.102`)
* **Alvo:** Metasploitable 2 (IP: `192.168.56.101`)
* **Rede:** Configurada como **Rede Somente Host (Host-Only)**, permitindo comunicação exclusiva entre as VMs.

![Configuração da Rede e IPs das Máquinas](images/kali_metasploitable_ip.png)

---

## 💥 Cenários de Ataque e Execução

Os testes de força bruta foram realizados utilizando o **Medusa** e wordlists customizadas.

### 1. Ataque de Força Bruta em FTP

O Medusa foi utilizado para tentar combinações de usuários e senhas no serviço FTP.

#### **Wordlists Utilizadas**

As wordlists `users.txt` e `pass.txt` foram criadas com os seguintes comandos, subidos no diretório raiz do repositório:

#### Wordlists Utilizadas

As wordlists `users.txt` e `pass.txt` foram criadas com os seguintes comandos, subidos no diretório raiz do repositório, refletindo usuários comuns e senhas fracas.

```bash
# Conteúdo de users.txt (Usado para o ataque FTP e SMB)
echo -e "msfadmin\nuser\nteste\nadmin\nroot" > users.txt

# Conteúdo de pass.txt (Senhas mais fracas testadas)
echo -e "msfadmin\npassword\n123456\nqwerty\nservice" > pass.txt
