# discord plugins

Bunny / Kettu plugin repository.

Paste this into the client's **plugin repository** field:

```
https://raw.githubusercontent.com/9ssault/discord-plugins/main/repo.json
```

## crowsb.kettu

Presence stack (streaming, PlayStation, Spotify), group-chat trap guard, snipe
log, text toolkit and reaction burst.

Commands, in any channel, prefix `z`:

| verb | what |
|---|---|
| `zsnipe` | last deleted message in this channel |
| `zeditsnipe` | last edited message, before + after |
| `zmock <text>` | alternating case |
| `zsmall <text>` | small caps |
| `zflip <text>` | upside down |
| `zzalgo <text>` | glitch text |
| `zclap <text>` | 👏 between words |
| `zemojify <text>` | letter emojis |
| `zreverse <text>` | reversed |
| `zrpc` | push the presence stack now |
| `zrpc status` | show what is staged |

Settings live in **Settings → Plugins → crowsb**. State is per-plugin storage on
the device; nothing leaves it except the presence call to Discord.

