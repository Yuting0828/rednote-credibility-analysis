# Content Credibility Signals on Xiaohongshu (RedNote): An Exploratory Study

**Author:** Yuting Wang

**Context:** Individual course project, Foundations of Data Science (FIT5145), Monash University, 2025

**Status:** Exploratory rule-based prototype in R. It is part of a broader course proposal on credibility assessment of AI-generated multimodal content; the components that would identify AI-generated content are **not** implemented.

## Research question

Which observable cues can flag potentially low-credibility posts on social platforms?

## Files

| File | Description |
|---|---|
| `rednote_credibility_analysis.Rmd` | R Markdown code for the analysis |
| `README.md` | This file |

## What the code does

1. **Data quality report:** missing values, image coverage, tag validity and numeric summaries.
2. **Engagement anomalies:** posts with zero likes but 100 or more collects, and posts with zero comments but 100 or more likes.
3. **Tag analysis:** the 20 most frequent tags (translated to English for display) and a word cloud. The most frequent tags concern weight loss, outfits, skincare, aesthetic medicine and product recommendations.
4. **Credibility heuristics (rule-based):**
   - *Text-image mismatch indicators:* long text (over 300 characters) with no image; short text (under 50 characters) with more than three images; food or outfit titles with no image.
   - *Heuristic credibility score:* promotional wording ("free", "claim", "benefits") scores 0.3; absolute claims ("most", "absolute", "100%") score 0.5; very little text per image scores 0.4; everything else scores 0.8.
   - *Suspicious features:* six-digit numbers or "verification code", more than three exclamation marks, and very long text with no image.

## Data and ethics

- Input file: `xiaohongshu_data.csv` (**not included**). It holds 1,163 public posts collected via platform search, used for coursework only.
- Fields used: title, content, tags, image URLs and interaction counts. Author names and identifiers were not used in the analysis.
- The sample comes from search results, so it is not a random sample of the platform.

## How to run

Install R with the packages `readxl`, `tidyverse`, `wordcloud2`, `ggplot2`, `htmlwidgets` and `skimr`, place a CSV with the same column names (`title`, `content`, `tags`, `image_urls`, `like_count`, `collect_count`, `comments_count`) next to the Rmd, and knit.

## Results (descriptive)

- The rules flagged about 18% of posts for a text-image mismatch indicator and about 6.2% for abnormal engagement.
- These are **rule hit rates**, not estimates of how much content on the platform is misleading or AI-generated.

## Limitations

- There are no ground-truth labels, so the heuristic score is not validated.
- The rules are crude. Image analysis is count-based only (image content is not analysed), and broad keywords (for example "most") are likely to flag many ordinary posts. Score thresholds are arbitrary.
- The prototype does not identify AI-generated content.
- It looks only at the content side, not at how users perceive or act on credibility cues.

## Next steps

1. **User-side study (main interest):** examine how users perceive and act on credibility cues, for example in an online experiment that varies one cue at a time and measures perceived credibility and behavioral intentions (clicking, sharing).
2. **Validation:** collect human credibility judgments for a sample of posts to test the heuristic score.
3. **AI-generated content:** study cues relevant to AI-generated content, such as provenance labels, rather than relying on keyword rules.
