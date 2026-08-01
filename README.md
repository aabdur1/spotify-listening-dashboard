# Spotify Listening Habits — Analysis + Tableau Dashboard

Personal-data portfolio project: full pipeline from a raw Spotify extended
streaming history export (JSON) to a published Tableau Public dashboard.

**Status: pre-data.** My own export is requested and in transit (up to 30
days). The pipeline is being built against a practice dataset in the same
schema so my data drops in on arrival.

## Layout

```
data/
  raw/practice/   # practice export (same schema, another user's public data)
  raw/mine/       # my Spotify extended streaming history (when it arrives)
  processed/      # tidy CSV extracts for Tableau
notebooks/        # pipeline notebooks, numbered in run order
```

`data/` is gitignored — raw listening history is personal data and is never
committed. The published version of this repo will ship aggregated extracts
only, plus a "request your own data" reproduce path (Spotify account →
Privacy Settings → request extended streaming history).

## Roadmap

1. Load + clean (pandas): concat JSON, local timestamps, real-listen threshold
2. Feature engineering: sessions, skip flags, discovery dates
3. Genre enrichment: Spotify Web API artist lookups, cached locally
4. Aggregate extracts for Tableau
5. Dashboard on Tableau Public

Full README (problem, data, methods, results, limitations) lands once results
exist.
