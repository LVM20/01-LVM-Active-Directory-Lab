# 🏢 LVM Technologies - Active Directory Lab

## 📌 Descrição

Este projeto simula a implantação de uma infraestrutura corporativa utilizando **Windows Server 2025** e **Active Directory**, reproduzindo um ambiente empresarial com autenticação centralizada, gerenciamento de usuários, grupos de segurança e controle de acesso a recursos compartilhados.

---

## 🎯 Objetivo

Implementar um ambiente Windows corporativo para estudo de:

- Active Directory Domain Services (AD DS)
- DNS
- Gerenciamento de usuários
- Organizational Units (OUs)
- Grupos de Segurança
- Controle de acesso baseado em grupos (RBAC)
- Compartilhamento de arquivos
- Estações Windows ingressadas no domínio

---

## 🖥️ Infraestrutura

| Máquina | Função | IP |
|----------|---------|---------|
| DC01 | Active Directory + DNS | 10.10.10.10 |
| WS01 | Estação RH | 10.10.10.20 |

Domínio:

```
lvm.local
```

---

## 📂 Estrutura Organizacional

- Diretoria
- RH
- Financeiro
- TI

---

## 👥 Implementações

- Criação do domínio **lvm.local**
- Configuração do DNS
- Criação de OUs
- Criação de usuários
- Criação de grupos de segurança
- Associação de usuários aos grupos
- Compartilhamento de pastas por departamento
- Controle de acesso baseado em grupos
- Ingresso de estação Windows 10 no domínio

---

## ✅ Validações

- Login utilizando contas do domínio
- Acesso permitido apenas ao departamento correspondente
- Bloqueio de acesso a departamentos não autorizados

---

## 📸 Evidências

As capturas de tela do laboratório estão disponíveis na pasta:

```
docs/
```

---

## 🚀 Próximos Projetos

- Projeto 2 – Group Policy (GPO) e Hardening
- Projeto 3 – Wazuh + Sysmon
- Projeto 4 – Detecção de Ataques
- Projeto 5 – Incident Response
- Projeto 6 – Vulnerability Management

---

## 👨‍💻 Autor

Leonardo Poncham