# ProtoJoint for AI apps (MCP)

[ProtoJoint](https://protojoint.ai) is a parametric CAD that runs in the browser. Its MCP server lets an AI app such as Claude, Cursor or Gemini CLI model in the design that is open in your own ProtoJoint tab: constrained sketches and named dimensions, features, standard parts, assemblies and joints, laser-cut boxes with finger joints, and robot export as URDF, MJCF, SDF and a ROS 2 package.

This repository holds only the description and configuration needed to connect an AI app to it. It contains no product code: ProtoJoint's editor, its server and its built-in AI assistant, Eleph, are closed source.

**Status: private beta.** Accounts are by invite. [Request an invite](https://protojoint.ai/app/#waitlist). Modelling and every export work without an account; connecting an AI app does need one.

- MCP server: `https://protojoint.ai/mcp` (Streamable HTTP)
- Sign-in: OAuth 2.1, found by the AI app from the server's 401 answer (dynamic client registration, PKCE S256); an API key for clients that take a header
- Tools: 54, of which 12 only read ([docs/tools.md](docs/tools.md))
- Documentation: <https://protojoint.ai/docs/ai/>

## Before an AI app can do anything: five steps

Every tool call that reads or changes the design runs in your open ProtoJoint tab, on the design open there. So:

1. **Sign in** at <https://protojoint.ai/app/> (the AI features need a confirmed email address).
2. **Have MCP calls**: a Maker, Pro or Max plan or, on a free account, share your designs and AI sessions in **Account › Privacy** (a free account shares only its designs unless you chose otherwise, and in the EU, UK, Switzerland and Quebec nothing at all, which gives no MCP calls; the choice is called **My designs and AI sessions**). See [what it costs](#what-it-costs).
3. Open the account menu, under your initial at the right of the header, and choose **AI connections…**
4. Turn on **Let AI apps control this tab**.
5. **Keep that browser tab open** while the AI app works. It can be in the background. If you have several ProtoJoint tabs open, the one you focused last answers.

Then add the server to your AI app: [docs/clients.md](docs/clients.md) has Claude (claude.ai and Desktop, Claude Code), Cursor and Gemini CLI. With no such tab open, a tool call returns an error that says what to do, not a generic failure.

## What an AI app can do

Model in the open design, one undo step per edit: sketch and constrain, extrude, revolve, sweep, loft, fillet and the rest of the features, insert parts from ProtoJoint's library (servos, boards, motors, wheels, rails and more), make parts, add joints and move them, check interference and motion, read mass properties, make a laser-cut box with finger joints, and export a design as STEP or STL or a robot as URDF, MJCF, SDF and a ROS 2 package. The full list is in [docs/tools.md](docs/tools.md).

## What it costs

Modelling, importing, exporting and saving are free and need no account. Connecting an AI app over MCP needs an account with MCP calls: a paid plan, or a free account that shares its designs and AI sessions. It uses no credits, because the AI app you connect is paid for by you. As of 2026-11-17, during the private beta (US dollars, plus any sales tax that applies; prices may change; see <https://protojoint.ai/pricing/>):

| Plan | Price a month (contributor / private) | MCP calls a month |
|---|---|---|
| Maker | $9 / $12 | 100 |
| Pro | $29 / $36 | 100 |
| Max | $99 / $119 | no monthly count (fair use) |
| Free account that shares its designs and AI sessions | $0 | 100 |
| Free account that does not | $0 | none |

The contributor's price is for a member who shares their designs and AI sessions to improve ProtoJoint's AI (never to train models); the private price is for one who does not.

## Privacy

What ProtoJoint keeps of a tool call, and for whom, is in the [privacy policy](https://protojoint.ai/legal/privacy.html), under "Your designs" and "Contributing designs and AI sessions". The results of a call, screenshots included, go to the AI app you connected, not to ProtoJoint's AI provider.

## Licence

The text and configuration in this repository are under the [MIT licence](LICENSE). That covers these files only: not ProtoJoint, its server or Eleph, and not the ProtoJoint name or logo.

## Support

<support@protojoint.ai> · <https://protojoint.ai/feedback/> · [Discord](https://discord.gg/dNsyPY2exM)
