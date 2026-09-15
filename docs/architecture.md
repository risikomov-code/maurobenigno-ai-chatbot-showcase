# Architecture Notes

This document explains the engineering approach at a level suitable for technical evaluation without exposing the production implementation.

## 1. Website interaction layer

The user interacts through a website chat interface. The presentation layer is kept separate from the AI backend so that the website can evolve without coupling visual changes to assistant logic.

## 2. Assistant API

A lightweight API service receives structured requests from the website.

Typical responsibilities include:

- request validation;
- input normalisation;
- session/context handling;
- intent routing;
- model orchestration;
- controlled error responses;
- health checks.

The public showcase intentionally omits the real endpoints and schemas.

## 3. Knowledge-guided answering

The assistant can use approved business material when it is relevant to the visitor's question.

The architectural principle is:

> Retrieve or inject only relevant approved context, then ask the model to answer within that boundary.

This reduces generic answers and helps keep the assistant aligned with the actual services and expertise represented on the website.

## 4. Response controls

Before a response returns to the visitor, the system applies behavioural constraints designed to reduce:

- unsupported claims;
- invented services;
- overconfident answers;
- leakage of internal information;
- inappropriate continuation when required context is missing.

## 5. Lead-oriented conversational flow

The assistant is designed to help the visitor understand the most relevant service or next action without pretending to replace a consultant.

Examples of safe conversational outcomes include:

- clarify the visitor's market-entry objective;
- identify whether the request concerns expansion, digital growth, certification or another supported service;
- explain the relevant service category;
- suggest an appropriate human follow-up.

## 6. Separation of concerns

The production architecture separates:

- website UI;
- assistant API;
- model/provider layer;
- knowledge context;
- business rules;
- monitoring and deployment configuration.

This makes troubleshooting and replacement of individual components significantly safer.

## Engineering patterns demonstrated

- API-first AI integration
- async backend design
- explicit validation
- controlled context injection
- separation of UI and AI logic
- service health monitoring
- safe failure behaviour
- modular provider integration

## Deliberately omitted

- real API routes
- production request schemas
- prompts
- retrieval queries
- database/vector-store configuration
- model parameters
- deployment topology
- credentials
- conversation history
- business-specific qualification logic
