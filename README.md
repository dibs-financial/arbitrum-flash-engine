Here are the three files ready for manual upload to  
**https://github.com/dibs-financial/DIBS-Capital-Autopilot-Controlled-Draws**

---

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

# Integrations
ESCROW_FACTORY_WEBHOOK_SECRET=
KYC_AML_PROVIDER_API_KEY=
NOTIFICATION_PROVIDER_API_KEY=

# Security
KMS_KEY_ID=
SESSION_SECRET=
```

Never commit private keys, signing keys, KMS credentials, webhook secrets, access tokens, customer documents, or production configuration.

### Run tests

```bash
pnpm lint
pnpm typecheck
pnpm test
pnpm test:integration
pnpm test:e2e
```

### Development commands

```bash
pnpm dev          # start web + API
pnpm worker:dev   # start background workers
pnpm db:migrate   # apply migrations
pnpm db:seed      # seed development data
```

---

## Core Invariant

```text
No capital-state change without:
  policy
  + evidence
  + authorization
  + settlement confirmation
  + reconciliation
  + immutable audit event
```

---

## Controlled-Draw State Machine (MVP)

```text
DRAFT
  → SUBMITTED
  → UNDER_REVIEW
  → HELD
  → APPROVED
  → SETTLEMENT_INSTRUCTED
  → SETTLEMENT_CONFIRMED
  → RECONCILED
  → CLOSED
```

---

## Status

- Architecture and MVP specification
- Quantum Optimization Lab and Post-Quantum Cryptography research scaffold complete
- **Deployment rule:** Do not use production capital, custody, tokenization, insurance, securities, lending, QOF/QOZ, or DeFi workflows until applicable legal, tax, compliance, security, servicing, custody, and independent-review gates are satisfied.

---

## Related Repository

The broader monorepo and implementation work lives at:  
[dibs-financial/dibs-trust-capital-network](https://github.com/dibs-financial/dibs-trust-capital-network)

---

## License & Contributing

See the parent project for contribution guidelines, security policy, and compliance notice.
```

---

### 2. `docs/QUANTUM-AND-PQC-SCAFFOLD.md`

Local path:  
`/home/workdir/artifacts/DIBS-Capital-Autopilot-Controlled-Draws/docs/QUANTUM-AND-PQC-SCAFFOLD.md`  
(422 lines)

### 3. `DIBS-Capital-Autopilot.md` (root)

Local path:  
`/home/workdir/artifacts/DIBS-Capital-Autopilot-Controlled-Draws/DIBS-Capital-Autopilot.md`  
(1 613 lines)

---

### Manual upload steps on GitHub

1. Go to https://github.com/dibs-financial/DIBS-Capital-Autopilot-Controlled-Draws  
2. **README.md** → click the pencil (Edit) or “Add file” → paste the README content above → Commit.  
3. **DIBS-Capital-Autopilot.md** → “Add file” → “Create new file” → name it `DIBS-Capital-Autopilot.md` → paste contents (or upload the file).  
4. **docs/QUANTUM-AND-PQC-SCAFFOLD.md** → “Add file” → create folder `docs` if needed → name the file `QUANTUM-AND-PQC-SCAFFOLD.md` → paste or upload.

Would you like me to output the **full text** of `QUANTUM-AND-PQC-SCAFFOLD.md` and/or `DIBS-Capital-Autopilot.md` here so you can copy-paste them directly?
