# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository is used to test personal Claude Code plugins from https://github.com/ragnarokkrr/ragna-claude-marketplace.git, specifically the `rgn.backend-architect` agent for architectural design work.

## Architecture Planning Context

The repository contains prompts (`prompts.txt`) for designing a microservices-based order processing system with the following specifications:

### System Design
- **Services**: Order, Payment, Inventory
- **Technology Stack**: Java Spring Boot
- **Architectural Patterns**:
  - Order Service: Hexagonal Architecture with SAGA pattern (compensating transactions)
  - Payment & Inventory Services: Vertical Slice Architecture
- **Database Strategy**: Single database per service
  - Order Service: PostgreSQL
  - Payment & Inventory: MongoDB
- **Event-Driven**: Order service emits events upon successful transaction completion

### Base Package Convention
Use `ragna.ecommerce` as the base package for all Java services.

### Git Workflow
- **Main Branch**: Production-ready code
- **Active Development Branch**: Integration branch
- **Feature Branches**: For individual features
- **Release Tags**: Mark production releases
- **Hot Fix Branches**: For urgent production fixes
- **Feature Flags**: Used for gradual feature rollout

### MVP1 Deferred Features
The following are explicitly deferred to MVP2 (see prompts.txt for ADR context):
- Payment gateway integration (using local DB transactions instead)
- Order API Gateway integration
- AVRO serialization for Kafka (using JSON)
- Security integration

When working on this codebase, consult prompts.txt for the full architectural requirements and check for any Architecture Decision Records (ADRs) that document these deferrals.

## Working with the Backend Architect Agent

To use the backend architect agent for design tasks:
```
/ragna-claude-plugins:rgn.backend-architect
```

This agent should be used for:
- Designing microservices architecture
- Creating architectural diagrams
- Documenting architectural decisions (ADRs)
- Refining system design based on patterns (Hexagonal, Vertical Slice, SAGA)
