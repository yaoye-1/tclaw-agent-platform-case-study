# Demo Script

This repository is a case study, not a runnable copy of the company deployment. Use the following structure for a screen recording or live interview with permission.

## 1. Architecture

Show the WebSocket path:

1. Client connects with JWT.
2. Server assembles Agent context.
3. Model streams text.
4. Model requests a tool.
5. Server executes the tool.
6. Tool result returns to the model.
7. Final answer is streamed and persisted.

## 2. Enterprise login

Show the OIDC sequence:

1. Generate state, nonce and PKCE challenge.
2. Redirect to the enterprise IdP.
3. Validate callback state.
4. Exchange the authorization code.
5. Verify ID token and UserInfo.
6. Resolve tenant binding.
7. Issue the platform JWT.

Do not show real tenant names, IDs, claims or provider URLs.

## 3. Governed data access

Show a bounded MCP action such as “get department headcount” and explain:

- Why it is not a raw SQL tool
- How actor identity is injected server-side
- How tenant filtering and output filtering work
- What is logged

## 4. Structured artifact

Select an output mode and show the result moving through:

```text
Model output -> Function Calling tool -> workspace file -> preview/editor -> export
```

## 5. Failure handling

Show or explain one failure:

- Empty tool arguments are rejected.
- A tool error is returned to the model.
- A loop reaches its maximum round count.
- A path attempts to escape the workspace.
- Model quota is exhausted.

## Boundary statement

> The open-source platform provides the Agent runtime and MCP framework. My contribution is the enterprise integration and productization layer. The public repository contains sanitized architecture documentation rather than proprietary source code.
