# indigo-airline-sentiment-analysis
Sentiment analysis of airline customer reviews using R
# ✈️ IndiGo Airlines Customer Review Sentiment Analysis

A personal data project where I dug into what passengers are actually saying about IndiGo - India's largest airline by market share. Scraped and curated 72 reviews from Skytrax, Trustpilot, TripAdvisor, and MouthShut spanning 2023–2025, then ran a full sentiment pipeline in R.

---

## Why I built this

I have intrest in aviation and in India IndiGo is basically unavoidable I kept noticing a pattern — my own experiences were fine, but people online seemed *furious* about the airline. I wanted to actually quantify that gap rather than just go off vibes.

Turns out the data is pretty interesting.

---

## What I found

The short version: **nearly half the reviews are negative**, with Customer Service and Baggage handling being the two biggest pain points. Punctuality is genuinely IndiGo's strongest suit — which matches my personal experience.

A few things that surprised me:

- Ratings are weirdly polarised. Lots of 1★ and 5★, not much in between. People either love or hate this airline.
- Sentiment has gotten *worse* year-over-year (2023 → 2025). Not a huge shift, but a consistent one.
- The word "cancelled" shows up in negative reviews at a very high frequency — more than "delayed", which I wasn't expecting.
- When people are happy, they specifically mention staff by name. When they're unhappy, it's always about systems.

---

## Charts

### Sentiment Distribution
![Sentiment Distribution](charts/1_sentiment_distribution.png)

### Star Rating Breakdown
![Rating Distribution](charts/2_rating_distribution.png)

### Sentiment Over Time (Quarterly)
![Sentiment Trend](charts/3_sentiment_trend.png)

### How Each Aspect Scored (Heatmap)
![Aspect Heatmap](charts/4_aspect_heatmap.png)

### Aspect-wise Breakdown (Grouped Bar)
![Aspect Grouped Bar](charts/5_aspect_grouped_bar.png)

### Keywords People Use (Positive vs Negative)
![Keyword Frequency](charts/6_keyword_frequency.png)

### Average Rating per Aspect
![Avg Rating by Aspect](charts/7_avg_rating_by_aspect.png)

### How Sentiment Shifted Year by Year
![Yearly Shift](charts/8_yearly_sentiment_shift.png)

---

## Tech stack

- **R** — main analysis language
- `ggplot2` — all charts
- `tidytext` — tokenisation and lexicon-based sentiment scoring
- `tidyverse` — data wrangling
- `wordcloud2` — keyword visualisation
- `RColorBrewer` + `scales` — colour palettes and axis formatting
- `ggrepel` — label placement on the trend chart

---

## How to run it yourself
```r
# clone the repo first, then:
source("indigo_sentiment_analysis.R")
```

You'll need R 4.x. The script auto-installs missing packages on first run so you shouldn't need to do anything extra. Charts save as PNGs in your working directory.

---

## Dataset notes

Reviews were manually curated from:
- **Skytrax** (aviation-specific, skews toward frequent flyers)
- **Trustpilot** (broader consumer base)
- **TripAdvisor**
- **MouthShut** (India-specific, good for domestic traveller perspective)

I kept only reviews that were clearly about IndiGo's domestic or international scheduled flights — filtered out reviews about cargo-only queries or misrouted complaints. Ratings were kept as-is from the source platform (all on a 1–5 scale).

This is not a statistically representative sample. It's exploratory.

---

## Limitations / what I'd do differently

- 72 reviews is a small sample. A proper study would need 500+, ideally scraped systematically.
- MouthShut in particular has a known negativity bias (people go there to complain).
- The NRC emotion lexicon was built on English text and some of the phrasing in India-specific English doesn't map cleanly.
- I'd love to add a time-of-day or route-level breakdown if I had the data.

---

## Folder structure
```
indigo-sentiment-analysis/
│
├── README.md
├── indigo_sentiment_analysis.R
└── charts/
    ├── 1_sentiment_distribution.png
    ├── 2_rating_distribution.png
    ├── 3_sentiment_trend.png
    ├── 4_aspect_heatmap.png
    ├── 5_aspect_grouped_bar.png
    ├── 6_keyword_frequency.png
    ├── 7_avg_rating_by_aspect.png
    └── 8_yearly_sentiment_shift.png
```

---

## Contact

If you have feedback on the methodology or want to talk data, feel free to open an issue or reach out on LinkedIn.

---

*Built as a personal learning project. Not affiliated with IndiGo Airlines.
