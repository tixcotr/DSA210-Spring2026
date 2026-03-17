# DSA210-Spring2026
## Does Your Body Drive Your Playlist? Exploring the Causal Relationship Between Physical Activity and Music Choice

## Project Overview
This project explores the causal relationship between physical activity and music listening behavior using personal data from Apple Health and Spotify. While it's well known that exercise and music go hand in hand, the question of which one drives the other is rarely examined. By combining daily health metrics (steps, heart rate, sleep, exercise minutes) with daily music features (tempo, energy, danceability), this project applies Granger causality analysis and machine learning to determine whether an active body shapes your playlist — or whether your playlist shapes your activity. The goal is to go beyond surface-level correlations and test a directional hypothesis with rigorous statistical methods.

## Motivation
Most studies on music and health focus on simple correlations — people who exercise more tend to listen to upbeat music. But correlation doesn't tell us which comes first. This project investigates the direction of causality: does an active day make you crave energetic music afterward, or does pumping up your playlist actually get you moving? By applying Granger causality analysis and predictive modeling, this project aims to untangle which direction the influence flows.

## Objectives
- **Collect the Data:** Export personal data from Apple Health and Spotify, enrich with audio features via the Spotify Web API.
- **Analyze the Gathered Data:** Aggregate daily health and music metrics, explore trends and patterns over 6 months.
- **Test Causality:** Apply Granger causality analysis to determine the direction of influence between activity and music choice.
- **Develop a Model:** Build predictive models to forecast music feature shifts based on prior physical activity levels.

## Research Questions
- **Does physical activity Granger-cause a shift toward higher-energy music on subsequent days?**
- **Does high-energy music listening Granger-cause increased physical activity the following day?**
- **Which health metrics (steps, heart rate, exercise minutes) are the strongest predictors of music choice?**
- **Are there weekly or seasonal patterns in the activity–music relationship?**

## Dataset

### Apple Health Data (Exported from personal iPhone):
- **Daily step count** and walking/running distance
- **Active energy burned** (kcal)
- **Exercise minutes**
- **Resting heart rate** and heart rate variability
- **Sleep duration** and bedtime/wake time
- Collection: Apple Health app → Export All Health Data (XML → CSV)

### Spotify Data (Personal account + API enrichment):
- **Listening history** requested via Spotify privacy settings
- **Audio features** enriched via Spotify Web API:
  - Average tempo (BPM)
  - Average energy (0.0–1.0)
  - Average danceability (0.0–1.0)
  - Average valence (0.0–1.0, musical positivity)
  - Listening time-of-day distribution
- Collection: spotify.com → Privacy Settings → Download Your Data + Spotify Web API

## Hypothesis

**Directional Hypothesis:** Physical activity drives music choice, not the other way around. Specifically, high-activity days Granger-cause a shift toward higher-energy music on subsequent days, but high-energy music listening does not Granger-cause increased physical activity.

**Null Hypothesis (H₀):** Physical activity levels do not Granger-cause changes in music listening features (energy, tempo, danceability). There is no statistically significant directional relationship from activity to music choice.

**Alternative Hypothesis (H₁):** Physical activity levels do Granger-cause shifts in music listening features on subsequent days, while music features do not Granger-cause changes in physical activity — indicating a one-directional influence from body to playlist.

## Tools & Technologies
- Python (pandas, numpy, scipy, scikit-learn, statsmodels, matplotlib, seaborn)
- Apple Health export (XML → CSV)
- Spotify Web API for audio feature extraction
- Jupyter Notebooks for analysis and visualization


