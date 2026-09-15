# Upwork Case Study

## AI Website Assistant for a Consulting Business

### Business problem

A consulting website can contain extensive information about services, markets and expertise, but visitors still need to determine which information applies to their own situation.

Static navigation and contact forms create friction: the visitor must understand the service structure before they can ask the right question.

### Objective

Create an AI assistant that can act as an intelligent first interaction layer while remaining controlled by approved business context.

The assistant needed to be useful without becoming an uncontrolled general-purpose chatbot.

### Solution

I designed a website AI-assistant architecture with a dedicated backend service that:

- receives visitor questions through an API;
- validates and normalises the request;
- uses relevant approved context when available;
- sends a bounded request to an LLM;
- applies response constraints;
- returns a structured answer to the website;
- keeps the AI logic independent from the front-end interface.

### Key design decisions

**Knowledge before improvisation**

Where relevant approved information exists, the assistant should use that information instead of relying only on the model's general knowledge.

**Backend isolation**

AI logic is kept outside the WordPress/front-end layer. This improves maintainability, security and troubleshooting.

**Controlled uncertainty**

When the assistant does not have enough context, it should avoid inventing specific facts or services.

**Business-oriented routing**

The conversation can help visitors identify the relevant service or next step while preserving the role of human consulting for substantive business decisions.

**Security boundary**

Credentials, prompts, infrastructure details, knowledge-base data and production configuration remain private.

### Outcome

The project demonstrates how a professional-services website can add conversational AI without turning the website itself into an unmaintainable AI application.

The architecture is reusable for:

- consulting firms;
- B2B service companies;
- professional practices;
- knowledge-driven businesses;
- internal or external information assistants.

### Skills demonstrated

Python · FastAPI · REST APIs · LLM Integration · AI Chatbots · RAG Concepts · Knowledge-Guided Responses · WordPress Integration · Prompt Architecture · Input Validation · API Troubleshooting · AI Automation
