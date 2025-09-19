# Semantic Hotel Likeability Ranker
##### Usage of Gen AI features of Bigquery AI

## Introduction: 

This notebook builds a  using BigQuery + Vertex AI text embeddings. It runs a one-off backend step to create hotel-level “master” embeddings and a vector index in BigQuery, then simulates a frontend journey for specific users: fetch their past reviews, produce a query embedding that reflects what they liked, perform a vector search over hotel embeddings, re-rank results, and visualize why the top hotels match their historical preferences.



## Notebook contains the following:

1. Setting application configurations at one place
2. Data preparation and cleansing
3. Master Embeddings generation
4. Hotel data retrieval (HotelFetcher)
5. User profile and preferences retrieval (UserFetcher, UserPreferenceGenerator)
6. Embedding generation (QueryEmbedder)
7. Semantic search (SemanticSearcher)
8. Ranking and scoring (Ranker)
9. Visualization and explainability (Visualizer)

## Responsibilities:
- Execute the full personalized hotel recommendation flow.
- Ensure outputs are explainable and validated.
- Provide a single entry point for notebooks.

## Includes simulation of various user journeys:

### User 1: which has only 1 previous review and travelling to a same previous city again.

Expectation: Hotels should be suggested based on the review and hotels should be boosted up that matches the user profile.

### User 2: which has 2-3 previous reviews for multiple destinations but travelling to a previous travelled destination.

Expectation: Hotels should be suggested based on the combination of previous reviews and hotels should be boosted up that matches the user profile.

### User 3: which has many reviews for a specific desination but is now travelling to a new city.

Expectation: Hotels should be suggested based on the combination of previous reviews that matches the semantic similarity with the hotels in the new destination and hotels should be boosted up that matches the user profile.
