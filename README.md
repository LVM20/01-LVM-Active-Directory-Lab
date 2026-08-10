# 🏢 LVM Technologies — Active Directory Lab

Laboratório corporativo virtualizado desenvolvido para estudar e praticar **Windows Administration, Active Directory, DNS, gerenciamento de identidades, controle de acesso e fundamentos de segurança defensiva**.

O ambiente simula uma infraestrutura empresarial com diferentes departamentos, usuários, grupos de segurança, estações Windows e um servidor centralizado.

---

## 📌 Sobre o Projeto

O projeto consiste na implementação de uma infraestrutura baseada em **Windows Server 2025**, utilizando o **Active Directory Domain Services (AD DS)** como núcleo do ambiente corporativo.

Foram implementados:

* Active Directory Domain Services
* DNS integrado ao domínio
* Organizational Units (OUs)
* Usuários e grupos
* Controle de acesso baseado em grupos
* RBAC
* Compartilhamento de arquivos
* Permissões NTFS e SMB
* Estações Windows ingressadas no domínio
* Autenticação centralizada

A infraestrutura também foi utilizada como base para os projetos posteriores de **Blue Team, SIEM e monitoramento de segurança**.

---

# 🎯 Objetivos

* Implementar um domínio Active Directory funcional.
* Configurar DNS integrado ao AD.
* Criar uma estrutura organizacional baseada em departamentos.
* Criar e administrar usuários.
* Criar grupos de segurança.
* Implementar controle de acesso baseado em grupos.
* Configurar compartilhamentos de arquivos.
* Aplicar permissões de acesso.
* Integrar estações Windows ao domínio.
* Validar autenticação centralizada.
* Construir uma infraestrutura que pudesse ser expandida para projetos posteriores de segurança.

---

# 🖥️ Infraestrutura

| Host            | Função                               | Endereço IP    |
| --------------- | ------------------------------------ | -------------- |
| **DC01**        | Active Directory + DNS + File Server | `10.10.10.10`  |
| **WS01**        | Recursos Humanos                     | `10.10.10.20`  |
| **WS02**        | Financeiro                           | `10.10.10.21`  |
| **WS03**        | Tecnologia da Informação             | `10.10.10.22`  |
| **WS04**        | Diretoria                            | `10.10.10.23`  |
| **SEC01**       | Wazuh Server                         | `10.10.10.30`  |
| **Host Ubuntu** | Administração / Laboratório          | `10.10.10.100` |

---

# 🌐 Rede

### Domínio

```text
lvm.local
```

### Rede

```text
10.10.10.0/24
```

### DNS

```text
10.10.10.10
```

---

# 🏢 Estrutura Organizacional

A estrutura do Active Directory foi organizada de acordo com os departamentos da empresa:

```text
LVM Technologies
│
├── Diretoria
├── RH
├── Financeiro
└── TI
```

Essa organização permite separar usuários, computadores e permissões de acordo com suas respectivas áreas.

---

# 👥 Usuários

### Diretoria

* `diretor01`
* `diretor02`

### RH

* `barbara.rh`
* `giovana.rh`

### Financeiro

* `lais.fin`
* `cecilia.fin`

### TI

* `ricardo.ti`
* `suporte.ti`
* `admin.ti`

---

# 🔐 Grupos de Segurança

Foram criados grupos específicos para cada departamento:

```text
GRP_DIRETORIA
GRP_RH
GRP_FINANCEIRO
GRP_TI
```

Os grupos foram utilizados para facilitar o gerenciamento de permissões e implementar o princípio de controle de acesso baseado em funções e departamentos.

---

# 💻 Computadores do Domínio

| Computador         | Departamento |
| ------------------ | ------------ |
| **PC-RH01**        | RH           |
| **PC-FIN01**       | Financeiro   |
| **PC-TI01**        | TI           |
| **NOTEBOOK-DIR01** | Diretoria    |

