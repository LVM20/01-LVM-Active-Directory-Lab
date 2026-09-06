# 🏢 Projeto 01 — Active Directory Corporate Lab

Laboratório corporativo virtualizado desenvolvido para praticar **Windows Administration, Active Directory, DNS, gerenciamento de identidades e controle de acesso**.

O ambiente simula a infraestrutura da **LVM Technologies**, utilizando Active Directory como núcleo para autenticação, usuários, grupos, computadores e compartilhamentos.

> **Aviso:** ambiente virtualizado e controlado, desenvolvido exclusivamente para fins educacionais.

---

## 🎯 Objetivo

Implementar uma infraestrutura Windows corporativa baseada em **Active Directory Domain Services (AD DS)**.

Durante o projeto foram praticados:

* Active Directory e DNS;
* Organizational Units;
* Usuários e grupos;
* RBAC e controle de acesso;
* Permissões NTFS e SMB;
* Domain Join;
* Autenticação centralizada;
* Troubleshooting de Windows/AD.

---

## 🏗️ Ambiente

| Host            | Função                               | IP             |
| --------------- | ------------------------------------ | -------------- |
| **DC01**        | Active Directory + DNS + File Server | `10.10.10.10`  |
| **WS01**        | Recursos Humanos                     | `10.10.10.20`  |
| **WS02**        | Financeiro                           | `10.10.10.21`  |
| **WS03**        | TI                                   | `10.10.10.22`  |
| **WS04**        | Diretoria                            | `10.10.10.23`  |
| **SEC01**       | Wazuh Server                         | `10.10.10.30`  |
| **Host Ubuntu** | Administração                        | `10.10.10.100` |

```text
Domínio: lvm.local
Rede:    10.10.10.0/24
DNS:     10.10.10.10
```

---

## 🧱 Arquitetura

```text
                    LVM Technologies
                          │
                    Active Directory
                          │
                         DC01
                    10.10.10.10
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
      WS01              WS02              WS03
       RH            Financeiro             TI
    .10.10.20        .10.10.21        .10.10.22
        │                 │                 │
        └─────────────────┼─────────────────┘
                          │
                         WS04
                      Diretoria
                    10.10.10.23
```

---

## 👥 Active Directory

Estrutura organizacional:

```text
LVM Technologies
│
├── Diretoria
├── RH
├── Financeiro
└── TI
```

Grupos:

```text
GRP_DIRETORIA
GRP_RH
GRP_FINANCEIRO
GRP_TI
```

Foram criados usuários e computadores associados aos respectivos departamentos.

---

## 📁 Controle de Acesso

Foram configurados compartilhamentos:

```text
\\DC01\RH
\\DC01\Financeiro
\\DC01\Diretoria
\\DC01\TI
```

O acesso foi controlado através de:

```text
Active Directory Groups
        ↓
RBAC
        ↓
Permissões NTFS
        ↓
Compartilhamentos SMB
```

---

## 🧪 Validação

Foram realizados testes de:

* Autenticação no domínio;
* Resolução DNS;
* Domain Join;
* Associação a grupos;
* Acesso autorizado e não autorizado;
* Permissões NTFS e SMB.

---

## ⚙️ Tecnologias

* Windows Server
* Windows
* Active Directory
* DNS
* SMB
* NTFS
* RBAC
* KVM/QEMU
* Ubuntu Linux

---

## 📸 Evidências

As evidências estão disponíveis em:

```text
evidencias/
```

Incluem capturas relacionadas a:

* Active Directory;
* DNS;
* Usuários e grupos;
* Computadores;
* Domain Join;
* Compartilhamentos;
* Permissões;
* Testes realizados.

---

## 📄 Relatório técnico

O relatório completo está disponível em:

```text
relatorio/
```

---

## 📈 Resultados

* ✅ Active Directory implementado;
* ✅ DNS integrado ao domínio;
* ✅ OUs, usuários e grupos configurados;
* ✅ Domain Join realizado;
* ✅ RBAC implementado;
* ✅ NTFS e SMB configurados;
* ✅ Autenticação centralizada validada;
* ✅ Infraestrutura preparada para os próximos projetos.

---

## 🧠 Competências desenvolvidas

* Windows Administration
* Active Directory
* DNS
* Identity Management
* Authentication
* RBAC
* Access Control
* NTFS / SMB
* TCP/IP
* Virtualização
* Troubleshooting

---

## 🚀 Próximas evoluções

A infraestrutura criada neste projeto serve como base para:

```text
GPO & Hardening
      ↓
Wazuh & Sysmon
      ↓
Threat Hunting
      ↓
Incident Response
      ↓
Vulnerability Management
      ↓
IAM
      ↓
Network Security
      ↓
Penetration Testing
```

---

## 🏁 Conclusão

O **Projeto 01 — Active Directory Corporate Lab** estabeleceu a infraestrutura Windows corporativa utilizada como base para os demais projetos da **LVM Technologies**.

O laboratório permitiu praticar **Active Directory, DNS, gerenciamento de identidades, RBAC, autenticação, NTFS, SMB e administração de ambientes Windows**.

A infraestrutura foi implementada e validada com sucesso, servindo como fundação para a evolução do laboratório em **Cybersecurity, Blue Team e SOC**.

---

## 📌 Status

```text
Projeto: Active Directory Corporate Lab
Status: Concluído
Ambiente: Laboratório corporativo virtualizado
Domínio: lvm.local
Rede: 10.10.10.0/24
Resultado: Infraestrutura AD implementada e validada
```

---

## 👨‍💻 Autor

**Leonardo Poncham**

**Foco:** Cybersecurity | Windows | Active Directory | Blue Team | SOC
