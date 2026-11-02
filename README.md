# 👋 Olá, eu sou Benne - Benedito Santana

**Desenvolvedor .NET Sênior · Arquitetura SaaS multi-tenant · .NET 10 + Angular 21 + PostgreSQL**

Mais de 12 anos construindo sistemas corporativos de missão crítica — crédito consignado, mercado
financeiro, telecom — e, desde 2026, arquitetando e entregando do zero duas plataformas SaaS
multi-tenant, uma delas em produção. Engenharia guiada por especificação, isolamento de dados como
fato mecânico e IA generativa (Claude) como par de arquitetura, revisão e auditoria.

---

## 📚 Sobre mim

- 🎓 **Formação:** Universidade Cruzeiro do Sul
- 💼 **Hoje:** **IEBT Innovation**, prestando serviço ao **Banco Rendimento**
- 🏢 **Arquitetura:** **Way One ERP**, na **Wayvis International**
- 🚀 **Produto próprio:** **Agenda SST** — no ar em [agendasst.com.br](https://agendasst.com.br)
- 📍 São Paulo, Brasil · híbrido ou remoto
- 🔎 Aberto a oportunidades

---

## 📈 Projetos em destaque

### 🏦 Banco Rendimento — pela IEBT Innovation

> *Especialistas em tecnologia e inovação, impulsionados por IA.*
> **Respiramos tecnologia, materializamos o futuro e transformamos organizações.**

| **+16** anos no mercado | **+200** profissionais de tech e inovação |
|---|---|

A **[IEBT Innovation](https://www.iebtinnovation.com/)** atua na interseção entre estratégia,
inovação, dados, cultura e digital, como parceira estratégica que une negócios e tecnologia para
transformar com impacto real. Atende grandes organizações públicas e privadas em **IA e dados**,
**engenharia de software** (soluções digitais completas e modernização), **consultoria de
inovação e P&D** e aceleração de startups, com unidades em Belo Horizonte, Vitória da Conquista,
Santo André e Manaus.

Pela IEBT, presto serviço ao **[Banco Rendimento](https://www.rendimento.com.br)**, instituição
especializada em **câmbio,
crédito e soluções de pagamentos**:

- **Soluções de pagamento** — maquininha **Rendimento Pay**, Pix em compras no exterior e
  automação de pagamentos recorrentes, como comissões de imobiliárias e incorporadoras.
- **Câmbio** — para pessoas e empresas: importação, exportação, investimento no exterior, hedge com
  NDF e **APIs de câmbio e white label** para parceiros.
- **Conta Não Residente** — conta para brasileiros e estrangeiros domiciliados no exterior, com
  IBAN e SWIFT para transferências internacionais.
- **Google AdSense** — recebimento em reais dos pagamentos internacionais de criadores e
  publicadores.
- **Segurança** — orientação ao cliente e proteção das transações.

Domínio financeiro regulado, de alta disponibilidade, em que integração e segurança da informação
não são opcionais — continuidade dos anos de crédito consignado e mercado financeiro.

### 🏢 Way One ERP — Wayvis International

Plataforma SaaS corporativa multi-tenant que governa organizações, holdings, empresas, filiais,
revendas e clientes em um único ecossistema.

- **Arquitetura congelada antes do código** — documentation-as-code: domínios (DOM), decisões (ADR),
  modelos de dados (DM) e guias governam o código, nunca o contrário; ADR aceito é imutável.
- **Bounded contexts** em Clean Architecture + DDD + CQRS: Identidade, Sessão, Organização,
  Autorização, Comercial, Contratos, Licenciamento, Faturamento, Financeiro, Notificação,
  Configuração, Segurança, Observabilidade e Auditoria.
- **Autorização multidimensional** (estrutural, operacional, comercial e temporal) no modelo
  Subject–Relationship–Time, com projeções de leitura.
- Autenticação com JWT, MFA/TOTP, recuperação de senha, federação e multi-vínculo.
- PostgreSQL com RLS e migrations forward-only; observabilidade com OpenTelemetry e Serilog.
- Método **BMAD + XP** — **2.150+** commits desde 06/2026.

### 🦺 Agenda SST — [agendasst.com.br](https://agendasst.com.br)

SaaS multi-tenant para prestadoras de treinamento em Segurança e Saúde do Trabalho: agenda cursos
de NR, aloca funcionários em turmas, controla a lista de presença, emite certificados e monitora
validades e reciclagens. **Em produção desde 09/2026**, operando sobre a base real de um cliente
(empresas × funcionários × vencimentos).

| | |
|---|---|
| Stack | .NET 10 · ASP.NET Core Minimal APIs · EF Core · Angular 21 (signals, zoneless) · PrimeNG · PostgreSQL 18 |
| Nuvem | Google Cloud — Cloud Run, Cloud SQL, Cloud Build, Secret Manager, balanceador com TLS gerenciado |
| Isolamento | Row-Level Security `FORCE` fail-closed, aplicação sem `BYPASSRLS`, FKs compostas com `tenant_id`, bateria de 25 testes de isolamento no CI |
| Escala do código | **274** migrations forward-only com checksum · **382** rotas de API, todas com gate declarado · **~2.480** testes de backend (xUnit) · **~1.550** de frontend |
| Processo | **392** changes especificadas e arquivadas com **OpenSpec** · **2.200+** commits em ~3 meses |
| Entrega | CI com 5 jobs obrigatórios; avançar a branch `producao` publica e confere o commit no ar |

Destaques de engenharia: autorização por catálogo Recurso × Ação (PDP fail-closed), menu dirigido
por dados, log e auditoria particionados por tempo com retenção automática, banco que sobe sem
superusuário (Cloud SQL), datas de negócio no fuso de Brasília sobre servidor em UTC, importação de
planilhas reais do cliente (xlsx) com relatório do que entrou, do que não entrou e por quê.

> Os dois repositórios são privados. Posso apresentar o código e as decisões em uma conversa técnica.

---

## 🧠 O que essas jornadas me ensinaram

- **Especificação antes do código.** Toda mudança de schema, API ou autorização nasce como change
  revisada (proposta, tarefas, deltas de spec); a spec é a norma, o histórico é contexto.
- **Isolamento se prova, não se declara.** RLS, papéis de banco e políticas se testam
  mecanicamente a cada build — com dois tenants no mesmo teste.
- **O verde não prova tudo.** Saber o que cada gate do CI *não* cobre vale tanto quanto o gate.
- **Migrations são uma porta de mão única.** Forward-only, com checksum; correção vira migration nova.
- **A tela nasce de um mock aprovado.** O protótipo é o contrato de UX até a tela existir.
- **Dado real do cliente é ativo central** — importar, reconciliar e informar o que divergiu, em vez
  de rejeitar em silêncio.
- **IA como par de engenharia:** agentes Claude em worktrees isoladas, com regras de repositório,
  skills de auditoria e exigência de evidência (`arquivo:linha` ou comando + saída) em cada afirmação.

---

## 🚀 Habilidades técnicas

**Backend:** C# · .NET 10 · ASP.NET Core · Minimal APIs · EF Core · LINQ · xUnit · WCF · Web Forms
· .NET Framework

**Frontend:** Angular 21 · TypeScript · RxJS · Signals · PrimeNG · Tailwind CSS · Karma/Jasmine

**Banco de dados:** PostgreSQL (RLS, particionamento, `plpgsql`) · SQL Server · T-SQL · Stored
Procedures · Oracle

**Arquitetura:** DDD · Clean Architecture · CQRS · multi-tenancy · ADR · REST · JWT/OAuth

**Infra e DevOps:** Docker · Google Cloud (Cloud Run, Cloud SQL, Cloud Build) · GitHub Actions ·
CI/CD · Jenkins · Git

**Observabilidade:** OpenTelemetry · Serilog

**Processo e IA:** OpenSpec · BMAD · XP · Claude Code · ChatGPT

<p>
  <img src="https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white" alt=".NET" />
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white" alt="C#" />
  <img src="https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white" alt="Angular" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white" alt="SQL Server" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Google%20Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white" alt="Google Cloud" />
  <img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/OpenTelemetry-425CC7?style=for-the-badge&logo=opentelemetry&logoColor=white" alt="OpenTelemetry" />
  <img src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white" alt="Claude" />
</p>

---

## 💼 Trajetória

| Período | Empresa | Atuação |
|---|---|---|
| 2026 – hoje | **IEBT Innovation** | Prestação de serviço ao Banco Rendimento — câmbio, crédito e pagamentos |
| 2026 – hoje | **Wayvis International** | Arquitetura e desenvolvimento do Way One ERP (SaaS multi-tenant) |
| 2026 – hoje | **Agenda SST** (produto próprio) | Concepção, arquitetura, desenvolvimento e operação em produção |
| 2018 – 2025 | **Consiglog Tecnologia e Soluções** | Crédito consignado: convênios, contratos, margens, folha; integrações com bancos; SQL de alta performance |
| 2014 – 2017 | **Resource IT Solutions** | Itaú (LCR, liquidez e risco), UBS (Billing Delivery — WCF, Oracle), Banco Volkswagen (remediação de vulnerabilidades OWASP em legado) |
| 2013 – 2014 | **Informatec** | ColetorIP: coleta de bilhetes de centrais telefônicas via FTP, SFTP, Telnet, TFTP, socket e e-mail |

---

## 📊 GitHub

<p>
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=BDSant&show_icons=true&count_private=true&theme=tokyonight&hide_border=true&locale=pt-br" alt="Estatísticas do GitHub" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=BDSant&layout=compact&theme=tokyonight&hide_border=true&locale=pt-br" alt="Linguagens mais usadas" />
</p>

---

## 🌐 Conecte-se comigo

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/benedito-santana-filho/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/BDSant)
[![Agenda SST](https://img.shields.io/badge/Agenda%20SST-no%20ar-2E7D32?style=for-the-badge)](https://agendasst.com.br)

*Construo software que precisa funcionar no dia seguinte — e explico por que funciona.*
