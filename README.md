# Kerala Assembly Questions Dataset
## 15th Kerala Legislative Assembly (2021–2026)

First open dataset of questions asked in the Kerala Legislative Assembly (Niyamasabha).

**Total questions: 66,868** | Unstarred: 61,678 | Starred: 5,190 | MLAs: 140 | Match rate: 100%

## Folder Structure
```
data/
  unstarred/         one CSV per session
  starred/           one CSV per session
  mla/
    mla_master.csv   140 MLAs with English and Malayalam details
scrapers/
  questions_scraper.py
```

## Sessions Covered
Sessions 1–14 and 16. Session 15 unavailable on source website.

## Columns
| Column | Description |
|--------|-------------|
| question_id | Unique ID (KLA-Session-Number) |
| kla | Assembly number (15) |
| session | Session number |
| question_number | Official question number |
| question_type | starred or unstarred |
| date | Date question was presented |
| ministry | Ministry the question was directed to |
| title_mal | Question title in Malayalam |
| mla_names | MLA(s) who asked (Malayalam) |
| question_body_mal | Full question text in Malayalam |
| answer_pdf_url | URL to answer PDF |
| source_url | Original source URL |
| mla_name_eng | MLA English name (joined) |
| mla_party_eng | Party name in English (joined) |
| mla_constituency_eng | Constituency in English (joined) |
| mla_party_mal | Party name in Malayalam (joined) |
| mla_constituency_mal | Constituency in Malayalam (joined) |

## Questions per Session
| Session | Unstarred | Starred |
|---------|-----------|---------|
| 1 | 258 | 120 |
| 2 | 5,687 | 510 |
| 3 | 6,692 | 600 |
| 4 | 3,086 | 240 |
| 5 | 5,407 | 450 |
| 6 | 2,299 | 180 |
| 7 | 2,888 | 210 |
| 8 | 6,810 | 570 |
| 9 | 2,902 | 210 |
| 10 | 3,553 | 270 |
| 11 | 6,746 | 570 |
| 12 | 2,562 | 210 |
| 13 | 5,942 | 510 |
| 14 | 3,922 | 300 |
| 16 | 2,924 | 240 |

## MLA Master List
140 MLAs with English and Malayalam names, party, and constituency.
Includes Kanathil Jameela who passed away during the term.

## How to Load
```python
import pandas as pd, glob

# Load all unstarred
dfs = [pd.read_csv(f) for f in glob.glob('data/unstarred/*.csv')]
df = pd.concat(dfs, ignore_index=True)
print(f"Total: {len(df)} questions")

# Load MLA master
df_mla = pd.read_csv('data/mla/mla_master.csv')
```

## Source
[niyamasabha.org](http://niyamasabha.org) — official Kerala Legislature website

## License
CC0 — Public Domain

## Citation
Kerala Assembly Questions Dataset, 15th KLA (2021–2026). Source: niyamasabha.org
