# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Zeabur deployment template for Supabase with Traditional Chinese localization. The template deploys a complete enterprise-grade Supabase stack consisting of 8 interconnected services.

## Core Template File

- `supabase-enhanced.yaml` - Main template definition (512 lines) containing complete service architecture
- Template follows Zeabur v1 specification with services under `spec.services`

## Essential Commands

### Template Management
```bash
# Authenticate first
npx zeabur auth login

# Create/publish template  
npx zeabur template create -f supabase-enhanced.yaml

# Deploy template to project
npx zeabur template deploy -f supabase-enhanced.yaml --project-id PROJECT_ID

# Update existing template
npx zeabur template update -c CODE -f supabase-enhanced.yaml
```

### Validation
- No standalone validate command exists in Zeabur CLI
- Use deploy command to validate template structure
- Check YAML syntax manually if needed

## Architecture

The template deploys 8 services with specific dependency chain:
```
Kong (API Gateway) ← Studio (Management UI)
Kong ← Database, Meta, REST, Auth, Storage, Realtime  
Storage ← Database, MinIO
Meta, REST, Auth, Realtime ← Database
```

Key services:
- **Database**: PostgreSQL 17.4 (primary data store)
- **Kong**: API Gateway (single entry point at port 8000)
- **Studio**: Supabase management dashboard
- **Auth**: GoTrue authentication service
- **REST**: PostgREST API
- **Storage**: File storage with MinIO backend
- **Realtime**: WebSocket subscriptions

## Configuration Variables

Template requires 3 user inputs:
- `SUPABASE_DOMAIN`: Domain for the deployment
- `ADMIN_USERNAME`: Studio admin username  
- `ADMIN_PASSWORD`: Studio admin password

## Localization

Includes `zh-TW` localization section with:
- Translated service descriptions
- Chinese variable names and descriptions
- Taiwan-specific documentation

## Template Schema Requirements

- Must have `services` under `spec.services` (not at root level)
- Avoid additional metadata properties beyond standard Zeabur schema
- Use proper dependency declarations between services
- Environment variable references use `${VAR_NAME}` syntax

## Git Status

Current changes:
- Modified: `supabase-enhanced.yaml` 
- Untracked: `README.md`

Successfully uploaded template code: LXL5G9