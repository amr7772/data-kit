# Data Kit

A skill for Claude Code and Codex that helps journalists get numbers from free institutional data sources and check them before publishing.

You ask a question in plain language, in Arabic or English. The skill picks the source, builds the request, fetches the data and then runs the checks a data editor would run: what the indicator actually measures, which year a number really belongs to, breaks in the series, revisions, units. Every answer comes with an attribution line you can paste into a story and the exact request, so you can rerun it later.

The instructions in `SKILL.md` are written in Arabic.

## Sources (28)

**Economy and development:** World Bank, World Bank PIP (poverty), IMF DataMapper, WHO GHO, UNHCR, UN SDG, ILOSTAT, HDX, Our World in Data, UN Comtrade, KAPSARC, Qatar and Bahrain open data portals, NASA POWER, USGS earthquakes, CAPMAS (Egypt), ESCWA Arab Development Portal.

**Satellite and Earth observation:** Microsoft Planetary Computer, Earth Search (AWS), Copernicus Data Space, NASA Black Marble night lights, NASA GIBS, NASA FIRMS fires, FAO WaPOR, GHSL and WorldPop, JRC Global Surface Water, Copernicus EMS and UNOSAT damage maps, Open-Meteo (ERA5).

Most requests were tested on 11 October 2026. The file marks the ones that need a free key or could not be tested.

## A few traps it catches

- The IMF reports Egypt by fiscal year (July to June) and the World Bank by calendar year. Egypt's 2023 inflation is 24.4% in one and 33.9% in the other.
- Our World in Data shows a 2025 poverty figure for Egypt that comes from a 2021 survey. The `original_year` column gives it away.
- ILOSTAT flags a series break (`obs_status = B`) in Egypt's 2024 youth unemployment figure.
- The cloud cover on a Sentinel-2 scene is for the whole 110 km tile, not for your area.

## Install

Claude Code:

```
.claude/skills/data-kit/SKILL.md
```

Codex:

```
.agents/skills/data-kit/SKILL.md
```

Then ask your question, for example: "How has inflation in Egypt, Jordan and Morocco changed since 2022?"

`index.html` is the project page. It reads `SKILL.md` from the same folder, so it also works on GitHub Pages.

## Credits

By Amr Eleraqi, InfoTimes. A companion to his data journalism book. The idea comes from the Global Data Kit project (MIT). The content, sources and tests here were written from scratch.

MIT License.
