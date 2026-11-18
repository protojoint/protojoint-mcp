# ProtoJoint

ProtoJoint is a parametric CAD that runs in the browser. Its tools act on the design open in the user's own ProtoJoint tab, so before a call can work the user needs to have:

1. signed in at https://protojoint.ai/app/ with a confirmed email address,
2. MCP calls on the account: a Maker, Pro or Max plan or, on a free account, designs and AI sessions shared in **Account › Privacy** (a free account shares only its designs unless the user chose otherwise, which gives no MCP calls),
3. opened **AI connections** from the account menu and turned on **Let AI apps control this tab**,
4. kept that browser tab open (it can be in the background).

If a call returns an error about a missing tab or missing MCP calls, say so to the user and tell them these steps. Accounts are by invite during the private beta; modelling and every export work without an account, connecting an AI app does not.

How to work in it:

- Read the design first (`get_document`) and look at it (`screenshot`) before changing anything. Every edit is one undo step the user can take back.
- Model in sketches with constraints and named dimensions, then features; use `set_parameter` to change a dimension rather than redrawing.
- Take standard parts (servos, boards, motors, wheels) from the library with `insert_part` instead of drawing them.
- Check what you made: `check_interference` for clashes, `check_motion` for joints, `mass_properties` for mass.
- `new_document` replaces the open design, and `delete_feature`, `delete_part` and `delete_joint` remove things: ask the user before using any of them.
- For a whole machine, give the user the spec you would build and ask before you start.
