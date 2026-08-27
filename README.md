# 🏢 Projeto 01 — Active Directory Corporate Lab

Laboratório corporativo virtualizado desenvolvido para praticar **Windows Administration, Active Directory, DNS, gerenciamento de identidades, controle de acesso e fundamentos de segurança defensiva**.

O ambiente simula uma infraestrutura empresarial da **LVM Technologies**, composta por um controlador de domínio, DNS, departamentos, usuários, grupos de segurança, estações Windows e compartilhamentos de arquivos.

A infraestrutura desenvolvida neste projeto serve como **base para os projetos posteriores de GPO, Hardening, Wazuh, Threat Hunting, Incident Response e demais atividades de Cybersecurity**.

> **Aviso:** todas as configurações foram realizadas em ambiente virtualizado e controlado, exclusivamente para fins educacionais.

---

## 🎯 Objetivo

O objetivo deste projeto foi construir uma infraestrutura corporativa Windows baseada em **Active Directory Domain Services (AD DS)**.

Durante a implementação foram praticados:

* Criação e configuração de um domínio Active Directory;
* Configuração de DNS integrado ao AD;
* Estruturação de Organizational Units;
* Criação e gerenciamento de usuários;
* Criação de grupos de segurança;
* Controle de acesso baseado em grupos;
* RBAC;
* Configuração de compartilhamentos SMB;
* Aplicação de permissões NTFS;
* Ingresso de estações Windows no domínio;
* Autenticação centralizada;
* Validação da infraestrutura;
* Troubleshooting de serviços Windows e Active Directory.

---

# 🏗️ Ambiente do laboratório

O laboratório foi construído em ambiente virtualizado utilizando **KVM/QEMU**, com Ubuntu Linux como sistema de administração.

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

## 🖥️ Infraestrutura

| Host            | Função                               | Endereço IP    |
| --------------- | ------------------------------------ | -------------- |
| **DC01**        | Active Directory + DNS + File Server | `10.10.10.10`  |
| **WS01**        | Endpoint — Recursos Humanos          | `10.10.10.20`  |
| **WS02**        | Endpoint — Financeiro                | `10.10.10.21`  |
| **WS03**        | Endpoint — Tecnologia da Informação  | `10.10.10.22`  |
| **WS04**        | Endpoint — Diretoria                 | `10.10.10.23`  |
| **SEC01**       | Wazuh Server                         | `10.10.10.30`  |
| **Host Ubuntu** | Administração / Laboratório          | `10.10.10.100` |

---

# 🧱 Arquitetura

A infraestrutura foi organizada de forma semelhante a um ambiente corporativo real:

```text
                         LVM Technologies
                               │
                         Active Directory
                               │
                              DC01
                        10.10.10.10
                               │
              ┌────────────────┼────────────────┐
              │                │                │
            RH             Financeiro           TI
              │                │                │
            WS01             WS02              WS03
        10.10.10.20      10.10.10.21      10.10.10.22
                               │
                            Diretoria
                               │
                              WS04
                         10.10.10.23
                               │
                               ▼
                             SEC01
                        Wazuh Server
                        10.10.10.30
```

O **DC01** atua como núcleo da infraestrutura de identidade e resolução de nomes, enquanto as estações Windows representam os diferentes departamentos da organização.

---

# 🌐 Active Directory

O domínio utilizado no laboratório é:

```text
lvm.local
```

O Active Directory foi utilizado para centralizar:

* Identidades;
* Autenticação;
* Grupos;
* Computadores;
* Estrutura organizacional;
* Controle de acesso.

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

Essa organização permite separar os objetos do domínio de acordo com suas respectivas áreas e facilita a aplicação futura de políticas e permissões.

---

# 👥 Usuários

### Diretoria

```text
diretor01
diretor02
```

### RH

```text
barbara.rh
giovana.rh
```

### Financeiro

```text
lais.fin
cecilia.fin
```

