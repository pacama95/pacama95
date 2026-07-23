Hi, I'm Pablo 👋

I'm a Software Engineer focused on backend development, distributed systems and software architecture. Most of my experience comes from fintech environments, where I have worked on scalable services, financial products, onboarding flows, PSD2-related initiatives and backend platforms.

I enjoy building systems that combine strong engineering foundations with practical product value: clean APIs, reliable data models, event-driven thinking, cloud-native services and increasingly, AI-powered workflows.



## Portfolio Assistant System

AI-assisted investment portfolio platform built as a microservices ecosystem.

The system combines backend services, financial data ingestion, AI agents and a frontend dashboard to manage and analyze an investment portfolio.

> **Important:** This is a work in progress. Don't expect anything useful or fully functional yet.

### Frontend

- [`portfolio_assistant_front_end`](https://github.com/pacama95/portfolio_assistant_front_end)  
  React + TypeScript dashboard for portfolio visualization and interaction.  
  The frontend acts as the main entry point and consumes the portfolio, transactions, suggestions, logo, AI summary and financial news APIs.

### Core backend services

- TBD

### Supporting APIs

- [`suggestions_api`](https://github.com/pacama95/suggestions_api)  
  Stock and financial instrument suggestion API with market data integration. Called directly from the frontend.

- [`logo_api`](https://github.com/pacama95/logo_api)  
  Supporting service for stock/company logos. Called directly from the frontend.

### AI and data layer

- [`portfolio_summary_assistant`](https://github.com/pacama95/portfolio_summary_assistant)  
  Multi-agent portfolio analysis service using LangGraph, LangChain, FastAPI, SSE streaming and MCP tools. Called directly from the frontend to generate portfolio insights and summaries.

- [`financial-data-feed`](https://github.com/pacama95/financial-data-feed)  
  Financial news RAG system with RSS/API ingestion, hybrid search, Qdrant, Redis and MCP integration. Called directly from the frontend to provide portfolio-related news and market context.

### Architecture overview

```text
A slightly cleaner diagram avoiding the duplicated visual edge to `transactions-api`:

```text
+-------------------------------+
| portfolio_assistant_front_end  |
| React + TypeScript dashboard   |
+---------------+---------------+
                |
                +------------------> transactions-api
                |                         |
                |                         | feeds portfolio events
                |                         v
                +------------------> portfolio-api
                |
                +------------------> suggestions_api
                |
                +------------------> logo_api
                |
                +------------------> portfolio_summary_assistant
                |
                +------------------> financial-data-feed
