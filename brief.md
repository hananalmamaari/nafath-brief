Version: NAFATH-V3

Track: Cybersecurity

## Overview

A trustworthy AI assistant for a government mobile application requires more than a language model. Software engineering provides clear API versioning and reliable updates, while AI techniques such as Retrieval-Augmented Generation (RAG) help ground responses in verified service information. Mobile security protects communication between the application and its backend, and networking ensures reliable connectivity as the number of connected devices grows. Cybersecurity addresses threats such as prompt injection, unauthorized access, and attempts to manipulate the assistant. Data management supports responsible handling of chat logs by balancing service improvement, privacy, and legal obligations. These fields must work together throughout design, development, testing, deployment, and maintenance. A failure in one area can affect the safety, accuracy, availability, or privacy of the entire service. For this project, cybersecurity is especially important because the assistant must resist malicious instructions while protecting citizens and government information.

## Software

Semantic Versioning uses three numbers: MAJOR.MINOR.PATCH. A MAJOR version increases when an incompatible API change is introduced. A MINOR version increases when new functionality is added in a backward-compatible way. A PATCH version increases when backward-compatible bug fixes are made. For a government AI assistant, following these rules helps mobile developers and backend teams understand the impact of updates and avoid unexpected service disruptions.

Resource: Semantic Versioning 2.0.0 - https://semver.org/

## AI

Retrieval-Augmented Generation (RAG) combines a language model with a retrieval system that searches trusted external information before generating an answer. For a government assistant, the system can retrieve relevant information from verified service guides and use it to construct a response. This can reduce unsupported answers by grounding generation in relevant evidence. However, RAG does not guarantee correctness; retrieved information may be outdated or incomplete, so sources and answers still require evaluation.

Resource: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks - https://arxiv.org/abs/2005.11401

## Mobile

Apple’s App Transport Security (ATS) enforces security requirements for network connections made by apps using standard URL loading APIs. It requires HTTPS connections that meet Apple’s security criteria, helping protect data in transit. If an app attempts to connect to a plain HTTP endpoint, ATS normally blocks the connection unless an applicable exception is configured. Government apps should prefer secure HTTPS endpoints and avoid weakening transport protections without a justified, carefully reviewed reason.

Resource: Preventing Insecure Network Connections - https://developer.apple.com/documentation/security/preventing-insecure-network-connections

## Networking

IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses, providing a vastly larger address space. This difference matters as smartphones, sensors, servers, and other connected devices continue to grow in number. IPv6 supports a much greater number of addressable devices and simplifies address autoconfiguration. For a government assistant, planning for IPv6 helps support future connectivity, although networks and services must be configured and secured correctly.

Resource: RFC 8200 - Internet Protocol, Version 6 (IPv6) Specification - https://www.rfc-editor.org/rfc/rfc8200

## Cybersecurity

Prompt injection occurs when malicious instructions manipulate an AI model into ignoring intended rules or performing unintended actions. Direct injection comes from a user's prompt; indirect injection is hidden in external content, such as a retrieved document or webpage. Risk can be reduced by treating retrieved content as untrusted data and by limiting the assistant's tools and permissions. Sensitive actions should also require explicit authorization and independent validation.

Resource: OWASP Top 10 for LLM Applications - LLM01: Prompt Injection - https://genai.owasp.org/llmrisk/llm01-prompt-injection/


## Data

Anonymization removes identifying information so individuals can no longer be identified by means reasonably likely to be used. Pseudonymization replaces direct identifiers with codes, but re-identification may remain possible using separately held information. Properly anonymized data falls outside personal-data protection rules where the applicable law defines it that way; pseudonymized data remains personal data. Chat logs should also be minimized, access-controlled, and retained only as long as necessary.

Resource: Regulation (EU) 2016/679 (General Data Protection Regulation) - https://eur-lex.europa.eu/eli/reg/2016/679/oj

## Misconception in My Track

A common misconception is that Retrieval-Augmented Generation (RAG) completely prevents prompt injection because the assistant uses trusted documents. In reality, retrieved documents can contain malicious instructions that manipulate the model. RAG improves access to relevant information but does not eliminate this security risk. The OWASP guidance explains that RAG does not fully mitigate prompt injection and recommends separating untrusted external content, limiting model privileges, and requiring human approval for high-risk actions.
Evidence sentence: “While techniques like Retrieval Augmented Generation (RAG) and fine-tuning aim to make LLM outputs more relevant and accurate, research shows that they do not fully mitigate prompt injection vulnerabilities.”

Resource used for evidence: OWASP Top 10 for LLM Applications - LLM01: Prompt Injection - https://genai.owasp.org/llmrisk/llm01-prompt-injection/

## Open Question

How can a government AI assistant reliably detect indirect prompt injection in retrieved service documents while keeping responses accurate and useful for citizens?
