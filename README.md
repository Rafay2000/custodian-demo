# custodian-demo

A custom cloud-based testing demo repository for the unit CAB432. It follow the Assignment 2 "Repository Custodian" AI agent which is a
cloud-native agent that automatically triages new GitHub issues, reviews open issues on a
schedule, and answers questions about this project using retrieval over its own documentation.

**Author:** Rafay Akbani

## What this repo is for

This repository exists as a lightweight target for the Repository Custodian agent to operate
on. When an issue is opened here, it's automatically triaged by an AI model (severity, labels,
summary) and stored. A scheduled job also reviews open issues hourly and can comment on ones
that need attention, using context pulled from the docs in this repo.

## Structure

- `docs/setup.md` — installation and configuration requirements
- `docs/troubleshooting.md` — common problems and fixes
- `README.md` — this file

## Related project

The actual agent infrastructure (Lambda functions, MCP server, vector store, chat agent) lives
in a separate AWS deployment and is not part of this repository. This repo is just the data
source it triages and searches over. Hence it is only used for testing purposes.
