# XivDispatch architecture

The trusted Slack connector owns OAuth credentials, event delivery, rate-limit backoff and explicit write actions. A compact renderer receives selected conversations and preserves drafts locally. Bot and user identities are distinct. The first app-window-hosting route reuses the official Slack client rather than scraping private APIs. Prism and Camp consume a panel contract rather than account secrets. A public release must verify workspace permissions, publishing method and history limits against current Slack documentation.

## Acceptance before release

- Distinguish simulated state from live state in every viewer.
- Record capabilities and failures instead of claiming unsupported behavior.
- Recover after disconnect, unload or unavailable optional providers.
- Preserve explicit input ownership and deliberate write actions.
- Measure performance on the actual target devices.
- Publish exact build, platform and hardware verification records.

## Primary API references

[User and bot tokens](https://docs.slack.dev/authentication/tokens/), [Events API](https://docs.slack.dev/apis/events-api/), [history access and limits](https://docs.slack.dev/reference/methods/conversations.history/). Workspace installation and sending identity must be verified before a live client release.
