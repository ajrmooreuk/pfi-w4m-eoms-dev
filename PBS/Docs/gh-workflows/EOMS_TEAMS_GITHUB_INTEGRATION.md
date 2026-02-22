# EOMS — GitHub ↔ Microsoft Teams Integration

**Status:** In Progress — connected but experiencing errors
**Date:** 22 February 2026

---

## What We're Trying to Do

Get automatic notifications in a Teams chat/channel when PRs are merged into the EOMS test and prod repos. This gives the client visibility of promotions without needing to check GitHub.

---

## Current Setup

### GitHub App in Teams (Installed)

The GitHub app was installed in Teams and authenticated:

```
✅ Login was successful! Amanda J R Moore is now connected to @ajrmooreuk.
```

### Subscriptions Created

| Repo | Subscribed | Status |
|------|-----------|--------|
| `ajrmooreuk/pfi-w4m-eoms-test` | Yes | Errors — see issues below |
| `ajrmooreuk/pfi-w4m-eoms-prod` | Not yet | Pending — resolve test issues first |
| `ajrmooreuk/pfi-w4m-eoms-dev` | Not yet | Optional — advisory use only |

### Connection Type

- **1-to-1 chat** with the GitHub bot in Teams (not a channel)
- Cards rendering as "Card - access it on https://go.skype.com/cards.unsupported" — this is the primary issue

---

## Known Issues

### 1. Cards Not Rendering

**Symptom:** Every response from the GitHub bot shows:
```
Card - access it on https://go.skype.com/cards.unsupported
```

**Likely Causes:**
- The Teams client (desktop or web) does not support Adaptive Cards in 1-to-1 bot chats
- Tenant policy may restrict third-party app card rendering
- Teams version may need updating

**To Investigate:**
- [ ] Try the same commands in a **Teams channel** (not 1-to-1 chat) — channels have better card support
- [ ] Check if the Teams desktop app is up to date
- [ ] Try Teams web client (https://teams.microsoft.com) to see if cards render there
- [ ] Check tenant admin settings: Teams Admin Centre → Messaging policies → allow third-party apps / URL previews
- [ ] Check if the GitHub app needs permissions granted by a Teams/M365 admin

### 2. 1-to-1 Chat Limitations

The GitHub Teams app works best in **channels**, not 1-to-1 chats. Microsoft's documentation recommends using channels for bot subscriptions.

**Recommended Fix:** Create a private Teams channel (e.g. "EOMS Notifications") and subscribe there instead:

1. Create private channel in your Team
2. Add the GitHub app to that channel
3. In the channel, type: `@GitHub subscribe ajrmooreuk/pfi-w4m-eoms-test pulls`
4. Repeat for prod

---

## Commands Reference

### Subscribe to a repo
```
@GitHub subscribe owner/repo
```
Default events: issues, pulls, commits, releases, deployments.

### Subscribe to specific events only
```
@GitHub subscribe owner/repo pulls
@GitHub unsubscribe owner/repo issues commits releases deployments
```

### List current subscriptions
```
@GitHub subscribe list
```

### Unsubscribe from a repo
```
@GitHub unsubscribe owner/repo
```

### Check connection
```
@GitHub signin
```

---

## Target Subscriptions (Once Working)

| Repo | Events | Purpose |
|------|--------|---------|
| `pfi-w4m-eoms-test` | `pulls` | Notify when PRs are merged into test (client review) |
| `pfi-w4m-eoms-prod` | `pulls` | Notify when PRs are merged into prod (go-live changes) |
| `pfi-w4m-eoms-dev` | `pulls` (optional) | Advisory visibility of dev activity |

---

## Alternative Approaches (If GitHub App Doesn't Work)

### Option A: Incoming Webhook (Channel Only)

If the GitHub app continues to have rendering issues, use an Incoming Webhook on a Teams channel with a GitHub Actions workflow that POSTs a message on PR merge.

**Pros:** Full control over message format, no dependency on GitHub Teams app.
**Cons:** Requires a workflow file in each repo + a webhook secret.

### Option B: Power Automate Flow

Create a Power Automate flow triggered by a webhook, sending a Teams chat message.

**Pros:** Works with 1-to-1 chats, flexible routing.
**Cons:** Requires Power Automate licence (usually included in M365 Business).

### Option C: Email Notifications (Fallback)

GitHub can email on PR activity. If Teams integration proves unreliable, configure GitHub notification settings to email the client directly.

**Pros:** Zero setup, always works.
**Cons:** Not real-time in Teams, relies on email being monitored.

---

## Next Steps

1. [ ] Try subscribing via a **private Teams channel** instead of 1-to-1 chat
2. [ ] Check Teams app version and tenant admin settings
3. [ ] If channel approach works, subscribe test + prod to `pulls` events
4. [ ] If GitHub app remains broken, fall back to Option A (Incoming Webhook + workflow)
5. [ ] Document final working setup in this file

---

*Prepared by wings4mind.ai | 22 February 2026*