Os computadores foram ingressados no domínio `lvm.local`, permitindo autenticação e gerenciamento centralizados.

---

# 📁 Compartilhamentos

Foram configurados compartilhamentos de arquivos específicos para cada departamento:

```text
\\DC01\RH
\\DC01\Financeiro
\\DC01\Diretoria
\\DC01\TI
```

As permissões foram configuradas utilizando grupos de segurança do Active Directory.

---

# ⚙️ Funcionalidades Implementadas

* ✅ Active Directory Domain Services
* ✅ DNS integrado ao Active Directory
* ✅ Organizational Units
* ✅ Usuários
* ✅ Grupos de Segurança
* ✅ RBAC
* ✅ Permissões NTFS
* ✅ Compartilhamento SMB
* ✅ Controle de acesso
* ✅ Estações Windows ingressadas no domínio
* ✅ Autenticação centralizada
* ✅ Estrutura organizacional por departamento

---

# 🧪 Testes Realizados

Foram realizados testes para validar o funcionamento da infraestrutura:

* Login utilizando contas do domínio.
* Resolução DNS.
* Ingresso das estações no domínio.
* Autenticação centralizada.
* Validação dos grupos de segurança.
* Testes de acesso aos compartilhamentos.
* Validação das permissões.
* Testes de acesso autorizado e não autorizado.

---

# 📸 Evidências

As evidências do projeto estão disponíveis no diretório:

```text
evidencias/
```

O diretório contém capturas relacionadas à implementação e validação do ambiente, incluindo:

* Active Directory
* DNS
* Organizational Units
* Usuários
* Grupos
* Computadores
* Compartilhamentos
* Permissões
* Testes realizados
* Configurações do domínio

---

# 📄 Relatório Técnico

O relatório técnico completo está disponível no diretório:

```text
relatorio/
```

O documento apresenta os detalhes da implementação, escopo técnico, evidências, resultados e competências desenvolvidas durante o projeto.

---

# 🛠️ Tecnologias Utilizadas

* Windows Server 2025
* Windows
* Active Directory
* DNS
* NTFS
* SMB
* RBAC
* Virtualização
* Ubuntu Linux
* KVM/QEMU

---

# 🚀 Roadmap do Laboratório

Este projeto representa a base da infraestrutura utilizada nos projetos seguintes.

* ✅ **Projeto 1 — Active Directory Lab**
* ⏳ **Projeto 2 — Group Policy (GPO) & Hardening**
* ⏳ **Projeto 3 — Wazuh + Sysmon**
* ⏳ **Projeto 4 — Detecção de Ataques**
* ⏳ **Projeto 5 — Incident Response**
* ⏳ **Projeto 6 — Vulnerability Management**
* ⏳ **Projeto 7 — Suricata IDS/IPS**
* ⏳ **Projeto 8 — pfSense Firewall**
* ⏳ **Projeto 9 — SOC / Security Operations**
* ⏳ **Projeto 10 — Projeto Final de Cybersecurity**

---

# 🧠 Competências Desenvolvidas

Este projeto permitiu desenvolver conhecimentos práticos em:

* Windows Server
* Active Directory
* DNS
* Gerenciamento de usuários
* Gerenciamento de grupos
* RBAC
* NTFS Permissions
* SMB
* Controle de acesso
* Autenticação centralizada
* Administração de ambientes Windows
* Virtualização
* Troubleshooting
* Estruturação de ambientes corporativos

---

# 👨‍💻 Autor

**Leonardo Poncham**

---

## 🎯 Objetivo do Laboratório

Este laboratório faz parte de uma série de projetos práticos voltados ao desenvolvimento de competências em **Cybersecurity, Blue Team, SOC, Threat Detection e Incident Response**.

A infraestrutura criada neste projeto serve como base para a implementação de mecanismos de **monitoramento, detecção, hardening, análise de eventos e resposta a incidentes** nos projetos seguintes.
