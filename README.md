# SupportLens AI Case Study

SupportLens AI is a support inbox copilot that helps teams review customer messages, retrieve policy context, draft replies, and keep a human in control before anything reaches the customer.

The source code is private. This repository documents the product, architecture, security decisions, and engineering work behind the project.

## Problem

Support teams often jump between inboxes, help-center articles, refund rules, shipping policies, warranty docs, and previous replies. Generic chatbots are not enough for this workflow because support responses need evidence, privacy controls, and human approval.

SupportLens AI was built to show how an AI assistant can fit inside a real support workflow without becoming an uncontrolled auto-responder.

## What I Built

- Support inbox review queue
- Gmail OAuth integration and message sync
- Knowledge upload for policies, FAQs, and product docs
- Retrieval workflow for finding relevant source text
- Draft reply generation with citations
- Human review before final customer response
- Gmail draft creation back into the original thread
- Admin login protection
- Encrypted OAuth token storage
- PII redaction before AI drafting
- Audit logs for integration and security changes

## Workflow

```text
Customer message
  -> inbox sync
  -> policy and FAQ retrieval
  -> PII redaction
  -> AI draft
  -> source review
  -> human approval
  -> Gmail draft
```

## Architecture

Core backend:

- FastAPI API
- PostgreSQL application database
- pgvector for retrieval
- OAuth token encryption
- Audit logging
- Auth-protected admin routes

Core frontend:

- React
- TypeScript
- Tailwind CSS
- Review queue UX
- Message detail view with draft, source, and privacy state

Runtime:

- Docker Compose local environment
- Gmail OAuth for real inbox integration
- Local demo workspace for fast walkthroughs

## Engineering Decisions

The product is built around review and control rather than automation for its own sake. The system drafts replies, but the human stays responsible for the final response.

Privacy controls are part of the main workflow instead of an afterthought. Sensitive text is redacted before drafting, token storage is encrypted, and integration changes are auditable.

## What I Owned

- Backend API design
- Gmail OAuth and message sync workflows
- AI retrieval and draft generation flow
- PII redaction and audit logging
- Admin authentication
- Review queue product flow
- Demo workspace and portfolio positioning

## Tech

- Python
- FastAPI
- PostgreSQL
- pgvector
- React
- TypeScript
- Tailwind CSS
- Docker Compose
- Gmail OAuth
- LLM APIs

## Results

SupportLens AI demonstrates practical AI engineering beyond a chatbot. It shows retrieval, source review, privacy controls, OAuth integration, auditability, and human approval inside a useful business workflow.

