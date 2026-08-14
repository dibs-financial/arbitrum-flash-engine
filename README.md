### 1. `README.md` (root)

```markdown
# DIBS Capital Autopilot — Controlled Draws

**Capital cannot move until the right policy, evidence, approvals, and covenant checks are satisfied.**

This repository holds the architecture and research scaffold for **DIBS Capital Autopilot**, a multi-tenant, policy-enforced capital-control platform focused on controlled-draw workflows for private lenders, construction lenders, debt funds, real-estate sponsors, fund administrators, and deal-specific SPVs.

---

## Core Documents

| Document | Description |
|----------|-------------|
| [`DIBS-Capital-Autopilot.md`](./DIBS-Capital-Autopilot.md) | Full product & architecture specification: state machines, data model, policy engine, evidence, covenants, settlements, audit ledger, SPV Factory, Base44 Super Agents, post-quantum security, Quantum Optimization Lab, repository layout, API design, security controls, pilot plan, and roadmap. |
| [`docs/QUANTUM-AND-PQC-SCAFFOLD.md`](./docs/QUANTUM-AND-PQC-SCAFFOLD.md) | Consolidated research scaffold covering QAOA/QUBO, constraint-preserving XY-mixers, Dicke-state preparation, ML-KEM/ML-DSA, HQC, BIKE (BGF decoder, DFR, absorbing sets), QCSD hardness, parameter tables, and integration roadmap. |

---

## Quick Start

### Prerequisites

```text
Node.js 20+
pnpm 9+
Docker and Docker Compose
PostgreSQL 16+
S3-compatible object storage (or local MinIO)
OIDC provider configuration
```

### Bootstrap (implementation monorepo)

The runnable application lives in the companion monorepo. Clone and start it as follows:

```bash
git clone https://github.com/dibs-financial/dibs-trust-capital-network.git
cd dibs-trust-capital-network

corepack enable
corepack prepare pnpm@latest --activate

pnpm install
cp .env.example .env

docker compose up -d postgres minio
pnpm db:migrate
pnpm db:seed
pnpm dev
```

### Essential environment variables

```bash
# Application
NODE_ENV=development
APP_URL=http://localhost:3000
API_URL=http://localhost:4000

# Database
DATABASE_URL=postgresql://dibs:dibs@localhost:5432/dibs

# Object storage
S3_ENDPOINT=http://localhost:9000
S3_BUCKET=dibs-evidence
S3_ACCESS_KEY=
S3_SECRET_KEY=

# Authentication
OIDC_ISSUER_URL=
OIDC_CLIENT_ID=
OIDC_CLIENT_SECRET=

# Audit and signing
AUDIT_SIGNING_KEY_ID=
AUDIT_SIGNING_PROVIDER=
MLDSA_SIGNING_KEY_ID=
# DIBS Capital Autopilot — Controlled Draws

**Capital cannot move until the right policy, evidence, approvals, and covenant checks are satisfied.**

This repository holds the architecture and research scaffold for **DIBS Capital Autopilot**, a multi-tenant, policy-enforced capital-control platform focused on controlled-draw workflows for private lenders, construction lenders, debt funds, real-estate sponsors, fund administrators, and deal-specific SPVs.

---

## Core Documents

| Document | Description |
|----------|-------------|
| [`DIBS-Capital-Autopilot.md`](./DIBS-Capital-Autopilot.md) | Full product & architecture specification: state machines, data model, policy engine, evidence, covenants, settlements, audit ledger, SPV Factory, Base44 Super Agents, post-quantum security, Quantum Optimization Lab, repository layout, API design, security controls, pilot plan, and roadmap. |
| [`docs/QUANTUM-AND-PQC-SCAFFOLD.md`](./docs/QUANTUM-AND-PQC-SCAFFOLD.md) | Consolidated research scaffold covering QAOA/QUBO, constraint-preserving XY-mixers, Dicke-state preparation, ML-KEM/ML-DSA, HQC, BIKE (BGF decoder, DFR, absorbing sets), QCSD hardness, parameter tables, and integration roadmap. |

---

## Quick Start

### Prerequisites

```text
Node.js 20+
pnpm 9+
Docker and Docker Compose
PostgreSQL 16+
S3-compatible object storage (or local MinIO)
OIDC provider configuration
