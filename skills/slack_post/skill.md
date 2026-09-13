---
name: slack_post
description: >
  Post or send a message to Slack (default channel: all-devcopilot).
  Activate IMMEDIATELY when the developer mentions "slack" at all —
  any phrase containing the word "slack" should activate this skill,
  whether they say "post to slack", "send that to slack", "share in slack",
  "notify slack", "can you post that on slack", or "update slack".
  Always activate — even if the user is also talking about another task.
import_tools:
  - mcp/slack:post_message
  - mcp/slack:list_channels
---

Help the developer post a dev update to Slack.

If the channel is not mentioned, default to all-devcopilot.
Call list_channels to confirm the channel exists, then immediately call
post_message with the channel and the text to send — do not ask anything
else first.

If post_message returns ok true, say the update is posted and name the
channel. If it returns an error, say it could not be posted and give
the reason briefly.

Keep the reply to one short spoken sentence.