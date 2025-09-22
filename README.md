# Semantic Hotel Likeability Ranker
##### Usage of Gen AI features of Bigquery AI

## Notebook Introduction: 

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

## Notebook Responsibilities:
- Execute the full personalized hotel recommendation flow.
- Ensure outputs are explainable and validated.
- Provide a single entry point for notebooks.

## Notebook includes simulation of various user journeys:

##### User 1: which has only 1 previous review and travelling to a same previous city again.

Expectation: Hotels should be suggested based on the review and hotels should be boosted up that matches the user profile.

##### User 2: which has 2-3 previous reviews for multiple destinations but travelling to a previous travelled destination.

Expectation: Hotels should be suggested based on the combination of previous reviews and hotels should be boosted up that matches the user profile.

##### User 3: which has many reviews for a specific desination but is now travelling to a new city.

Expectation: Hotels should be suggested based on the combination of previous reviews that matches the semantic similarity with the hotels in the new destination and hotels should be boosted up that matches the user profile.


## Executive Summary
Booking a hotel should be exciting, not exhausting. Yet for most travellers it feels like work – scrolling through endless listings, juggling filters, and comparing reviews until the fun of trip planning fades away. A hotel likeability ranker powered by BigQuery AI can change that, making hotel search faster, smarter, and more personal.
#### The Problem: Too Many Choices, Too Little Joy
Planning a trip starts out fun but quickly turns into a chore.
-- Travellers spend over 5 hours researching across 38 different sites, clicking through 141 pages before making a decision.
-- Around 81% of people abandon their booking cart before finishing.
The struggle isn’t just on the traveller’s side. Online Travel Agencies (OTAs) feel the pain too. They face:
-- Low conversion rates (0.2% - 4%).
-- High churn (15%-25% each year).
-- Marketing costs of £30-£50 per new customer.
With little differentiation to set them apart, many OTAs end up competing on price alone – squeezing profits and leaving customers unsatisfied.
#### The Solution: Semantic Hotel Likeability Ranker
What if your travel site could understand your preferences and know what you want?
That’s where a hotel likeability ranker powered by BigQuery AI Semantic Detective comes in. Instead of dumping hundreds of generic hotel results, it:
-- Displays hotels ranked according your likeability and preferences.
-- Cuts booking time from hours to a few minutes.
-- Makes the process feel like personal recommendations from a trusted friend, not a database search.
By ranking hotels based on what you’re most likely to love, this prototype turns hotel booking into an effortless discovery rather than a frustrating transaction.
#### The Value: Happier Travellers, Stronger OTAs
This smarter, intent-driven approach is a win-win.
-- For travellers: Less stress, less time spent, and more confidence in every booking.
-- For OTAs: Visible drop in cart abandonment, better conversion rates, lower acquisition costs, and stronger profit margins boosted by increased customer loyalty.
Instead of being just another site in an endless list of tabs, with the hotel likeability ranker, an OTA can become the go-to destination, standing out in a crowded market.
