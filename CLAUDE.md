# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains an n8n workflow demonstration focused on RAG (Retrieval-Augmented Generation) capabilities. The project consists of a single n8n workflow definition that implements a conversational AI agent with vector database integration.

## Architecture

**Core Components:**
- **RAG Agent Workflow** (`RAG_Agent_Demo.json`): A complete n8n workflow demonstrating AI-powered chat with document retrieval
- **Specialized Agents** (`.claude/agents/`): Two custom Claude Code agents for specific domains

**Workflow Architecture:**
The RAG_Agent_Demo.json implements a sophisticated conversational AI pattern:
- Chat Trigger for user input reception
- RAG Agent as the central orchestrator
- OpenAI Chat Model for language processing
- Postgres Chat Memory for conversation history
- Supabase Vector Store with OpenAI Embeddings for document retrieval
- Vector Store Tool for connecting retrieval capabilities to the agent

**Key Integration Points:**
- Uses `@n8n/n8n-nodes-langchain` nodes for AI capabilities
- Integrates OpenAI for both chat and embeddings
- Supabase for vector storage with pgvector
- PostgreSQL for conversation memory persistence

## Available Agents

**n8n-agent**: Specialized for n8n workflow questions and automation tasks. Use when working with n8n-specific implementations, workflow design, or automation architecture.

**Success-Influencer**: Business strategy and personal branding agent. Use when discussing business growth, content creation, or entrepreneurial strategies.

## Workflow Development

**Working with n8n Workflows:**
- Workflow files are JSON exports from n8n instances
- Contains complete node definitions, connections, and metadata
- Can be imported directly into n8n for execution or modification

**Testing Workflows:**
- Import JSON files into a running n8n instance
- Configure required credentials (OpenAI API keys, database connections)
- Test individual nodes before running complete workflow
- Use n8n's built-in execution logging for debugging

**Key Node Types Used:**
- `@n8n/n8n-nodes-langchain.chatTrigger`: Chat interface trigger
- `@n8n/n8n-nodes-langchain.agent`: Main AI agent orchestrator  
- `@n8n/n8n-nodes-langchain.lmChatOpenAi`: OpenAI chat integration
- `@n8n/n8n-nodes-langchain.memoryPostgresChat`: Conversation memory
- `@n8n/n8n-nodes-langchain.vectorStoreSupabase`: Vector database integration
- `@n8n/n8n-nodes-langchain.toolVectorStore`: Document retrieval tool

## Dependencies

**Required External Services:**
- OpenAI API for chat and embeddings
- Supabase instance with vector storage enabled
- PostgreSQL database for conversation memory

**n8n Requirements:**
- n8n instance with LangChain nodes package installed
- Proper credential configuration for external services
- Vector store setup with appropriate embeddings model