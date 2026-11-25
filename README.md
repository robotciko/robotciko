# Veriznode

Validator and RPC infrastructure. Running nodes across mainnet and testnet networks:
systemd units, key management, snapshot handling, monitoring.

**Operator:** Francisco · [veriznode.xyz](https://veriznode.xyz) · francisco@veriznode.xyz

---

### Repositories

| | |
|---|---|
| [**flop-devnet-rpc**](https://github.com/robotciko/flop-devnet-rpc) | Keyless FLOP devnet RPC replica — runbook, pinned inputs (image digest, chain spec sha256, genesis, peer ID), snapshot restore procedure, sync and restart proof against the reference endpoint |
| [**veriznode-infra**](https://github.com/robotciko/veriznode-infra) | Validator and RPC operations — host layout, operational conventions, health check script |

---

### Infrastructure

| Host | Role |
|---|---|
| `veriznode-kii` | validators + RPC (multi-network) |
| `veriznode-flop` | FLOP devnet RPC replica (archive) |

Ubuntu 24.04 LTS on KVM. Validators under systemd units; RPC replicas as Docker Compose
projects. Every chain binary is pinned and version-checked against the chain's required
upgrade height before restart, and every snapshot is hash-verified against the chain's
expected genesis before use.

### Networks

Kiichain · Safrochain · Asentum · Espresso · FLOP

---

*No keys, seeds, tokens or enrollment material are stored in any public repository here.*
