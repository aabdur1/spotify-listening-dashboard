# Spotify Listening Habits — Analysis + Tableau Dashboard

Personal-data portfolio project: full pipeline from a raw Spotify extended
streaming history export (JSON) to a published Tableau Public dashboard.

**Status: published.** Live on Tableau Public:
[My Spotify Listening, 2021–2026](https://public.tableau.com/app/profile/amir.abdur.rahim/viz/MySpotifyListening2021-2026/MySpotifyListening20212026)
— 61,230 raw plays (Dec 2021 – Jul 2026) → 57,200 music streams across 7
views: KPI row, monthly hours, genre mix, hour×day heatmap, skip-rate
heatmap (diverging, anchored at my 45.7% average), and genre-colored top
artists with cross-chart hover. A Year Select parameter drives 5 of the 7
views; the KPI row is deliberately all-time.

## Layout

```
data/
  raw/practice/   # practice export (same schema, another user's public data)
  raw/mine/       # my Spotify extended streaming history
  processed/      # tidy CSV extracts for Tableau
notebooks/        # pipeline notebooks, numbered in run order
tableau/          # spotify_dashboard.twb — the published workbook
```

`data/` is gitignored — raw listening history is personal data and is never
committed. The published version of this repo will ship aggregated extracts
only, plus a "request your own data" reproduce path (Spotify account →
Privacy Settings → request extended streaming history).

## Pipeline (all complete)

1. Load + clean (pandas): concat JSON, local timestamps, real-listen threshold
2. Feature engineering: sessions, skip flags, discovery dates
3. Genre enrichment: Last.fm artist lookups, cached locally
4. Aggregate extracts for Tableau (year-aware as of v1.3)
5. Dashboard on Tableau Public

Full README (problem, data, methods, results, limitations) is in progress —
landing alongside the public GitHub release.
