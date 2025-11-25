# Order Architecture with Backend Architect Agent

Testing repository for Claude Code plugins from [ragna-claude-marketplace](https://github.com/ragnarokkrr/ragna-claude-marketplace.git), specifically the `rgn.backend-architect` agent.

## Project Overview

Microservices-based order processing system design with:
- **Services**: Order, Payment, Inventory (Java Spring Boot)
- **Base Package**: `ragna.ecommerce`

## Architecture

- **Order Service**: Hexagonal Architecture + SAGA pattern (compensating transactions), PostgreSQL
- **Payment & Inventory**: Vertical Slice Architecture, MongoDB
- **Event-Driven**: Order service emits events on successful transactions
- **Database Strategy**: Single database per service

## Git Workflow

- Main branch (production)
- Active development branch (integration)
- Feature branches with release tags
- Hot fix branches for urgent fixes
- Feature flags enabled

## MVP1 Scope

Deferred to MVP2:
- Payment gateway integration (using local DB transactions)
- Order API Gateway
- AVRO serialization (using JSON)
- Security integration

## Usage

Design with backend architect agent:
```bash
/ragna-claude-plugins:rgn.backend-architect
```

See `prompts.txt` for detailed requirements and `CLAUDE.md` for complete context.