### TI

```text
ricardo.ti
suporte.ti
admin.ti
```

Os usuários foram criados no Active Directory e utilizados posteriormente para validação de autenticação e controle de acesso.

---

# 🔐 Grupos de Segurança

Foram criados grupos específicos para os departamentos:

```text
GRP_DIRETORIA
GRP_RH
GRP_FINANCEIRO
GRP_TI
```

Os grupos foram utilizados como base para o gerenciamento de permissões.

Essa abordagem reduz a necessidade de atribuir permissões diretamente a usuários individuais e facilita a administração do ambiente.

---

# 💻 Computadores do domínio

As estações Windows foram organizadas de acordo com seus respectivos departamentos:

| Computador         | Departamento |
| ------------------ | ------------ |
| **PC-RH01**        | RH           |
| **PC-FIN01**       | Financeiro   |
| **PC-TI01**        | TI           |
| **NOTEBOOK-DIR01** | Diretoria    |

As máquinas foram ingressadas no domínio:

```text
lvm.local
```

permitindo autenticação e gerenciamento centralizados.

---

# 📁 Compartilhamentos

Foram configurados compartilhamentos de arquivos específicos para cada departamento:

```text
\\DC01\RH
\\DC01\Financeiro
\\DC01\Diretoria
\\DC01\TI
```

O controle de acesso foi estruturado utilizando grupos de segurança do Active Directory.

---

# 🔒 Permissões e controle de acesso

O laboratório utilizou:

```text
Active Directory Groups
        ↓
Controle de acesso
        ↓
Permissões NTFS
        ↓
Compartilhamentos SMB
```

A utilização de grupos permite administrar permissões de forma centralizada e alinhada aos departamentos da organização.

---

# ⚙️ DNS

O DNS foi integrado ao Active Directory e utilizado para resolução de nomes dentro do domínio.

Servidor DNS:

```text
10.10.10.10
```

A resolução de nomes é fundamental para o funcionamento correto de serviços dependentes do domínio, incluindo autenticação e comunicação entre os computadores.

---

# 🧪 Validação e testes

Após a implementação foram realizados testes para validar a infraestrutura.

### Autenticação

* Login utilizando contas do domínio;
* Validação das credenciais;
* Autenticação centralizada.

### DNS

* Resolução de nomes;
* Comunicação com o controlador de domínio;
* Validação do DNS utilizado pelas estações.

### Domain Join

* Ingresso das estações no domínio;
* Validação da associação das máquinas ao Active Directory.

### Grupos

* Validação da associação dos usuários aos grupos;
* Testes de controle de acesso.

### Compartilhamentos

* Acesso autorizado;
* Acesso não autorizado;
* Validação das permissões NTFS e SMB.

---

# 📊 Funcionalidades implementadas

* ✅ Active Directory Domain Services
* ✅ DNS integrado ao Active Directory
* ✅ Organizational Units
* ✅ Usuários
* ✅ Grupos de segurança
* ✅ RBAC
* ✅ Controle de acesso
* ✅ Permissões NTFS
* ✅ Compartilhamentos SMB
* ✅ Domain Join
* ✅ Autenticação centralizada
* ✅ Estrutura organizacional por departamento
* ✅ Infraestrutura virtualizada

---

# 📸 Evidências

As evidências do projeto estão organizadas no diretório:

```text
evidencias/
```

As capturas incluem evidências relacionadas a:

* Active Directory;
* DNS;
* Organizational Units;
* Usuários;
* Grupos;
* Computadores;
* Domain Join;
* Compartilhamentos;
* Permissões;
* Autenticação;
* Testes realizados.

---

# 📄 Relatório técnico

O relatório técnico completo está disponível no diretório:

```text
relatorio/
```

O documento contém informações detalhadas sobre:

* Implementação;
* Configuração;
* Estrutura do domínio;
* Evidências;
* Testes;
* Resultados;
* Troubleshooting;
* Competências desenvolvidas.

