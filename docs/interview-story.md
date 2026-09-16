# Interview Story

## 30-second positioning

I worked on an enterprise multi-agent platform based on the open-source Clawith codebase. The runtime and MCP framework came from the open-source base. My work focused on enterprise delivery: OIDC login, tenant identity binding, governed MCP tools, six structured content tools, workspace isolation and multi-tenant governance.

## 90-second project story

The platform gives each Agent a persistent identity, memory, workspace, tools and collaboration relationships. Users interact through WebSocket, IM channels or scheduled triggers.

One of the hardest parts was not calling the model. It was making the Agent safe and usable in an enterprise setting. I worked on the external OIDC login flow, including PKCE, state, nonce, ID-token verification, UserInfo cross-checking and tenant identity binding.

For data access, I helped expose bounded business actions as MCP tools instead of a universal database query. The server resolves the authenticated tenant and enforces permission checks.

For content delivery, we added six Function Calling output tools so the model could produce documents, mind maps, slides, quizzes, video scripts and webinar outlines. Users could preview, edit and export these files from the workspace.

I also worked on workspace isolation to prevent different sessions from reading or overwriting each other's files, and on governance features such as quotas, model fallback and audit-related behavior.

## Deep-dive checklist

- Draw the WebSocket-to-tool-loop sequence.
- Explain state, nonce and PKCE separately.
- Explain why the server must not trust model-provided tenant IDs.
- Explain how a tool result is returned to the model.
- Explain why an Agent loop needs a maximum round count and quota stop.
- Explain workspace path traversal protection.
- Explain why chat output alone is not a deliverable.

## Honest boundaries

- Do not claim the Clawith runtime was written from scratch.
- Do not claim company code can be published.
- Do not claim production quality for the in-memory OIDC state store.
- Explain which governance capabilities came from the base and which were extended.
