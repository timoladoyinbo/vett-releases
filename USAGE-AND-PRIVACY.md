# Usage counts, licences and privacy

Vett runs on your computer. The sites you test, your specs, findings, reports, screenshots, provider keys and test secrets stay there. This page lists everything Vett sends, and how to turn it off.

## What Vett sends

Once a day, if usage counts are on (the default) and this build has a usage address:

| Field | Example | Why |
| --- | --- | --- |
| Install id | `3b241101-e2bb-…` | A random id made on first launch, to count active installs. Not linked to you or your hardware. Reset it in Settings › Privacy & usage. |
| App version, OS, processor | `0.1.0`, `darwin`, `arm64` | Which builds are in use. |
| Plan, licence id | `pro`, `lic-7f3a9c` | Only if you added a licence key. No name or email. |
| Daily counts | runs by LLM mode, Quick runs, spec runs, tasks, exports by format, specs and profiles created, runs that used the LLM judge | How Vett is used, in numbers only. |

The exact next message is shown in Settings › Privacy & usage › "Show what would be sent next".

## What Vett never sends

Site addresses or hosts, specs, profiles, tasks, variables, findings, checklists, screenshots, reports, provider names, API keys, test secrets, file paths and error messages. The message format allows only numbers, fixed choices and formatted ids, so free text can't be included. The leak tests check this.

## Turning it off

Settings › Privacy & usage › untick "Send anonymous daily usage counts", then Save settings. With counts off:
- no install id or counts are sent;
- if you added a licence key, only a check-in with the licence id is sent, so the licence can be confirmed. Remove the key to stop that too.

Development builds and builds made without a usage address send nothing at all.

## What goes to AI providers

When an LLM is used (Assist or Full agent mode, or "Test connection"), the provider that answers receives page text, element lists and, for visual checks on a vision model, screenshots from the sites you test. Test secrets are never sent: the model only sees placeholders such as `{{secret:shop_pw}}`.

- **On this computer** (Ollama, LM Studio): nothing leaves your computer.
- **Free with a key**: each provider's terms apply. Google's free tier may use prompts to improve its products outside the EEA, Switzerland and the UK; Mistral's free plan requires agreeing to training use; some OpenRouter free models are hosted by providers that log prompts.
- **Community services** (LLM7.io, Pollinations): free and anonymous, with no published data policy. Vett keeps them off until you turn one on and confirm, and never uses one you haven't confirmed. Use them only for public or non-sensitive sites.
- **Paid** (OpenAI, Anthropic): their API terms apply; neither trains on API data by default.

## Licences

Vett's free Community plan includes everything today. A licence key (`VETT1-…`) adds a paid plan when one is offered. Keys are checked on your computer and confirmed online about once a day. Without a connection a key keeps working for 14 days after the last confirmation, then Vett falls back to Community until it can confirm again. A revoked or expired key also falls back to Community; Vett never locks you out.

_Licence terms: to be written._

## What the usage server stores

For the maintainer: one row per install (install id, first and last seen, version, OS, plan, licence id), daily counts, licences issued and revocations. IP addresses are not stored. Daily counts are kept for 13 months; installs not seen for 13 months are deleted.

