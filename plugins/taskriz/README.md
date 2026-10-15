# Taskriz

Ask a person for something and act on their answer. With Taskriz, Claude can send someone a
request (an approval, a choice, details, a date, a file or photo) as an interface they answer
in the Taskriz app, in a browser or from an email. Their structured answer comes back to
Claude, which carries on.

## What it adds

- **The Taskriz MCP server** (`https://www.taskriz.com/mcp`), hosted by Taskriz. Its tools let
  Claude create an Agent, invite people with a pairing code or by email, design a request and
  check how it looks, send it, read the replies and any files people attach, acknowledge them,
  and withdraw a request that is no longer needed.
- **A skill** that tells Claude when and how to use them: one request and its reply at a time,
  respecting a decline, and pickers rather than asking people for links.

## Before you start

You need a Taskriz account; there is a Free plan to start. The people you ask never pay and
don't need to install an app. The first time Claude uses Taskriz, sign in through `/mcp`: choose
the taskriz server and complete the sign-in in your browser.

## What it sends, and where

The plugin runs no code on your machine. Everything goes to the Taskriz MCP server at
`https://www.taskriz.com/mcp`, over HTTPS, signed in with OAuth:

- the requests Claude writes, and who they are for (email addresses or people already
  paired with your Agent);
- files you ask Claude to attach to a request;
- the replies Claude reads back.

Taskriz delivers each request to the people it is for. How Taskriz handles this data is in the
[Privacy Policy](https://www.taskriz.com/privacy/); use is under the
[Terms of Service](https://www.taskriz.com/terms/).

## Help

See [Support](https://www.taskriz.com/support/) or email support@appeggio.com. For building
requests, see [Developers](https://www.taskriz.com/developers/).

## Licence

MIT. See [LICENSE](LICENSE).
