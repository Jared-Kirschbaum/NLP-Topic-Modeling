# Topic Modeling with Latent Dirichlet Allocation (LDA)

## Project Overview

This project applies Latent Dirichlet Allocation (LDA) to uncover latent topics in Mutual UFO Network (MUFON) sighting reports. The project integrates geospatial data to identify regional topic distributions across the United States. LDA is chosen for its robustness in topic modeling and is adapted for shorter texts using TF-IDF vectorization.

## Objectives

- Analyze MUFON sighting reports to extract meaningful topics.
- Integrate geospatial data to visualize regional distributions of topics.
- Develop insights into patterns and trends within UFO sighting reports.

## Dataset

The dataset used in this project consists of MUFON sighting reports. The data includes textual descriptions of sightings along with geospatial information (e.g., latitude and longitude).

## Methodology

### 1. Data Preprocessing

- **Cleaning the Text Data**: This involves removing stop words, punctuation, and performing lemmatization to ensure the text is in a suitable form for analysis.
- **TF-IDF Vectorization**: Transform the text data into numerical features. Term Frequency-Inverse Document Frequency (TF-IDF) is a statistical measure used to evaluate how important a word is to a document in a collection or corpus.

    The formula for TF-IDF is:

    $$\text{TF-IDF}(t, d) = \text{TF}(t, d) \times \text{IDF}(t)$$

    where:

    - $\text{TF}(t, d)$ is the term frequency of term \( t \) in document \( d \).
    - $\text{IDF}(t)$ is the inverse document frequency of term \( t \), calculated as:

    $$\text{IDF}(t) = \log \frac{N}{|\{d \in D : t \in d\}|}$$

    where \( N \) is the total number of documents and \( |\{d \in D : t \in d\}| \) is the number of documents containing term \( t \).

### 2. Topic Modeling with LDA

**Latent Dirichlet Allocation (LDA)**: A generative statistical model that allows sets of observations to be explained by unobserved groups. It posits that each document is a mixture of a small number of topics and that each word in the document is attributable to one of the document's topics.

The LDA model involves the following parameters:

- $\alpha$: The parameter of the Dirichlet prior on the per-document topic distributions.
- $\beta$: The parameter of the Dirichlet prior on the per-topic word distribution.
- $\theta_d$: The topic distribution for document $d$.
- $\phi_k$: The word distribution for topic $k$.

The generative process for LDA is as follows:

1. For each document $d$:
    - Draw a topic distribution $\theta_d \sim \text{Dir}(\alpha)$.
    - For each word $w$ in document $d$:
        - Draw a topic $z \sim \text{Multinomial}(\theta_d)$.
        - Draw a word $w$ from $P(w \mid z, \beta)$.

    The model is optimized using techniques such as Variational Inference or Gibbs Sampling to estimate the posterior distributions of the latent variables.

### 3. Geospatial Analysis

- **Integration of Geospatial Data**: Combine the extracted topics with the geospatial data to analyze and visualize the regional distribution of topics.
- **Visualization**: Use mapping tools to create visual representations of topic distributions across different regions in the United States. This helps in identifying regional patterns and trends in UFO sightings.

## Analysis and Results

- **Topic Extraction**: LDA was used to extract a set of coherent topics from the MUFON sighting reports. Each topic is represented by a set of keywords, and each document is represented by a mixture of topics.
- **Geospatial Visualization**: The integration of geospatial data allowed for the creation of maps showing the distribution of topics across different regions. This visualization provided insights into regional patterns and trends in UFO sightings.

### Findings

- **Topic Coherence**: The topics extracted were found to be coherent and meaningful, capturing distinct themes within the sighting reports.
- **Regional Trends**: Certain topics showed distinct regional trends, indicating that specific types of sightings were more prevalent in certain areas.

## Usage

1. Open the Jupyter Notebook:
    ```bash
    jupyter notebook topic_modeling_kirschbaum.ipynb
    ```

2. Follow the instructions in the notebook to preprocess the data, run LDA, and visualize the results.

## Conclusion

This project demonstrates the application of LDA to extract topics from UFO sighting reports and integrate geospatial data to visualize regional patterns. The insights gained from this analysis can contribute to understanding trends and patterns in UFO sightings.

## Author

Jared Kirschbaum

## Acknowledgements

- Colorado State University for providing the resources to pursue this project.
- MUFON for the sighting report data.
