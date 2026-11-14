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
| `zsnipe [n]` | last deleted and edited messages in this channel |
| `zsnipeclear` | drop this channel's snipe log |
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
| `zdiag` | what the plugin found at runtime (sender, registrar, token) |
| `zhelp` | list every verb |
| `zstream <title\|off> [gif]` | streaming card |
| `zps <game\|off> [gif]` | PlayStation card |
| `zsp <gif\|off>` | Spotify card |
| `zstack [on\|off\|reset]` | toggle the extra cards |
| `zrpc` | push the presence stack now |
| `zagct` | group-chat trap status |
| `znick <name\|off>` | rename yourself in the guild |
| `zbio <text>` | set about me |
| `zreact [emoji]` | burst reaction on the replied message |
| `znote <user id> <text>` | save a private note |
| `znotes` | list saved notes |

Every verb is also a slash command: `/zsnipe`, `/zmock` (with `user` and
`channel` options), `/zsponge`, and so on. Slash commands take a free-text
`args` option; `/zmock` and `/znote` also take a `user` option, `/zmock` a
`channel` option.

Settings live in **Settings → Plugins → crowsb**: streaming/PS/Spotify cards,
the trap guard, mirror webhooks/bots/pause, and the command bus itself (typed
commands on/off, slash registration on/off, live sender + registrar status).
State is per-plugin storage on the device; the only outbound calls are to
Discord itself.
