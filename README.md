A Python command-line assistant that asks anglers for the month of their trip to Rügen and recommends the right target fish, the best hotspots and the right bait, based on ten years of local fishing experience.

Instead of searching through generic websites and YouTube videos or asking locals on site, anglers get concrete, season-specific insider tips for the Bodden and the Baltic Sea on the drive to the island.

**Status:** Working prototype. The rule-based advisor covers March to November; an LLM-based chat mode and winter recommendations are planned.

## Features

- **Seasonal Recommendations:** Suggests the best target fish for each month from March to November, from spawning herring in spring to autumn pike and flatfish.
- **Target Fish Selection:** Lets anglers choose between several species in months with more than one option (autumn pike or flatfish, summer pike or perch and zander).
- **Local Hotspots:** Names concrete spots such as the Strelasund, the Greifswalder Bodden, the Rügendamm and the piers of Sellin, Göhren and Binz.
- **Bait and Rig Advice:** Recommends lures and rigs for each species, for example a Sbirulino rig for garfish or a sand eel spoon for sea trout.
- **Forgiving Input:** Accepts months as names or numbers and recognizes answers regardless of capitalization (`oktober`, `10`, `Maerz`, `JA`, `nee`).
- **No Dependencies:** Runs with the Python standard library only, with no API key and no internet connection.

## Why This Project

Rügen is one of the best places in Europe for trophy-sized predatory fish. Zander, pike and perch grow exceptionally large because they feed on the herring shoals in the Bodden, where brackish water and the Baltic Sea meet. Yet the information available online is very general. After ten years of fishing in Rügen's waters, I built this agent to share my insider knowledge with every angler who visits the island.

## How It Works

1. **Month** – The agent asks for the month of the trip.
2. **Target Fish** – It recommends the seasonal species and, where there are several, asks which one you want to catch.
3. **Hotspots** – On request, it names the most promising spots for that species.
4. **Bait** – On request, it recommends the right lures and rigs.
5. **Repeat** – You can ask about another month or exit with `ende`.

All advice is stored in two data tables (`FISCHE` and `SAISONS`) in `rfa.py`, so a new species or month only takes a few lines.

## Getting Started

### Prerequisites

- Python 3.8+

### Installation

```bash
git clone https://github.com/DanBellut/R-gen-Fishing-Agent.git
cd R-gen-Fishing-Agent
```

## Usage

```bash
python3 Python/Code/rfa.py
```

Example session (the agent speaks German):

```
Willkommen zum Rügen Fishing Agent!
Nenne einen Monat, in dem du auf Rügen angeln magst. … Oktober
Herbsthecht und Plattfische von der Seebrücke (Flunder, Kliesche und Scholle).
Möchtest du Herbsthecht oder Plattfisch angeln? Hecht
Das ist eine aufregende Wahl. Die Hechte sind im Oktober extrem aggressiv …
Willst du wissen, wo die Hotspots für Hechte in Rügener Gewässern sind? ja
Hotspots sind Schilfkanten und Fahrrinnen im Strelasund, im Greifswalder Bodden, …
```

## Tech Stack

- **Language:** Python 3.8+
- **Interface:** Command line (`input` / `print`)
- **Data:** Python dictionaries (no external files or database)
