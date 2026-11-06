<div align="center">

# ⚔️ PartySystem

**Gratis party- og kitsystem til Paper med forudlavede kits, matches, ranked ELO og toplister.**

![Version](https://img.shields.io/badge/version-1.5.0-blue)
![Paper](https://img.shields.io/badge/Paper-1.21%2B-success)
![Java](https://img.shields.io/badge/Java-21-orange)
![PlaceholderAPI](https://img.shields.io/badge/PlaceholderAPI-valgfri-lightgrey)

[📥 **Download PartySystem.jar**](https://github.com/BlockCraft-HQ/PartySystem/raw/main/PartySystem.jar)

</div>

---

## ✨ Hvad kan pluginet?

| | |
|---|---|
| 🎒 **Kits** | Vælg et af 17 forudlavede kits, eller byg dit eget med `/party edit` |
| 🔁 **Restock** | Få dit kit igen og igen med `/party restock` (med cooldown) |
| 👥 **Partyer** | Opret et party, inviter venner og spil sammen |
| 🏟️ **Matches** | Sidste spiller i live vinder, med valgfrit antal runder |
| 🏆 **Ranked** | Matchmaking-kø til 1v1 med ELO, win streak og K/D |
| 📊 **Toplister** | Hologrammer med top ELO, sejre, win streak og kills |
| 🧩 **PlaceholderAPI** | Placeholders til scoreboard, TAB og andre plugins |
| 💬 **Egne beskeder** | Alle tekster kan ændres i `messages.yml` (MiniMessage) |

---

## 📋 Krav

- **Paper 1.21 eller nyere** (Spigot og Bukkit er ikke understøttet)
- **Java 21**
- *(Valgfrit)* [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) hvis du vil bruge placeholders

---

## 🚀 Installation

1. Download [`PartySystem.jar`](https://github.com/BlockCraft-HQ/PartySystem/raw/main/PartySystem.jar).
2. Læg filen i serverens `plugins/`-mappe.
3. Genstart serveren.
4. Pluginet opretter nu `plugins/PartySystem/` med `config.yml`, `messages.yml` og en `Kits/`-mappe med alle standard-kits.
5. Følg opsætningen herunder, så er du klar.

> 💡 Brug `/party reload`, når du har rettet i config, beskeder eller kits. Du behøver ikke genstarte.

---

## 🛠️ Opsætning (for admins)

Før nogen kan spille et match, skal der være mindst én **arena**.

1. Stå der, hvor spillerne skal spawne, og skriv:
   ```
   /party setspawn arena1
   ```
   Et nyt navn opretter en ny arena.
2. Sæt arenaens område ved at stå i to hjørner:
   ```
   /party setpos1 arena1
   /party setpos2 arena1
   ```
3. *(Valgfrit)* Begræns arenaen til bestemte kits:
   ```
   /party arenakit arena1 add sword
   ```
4. Se alle arenaer med `/party arenas`.

Du kan lave så mange arenaer, du vil. Matches bruger en ledig arena, så flere kampe kan køre samtidig.

Brug `/party open` og `/party close` til at åbne eller lukke party for almindelige spillere. Admins kan altid komme ind.

---

## 🎮 Sådan bruger du det (for spillere)

### Vælg et kit
```
/party kit            Se alle kits
/party kit <navn>     Vælg et kit, f.eks. /party kit sword
```
I et party giver lederen kittet til hele partyet.

### Byg dit eget kit
```
/party edit           Byg eller rediger dit eget kit
/party save           Gem dit kit
```
Når du gemmer, bliver kittet tjekket mod serverens regler. Forbudte items fjernes, og der er grænser for f.eks. TNT og guldæbler.

### Få dit kit igen
```
/party restock        Få dit kit igen (har cooldown)
/party status         Se din status og restock-cooldown
/party leave          Forlad arenaen eller dit party
```

### Spil sammen i et party
```
/party create             Opret dit eget party
/party invite <spiller>   Inviter en spiller
/party accept | deny      Svar på en invitation
/party list               Se medlemmer
/party remove <spiller>   Fjern en spiller (kun lederen)
/party disband            Opløs partyet (kun lederen)
```
Lederen kan ikke bruge `/party leave`, men skal bruge `/party disband`.

### Start et match
```
/party menu               Åbn match-menuen
/party start [kit]        Start et match med menuens indstillinger
```
Alle spiller med samme kit. Der er en nedtælling, før kampen går i gang, og **den sidste i live vinder**. Du kan vælge antal runder i menuen.

### Ranked 1v1
```
/party queue <kit>        Stil dig i kø til et ranked 1v1-match
/party queue leave        Forlad køen
/party stats [spiller]    Se ranked stats
/party top [elo|wins|streak|kills]
```
Du matches mod en spiller med nogenlunde samme ELO. Søgeområdet bliver større, jo længere du venter. Du skal forlade dit party, før du kan stille dig i kø.

---

## 📖 Alle kommandoer

Hovedkommandoen er `/party`, og aliaset er `/pt`.

### 👤 Spillere (`partysystem.use`)

| Kommando | Beskrivelse |
|---|---|
| `/party help` | Vis hjælp |
| `/party kit [navn]` | Se kits eller vælg et |
| `/party menu` | Åbn match-menuen |
| `/party start [kit]` | Start et match |
| `/party edit` / `save` | Byg og gem dit eget kit |
| `/party restock` | Få dit kit igen |
| `/party status` | Se din status |
| `/party leave` | Forlad arena eller party |
| `/party create` / `disband` | Opret eller opløs party |
| `/party invite` / `accept` / `deny` | Invitationer |
| `/party list` / `remove` | Medlemmer |
| `/party queue <kit>` / `queue leave` | Ranked kø |
| `/party stats [spiller]` | Ranked stats |
| `/party top [type]` | Toplister i chatten |

### 🔧 Admins (`partysystem.admin`)

| Kommando | Beskrivelse |
|---|---|
| `/party setspawn [arena]` | Sæt spawn (nyt navn = ny arena) |
| `/party setpos1` / `setpos2 [arena]` | Sæt arenaens område |
| `/party delspawn <arena>` | Slet en arena |
| `/party arenas` | Vis alle arenaer |
| `/party arenakit <arena> <add\|remove\|clear> [kit]` | Begræns en arena til bestemte kits |
| `/party open` / `close` | Åbn eller luk party |
| `/party reload` | Genindlæs config, beskeder og kits |
| `/party editkit <kit>` | Rediger et kit (nyt navn = nyt kit) |
| `/party savekit` / `cancelkit` | Gem eller afbryd redigering |
| `/party resetkit <spiller>` | Nulstil en spillers kit |
| `/party resetcooldown <spiller>` | Nulstil restock-cooldown |
| `/party kick <spiller>` | Fjern en spiller fra party |
| `/party info <spiller>` | Vis spillerdata |
| `/party setelo <spiller> <elo>` | Sæt en spillers ELO |
| `/party resetstats <spiller>` | Nulstil ranked stats |
| `/party hologram create <elo\|wins\|streak\|kills>` | Opret en toplist hvor du står |
| `/party hologram remove\|move <id>` | Fjern eller flyt et hologram |
| `/party hologram list\|refresh` | Vis hologrammer / opdater nu |

---

## 🔐 Permissions

| Permission | Standard | Beskrivelse |
|---|---|---|
| `partysystem.use` | Alle | Spiller-kommandoer |
| `partysystem.admin` | OP | Admin-kommandoer |
| `partysystem.restock.nocooldown` | OP | Ingen cooldown på restock |
| `partysystem.command.bypass` | OP | Må bruge alle kommandoer i party |

---

## 🎒 Medfølgende kits

Der følger 17 kits med, som oprettes første gang pluginet starter:

`axe` · `bow` · `creeper` · `crystal` · `diamond-crystal` · `diamond-smp` · `lt-cart` · `mace` · `netherite-pot` · `pot` · `shieldless-uhc` · `smp` · `spear-elytra` · `spear-mace` · `sword` · `trident` · `uhc`

### Lav dit eget kit

Hvert kit er en fil i `plugins/PartySystem/Kits/`. Filnavnet uden `.yml` er kittets navn i kommandoen. Opret en ny fil, f.eks. `Kits/mit-kit.yml`, og skriv `/party reload`.

```yaml
display-name: <aqua>Mit Kit
items:
- slot: 0
  material: DIAMOND_SWORD
  enchantments:
    sharpness: 5
    unbreaking: 3
- slot: helmet
  material: DIAMOND_HELMET
  enchantments:
    protection: 4
```

| Felt | Forklaring |
|---|---|
| `slot` | `0-8` hotbar, `9-35` inventory, eller `helmet` / `chestplate` / `leggings` / `boots` / `offhand` |
| `material` | Minecraft-material |
| `fallback` | Bruges, hvis materialet ikke findes på serveren *(valgfri)* |
| `amount`, `name`, `lore` | Antal, navn og beskrivelse (MiniMessage) |
| `enchantments` | `navn: niveau` |
| `potion` | F.eks. `strong_healing` |
| `unbreakable` | `true` eller `false` |

Du kan også redigere kits direkte i spillet med `/party editkit <kit>` og gemme med `/party savekit`.

---

## ⚙️ Konfiguration

Alt kan ændres i `plugins/PartySystem/config.yml`. De vigtigste indstillinger:

| Indstilling | Standard | Beskrivelse |
|---|---|---|
| `restock.cooldown-seconds` | `60` | Cooldown på `/party restock` (0 = ingen) |
| `restock.mode` | `REPLACE` | `REPLACE` erstatter inventory, `FILL` fylder kun op |
| `group.max-size` | `8` | Maks. spillere i et party |
| `group.invite-expire-seconds` | `60` | Hvor længe en invitation er gyldig |
| `group.scoreboard.enabled` | `true` | Sæt til `false`, hvis TAB styrer dit scoreboard |
| `match.countdown-seconds` | `5` | Nedtælling før kampen starter |
| `match.max-rounds` | `20` | Maks. runder i menuen |
| `kit.reject-empty` | `true` | Afvis tomme kits ved save |
| `kit.limits.per-material` | se config | Grænser, f.eks. `TNT: 16` |
| `time-limit.enabled` | `false` | Tidsgrænse til at bygge kit |
| `ranked.start-elo` | `1000` | Start-ELO |
| `ranked.k-factor` | `32` | Hvor meget ELO en kamp flytter |
| `ranked.rounds` | `3` | Runder i en ranked kamp |
| `queue.elo-range.initial` | `100` | Start-søgeområde i køen |

Config-filen har kommentarer ved hver indstilling, så den er nem at gå til.

> Alle tekster ligger i `messages.yml` og bruger [MiniMessage](https://docs.advntr.dev/minimessage/format.html), så du kan ændre både tekst og farver.

---

## 🏆 Toplister (hologrammer)

1. Stå, hvor hologrammet skal sidde.
2. Skriv `/party hologram create elo` (eller `wins`, `streak`, `kills`).
3. Ret udseendet i `config.yml` under `leaderboard`, og skriv `/party reload`.

Hologrammerne opdateres automatisk. Du kan flytte dem med `/party hologram move <id>`.

---

## 🧩 PlaceholderAPI

Kræver [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/). Identifier: `party`.

| Placeholder | Beskrivelse |
|---|---|
| `%party_count%` | Spillere i party lige nu |
| `%party_in_party%` | Er spilleren i et party/match? |
| `%party_has_kit%` | Har spilleren et kit? |
| `%party_in_builder%` | Er spilleren i kit-builderen? |
| `%party_restock_cooldown%` | Sekunder til næste restock |
| `%party_restock_ready%` | Kan spilleren restocke nu? |
| `%party_restocks%` / `%party_joins%` | Antal restocks / joins |
| `%party_last_save%` | Seneste save |
| `%party_in_group%` | Er spilleren i et spiller-party? |
| `%party_group_size%` / `%party_group_max%` | Partyets størrelse / maks. |
| `%party_group_leader%` | Lederens navn |
| `%party_group_members%` | Medlemmernes navne |
| `%party_in_queue%` / `%party_queue_size%` | I kø? / antal i køen |
| `%party_elo%` / `%party_peak_elo%` | ELO / højeste ELO |
| `%party_wins%` / `%party_losses%` / `%party_draws%` | Sejre / nederlag / uafgjort |
| `%party_matches%` / `%party_winrate%` | Kampe / win rate |
| `%party_streak%` / `%party_best_streak%` | Win streak / bedste |
| `%party_kills%` / `%party_deaths%` / `%party_kdr%` | Kills / deaths / K/D |
| `%party_top_<type>_<plads>_name%` | Navn på en plads i toplisten |
| `%party_top_<type>_<plads>_value%` | Værdi på en plads i toplisten |

`<type>` er `elo`, `wins`, `streak` eller `kills`. Eksempel: `%party_top_elo_1_name%` giver navnet på spilleren med højest ELO.

---

## 💾 Data

Spillerdata og ranked stats gemmes i en SQLite-database, `plugins/PartySystem/data.db`. Der skal ikke opsættes noget, og du kan tage backup ved at kopiere filen.

---

## ❓ Ofte stillede spørgsmål

**Jeg kan ikke starte et match.**
Tjek, at der er mindst én arena (`/party arenas`), og at party er åbent (`/party open`).

**Spillerne kan ikke slå hinanden.**
Hvis en anden plugin, f.eks. WorldGuard, blokerer PvP, så tjek `kit-mode.override-protection` og `match.force-world-pvp` i `config.yml`.

**Mit scoreboard bliver overskrevet.**
Sæt `group.scoreboard.enabled: false`, og brug placeholders i dit eget scoreboard-plugin.

**En spiller kan ikke gemme sit kit.**
Kittet er enten tomt, eller det indeholder forbudte items eller for mange af et item. Reglerne står under `kit` i `config.yml`.

**Hvordan nulstiller jeg en spillers cooldown eller kit?**
Brug `/party resetcooldown <spiller>` eller `/party resetkit <spiller>`.

---

<div align="center">

Lavet af **BlockCraft** 💙

</div>
