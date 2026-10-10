---
name: taskriz
description: Ask a person for something through Taskriz and act on their answer: an approval, a choice, details, a file or photo, or sending them something to review. Use when the user wants to ask, check with, collect from or get sign-off from someone else (by name or email), or to see what someone has answered.
---

# Asking a person through Taskriz

Taskriz delivers a request to a person as an interface they answer in the Taskriz app, a
browser or by email. Their answer comes back to you. Use the `taskriz` MCP tools.

## The loop

1. **Choose the Agent.** Requests are sent from an Agent in the user's Taskriz account. Call
   `list_agents` and ask the user which one to use, or create one with `create_agent`.
2. **Choose the recipients.** `list_recipients` lists who the Agent can already reach. Someone
   not yet paired can be named by email: they are emailed an invitation, and the request waits
   until they accept it. An account can invite only a limited number of different people, so
   confirm the email address with the user first.
3. **Write the interface.** Read `get_ui_guide` before writing the first interface in a
   session. Interfaces are Smalltalk Morphs, laid out following Apple's Human Interface
   Guidelines. To ask for a file or photo, use a `DocumentPickerMorph` or `PhotoPickerMorph`,
   never a field for a link.
4. **Check it.** Run `check_ui` and fix any error. Its plain-text preview shows what the
   person will see.
5. **Send it** with `send_request`. Files to send go in `attachments` (from
   `create_attachment`). Use `thread` to continue an earlier conversation.
6. **Wait for the answer.** `get_replies` returns replies, requests people started, and what
   became of invitations. Pass `wait_seconds` to wait for something to arrive. Files in a reply
   are fetched with `get_attachment`.
7. **Acknowledge** each event once it's handled, with `acknowledge`, so it isn't offered
   again.

Withdraw a request that no longer needs an answer with `recall_request`.

## Respect a decline

If someone declines an invitation, tell the user. Never create another Agent, or find
another route, to reach a person who declined.

## Signing in

The first time, the `taskriz` server needs the user to sign in to their Taskriz account. If
the tools aren't available, ask the user to run `/mcp`, choose the taskriz server and complete
the sign-in in their browser.
