# DSA210-Spring2026

## What Makes a Movie Oscar-Worthy? Predicting Oscar Nominations Using Movie Metadata and Historical Award Data

## Project Overview
This project investigates what measurable characteristics predict whether a movie receives an Oscar nomination. While critical acclaim and artistic merit are often cited as the defining factors behind Oscar recognition, the question of which concrete, quantifiable features — budget, runtime, release timing, audience ratings, revenue — actually distinguish Oscar-nominated films from the rest is rarely examined with data. By combining a large movie metadata dataset with historical Oscar nomination records, this project applies statistical testing and machine learning to identify the strongest predictors of nomination and test specific hypotheses about what the Academy truly values when it comes to numbers.

## Motivation
Every year, thousands of movies are released, but only a handful receive Oscar nominations. Industry discussions around "Oscar bait" suggest that certain patterns exist — dramas released in the fall, with longer runtimes and moderate budgets, tend to get nominated more often. But is this actually supported by data? Are big-budget blockbusters more or less likely to be recognized? Does releasing a film in October genuinely improve its chances compared to a summer release? This project moves beyond speculation by quantifying these patterns. By merging movie-level features with nomination outcomes, the goal is to determine which factors genuinely matter and whether a model can predict nomination likelihood from a movie's measurable attributes alone.

## Objectives
- **Collect and Merge the Data:** Combine the TMDB movie metadata dataset with the historical Oscar Award dataset, matching on movie title and release year to create a single enriched dataset with a binary nomination label.
- **Analyze the Data:** Explore distributions and trends across nominated vs. non-nominated films, identifying visual and statistical differences in budget, runtime, ratings, revenue, genre, and release month.
- **Test Hypotheses:** Apply statistical tests (t-tests, chi-square) to determine whether observed differences between nominated and non-nominated films are statistically significant — not just apparent in plots.
- **Build a Predictive Model:** Train a classification model to predict whether a movie gets nominated based on its features, and analyze feature importance to answer which factors carry the most weight.

## Research Questions
- **Do Oscar-nominated films have significantly higher budgets than non-nominated films?**
- **Is there a "sweet spot" for runtime that increases nomination likelihood?**
- **Does release month matter — are fall releases (September–December) more likely to be nominated?**
- **Are audience ratings (vote average) a strong predictor, or does popularity matter more?**
- **Which single feature is the strongest predictor of Oscar nomination: budget, ratings, revenue, or runtime?**
- **Can a machine learning model reliably distinguish nominated films from non-nominated ones using only numerical features?**

## Dataset

### TMDB Movie Metadata (Kaggle):
- ~5,000 movies with features including:
  - **Budget** (USD)
  - **Revenue** (USD)
  - **Runtime** (minutes)
  - **Vote average** (0–10 scale) and **vote count**
  - **Popularity** score
  - **Release date** (used to extract release month and year)
  - **Genres** (JSON-encoded, parsed into individual genre labels)
  - **Original language** and **production companies**
- Source: [kaggle.com/datasets/tmdb/tmdb-movie-metadata](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

### The Oscar Award, 1927–2025 (Kaggle):
- Complete historical record of all Oscar nominations and winners, including:
  - **Year of ceremony**
  - **Category** (Best Picture, Best Director, Best Actor, etc.)
  - **Film name**
  - **Winner status** (True/False)
- Source: [kaggle.com/datasets/unanimad/the-oscar-award](https://www.kaggle.com/datasets/unanimad/the-oscar-award)

### Enrichment
The TMDB dataset serves as the base. The Oscar dataset is merged in to add:
- A binary label: `nominated` (1 if the film received at least one Oscar nomination, 0 otherwise)
- `nomination_count`: total number of nominations the film received across all categories
- `winner`: whether the film won at least one Oscar

This enrichment transforms a general movie metadata dataset into one that can answer award-specific questions with statistical rigor.

## Hypothesis

**Directional Hypothesis:** Oscar-nominated films are systematically different from non-nominated films in measurable ways — specifically, they tend to have higher budgets, longer runtimes, higher audience ratings, and are more likely to be released in the final quarter of the year (October–December).

**Null Hypothesis (H₀):** There is no statistically significant difference in budget, runtime, vote average, or release month distribution between Oscar-nominated and non-nominated films. Any observed differences are due to random variation.

**Alternative Hypothesis (H₁):** Oscar-nominated films have significantly higher budgets, longer runtimes, and higher audience ratings than non-nominated films, and are disproportionately released in Q4 (October–December) compared to the rest of the year.

## Plan
| Phase | Description | Deadline |
|-------|-------------|----------|
| Data Collection | Download, clean, and merge both datasets | April 14 |
| EDA & Hypothesis Testing | Visualize distributions, run statistical tests | April 14 |
| Machine Learning | Train classification models, analyze feature importance | May 5 |
| Final Report | Write up findings, limitations, and conclusions | May 18 |

## Tools & Technologies
- Python (pandas, numpy, scipy, scikit-learn, matplotlib, seaborn)
- Jupyter Notebook for analysis and visualization
- GitHub for version control and submission

