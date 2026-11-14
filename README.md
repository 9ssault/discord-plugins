# discord plugins

Bunny / Kettu plugin repository. Two install flows, pick whichever field your client shows.

## Install — repository field

Bunny: Settings → Plugins → **Add repository**, paste:

```
https://raw.githubusercontent.com/9ssault/discord-plugins/main/repo.json
```

## Install — paste-a-URL field

Kettu/Vendetta-style field that asks for a **plugin URL** (the one that says
"Failed to fetch manifest for ..."), paste the repo root, trailing slash included:

```
https://raw.githubusercontent.com/9ssault/discord-plugins/main/
```

The loader fetches `<url>manifest.json`, then `<url>index.js` and evals it.

## Files

```
repo.json                         repository index (repo-field install)
builds/crowsb.kettu/manifest.json spec 3 manifest (repo-field install)
builds/crowsb.kettu/index.js      bundle, statement iife
manifest.json                     polymanifest (paste-a-URL install)
index.js                          bundle, single expression
```

## crowsb.kettu

Presence stack (streaming, PlayStation, Spotify), group-chat trap guard, mock
mirror, snipe log, text toolkit and reaction burst.

Commands, any channel, prefix `z`:

| verb | what |
|---|---|
| `zsnipe` | last deleted message in this channel |
| `zeditsnipe` | last edited message, before + after |
| `zmock <@user>` | repost that member's messages here, verbatim |
| `zmock #channel <@user>` | same, in one channel |
| `zmock webhook on\|off` | post the copies as them through a webhook |
| `zmock bots on\|off` | include bot accounts |
| `zmock status` | show what is being mirrored |
| `zmock off` | stop everywhere |
| `zsmock` | pause / resume mirroring |
| `zsponge <text>` | alternating case |
| `zsmall <text>` | small caps |
| `zflip <text>` | upside down |
| `zzalgo <text>` | glitch text |
| `zclap <text>` | 👏 between words |
| `zemojify <text>` | letter emojis |
| `zreverse <text>` | reversed |
| `zrpc` | push the presence stack now |
| `zrpc status` | show what is staged |

Settings live in **Settings → Plugins → crowsb**. State is per-plugin storage on
the device; the only outbound calls are to Discord itself.