---

# ⚠️ Limitações

Como se trata de um laboratório educacional, a infraestrutura possui limitações quando comparada a um ambiente corporativo real.

Entre elas:

* Ambiente isolado e controlado;
* Quantidade reduzida de endpoints;
* Estrutura simplificada de departamentos;
* Ausência de infraestrutura redundante;
* Ausência de múltiplos controladores de domínio;
* Ausência de alta disponibilidade;
* Serviços corporativos limitados ao escopo do laboratório.

Essas limitações não impedem o objetivo principal do projeto, que é desenvolver conhecimento prático sobre administração de ambientes Windows e Active Directory.

---

# 📈 Resultados

Ao final do projeto foi possível validar:

* ✅ Domínio Active Directory funcional;
* ✅ DNS integrado ao domínio;
* ✅ Estrutura organizacional por departamentos;
* ✅ Usuários centralizados;
* ✅ Grupos de segurança;
* ✅ Controle de acesso baseado em grupos;
* ✅ Compartilhamentos SMB;
* ✅ Permissões NTFS;
* ✅ Estações ingressadas no domínio;
* ✅ Autenticação centralizada;
* ✅ Infraestrutura preparada para projetos de segurança posteriores.

---

# 🧠 Competências desenvolvidas

Durante o projeto foram praticadas competências relacionadas a:

### Windows Administration

* Windows Server;
* Administração de usuários;
* Administração de computadores;
* Gerenciamento de serviços;
* Troubleshooting.

### Active Directory

* AD DS;
* Organizational Units;
* Users;
* Groups;
* Computer Objects;
* Domain Join;
* Authentication.

### Network / Infrastructure

* DNS;
* SMB;
* NTFS;
* TCP/IP;
* Virtualização.

### Security

* RBAC;
* Controle de acesso;
* Princípio de menor privilégio;
* Gerenciamento de identidades;
* Administração centralizada.

---

# 🚀 Próximas evoluções

A infraestrutura criada neste projeto serve como base para os projetos seguintes.

O laboratório poderá evoluir para:

* GPO;
* Windows Hardening;
* Wazuh;
* Sysmon;
* Threat Hunting;
* Incident Response;
* Vulnerability Management;
* Identity & Access Management;
* Network Security;
* Corporate Penetration Testing;
* Detection Engineering;
* Security Automation.

---

# 🗂️ Estrutura do projeto

```text
01-LVM-Active-Directory/
│
├── README.md
│
├── evidencias/
│
└── relatorio/
```

---

# 🏁 Conclusão

O **Projeto 01 — Active Directory Corporate Lab** estabeleceu a infraestrutura corporativa utilizada como base para a evolução do laboratório de Cybersecurity da **LVM Technologies**.

A implementação permitiu praticar a administração de um ambiente Windows centralizado utilizando **Active Directory, DNS, usuários, grupos, computadores, RBAC, NTFS e SMB**.

A estrutura organizacional por departamentos possibilitou representar diferentes áreas de uma empresa e estabelecer uma base para controle de acesso e gerenciamento de identidades.

Além da implementação técnica, o projeto permitiu desenvolver conhecimentos fundamentais em **Windows Administration, Identity Management, Authentication, Access Control, Networking e Virtualização**.

A infraestrutura criada passou a servir como fundamento para os projetos posteriores de **Hardening, SIEM, Threat Hunting e Incident Response**.

---

## 📌 Status

```text
Projeto: Active Directory Corporate Lab
Status: Concluído
Ambiente: Laboratório corporativo virtualizado
Domínio: lvm.local
Rede: 10.10.10.0/24
DC: DC01
DNS: 10.10.10.10
Resultado: Infraestrutura AD implementada e validada
```

---

## 👨‍💻 Autor

**Leonardo Poncham**

**Foco:** Cybersecurity | Windows | Active Directory | Blue Team | SOC
