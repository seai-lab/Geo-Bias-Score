# Geo-Bias Score Toolkit

## Overview
Geo-Bias Score (GBS) is a collection of information-theoretic, model-agnostic metrics of how much geospatial bias (i.e., non-uniform performance across different regions on Earth) there is when we evaluate a model. It is complementary to existing model performance metrics such as accuracy, precision, recall and reciprocal rank. This project aims at providing a plug-and-play toolkit for researchers to painlessly benchmarking the geo-bias of their models and encouraging them to report the geo-bias scores alongside with other metrics, in hopes of boosting the fairness and trustworthiness of spatial data analysis and GeoAI research -- In fact, we find that while introducing fine-grained geospatial information into models greatly improves the performance, it also significantly increases geo-bias. It is important to pay attention to both sides of the coin. 

Different geo-bias scores focus on different spatial aspects of geospatial bias. In this initial version, we introduce two most important categories of GBS: **Spatial Self-Information (SSI)** Scores and **Spatial Relative Information (SRI)** Scores. As the names indicate, SSI focuses on the bias originating from the spatial arrangement within each region of interest (i.e., _self_-information), while SRI focuses on the bias originating from the mis-alignment between global model performance and local model performance (i.e., _relative_ information). Each category of GBS consists of different GBS implementations, further specifying what spatial arrangement/mis-alignment we exactly take into consideration. Select the GBS implementation that best fits your research questions.

We will be actively supporting more GBS categories in the future.

## Supported Geo-Bias Scores Categories
### SSI Scores
#### Presence-Only SSI
It measures the “base” strength of spatial patterns of the neighborhood against which we evaluate our model. Starting from the base geo-bias, the spatial distribution of low-performance observations may further increase or decrease the SSI of the neighborhood. 
#### Relative SSI
We define relative geo-bias score as the difference between the SSI of the low-performance observations generated by our models and the SSI of completely random low-performance observations. This score measures the “relative” strength of spatial patterns of the low-performance observations. In our experiments, we compute the base geo-bias scores and the relative geo-bias scores for all neighborhoods that contain low-performance observations and report the average.
### SRI Scores
