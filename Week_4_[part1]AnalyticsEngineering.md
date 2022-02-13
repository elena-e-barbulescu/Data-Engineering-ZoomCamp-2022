# Week - 4 - Learning || Analytics Engineering - part 1

## Data Engineer:

- Prepares the infrastructure that the data team needs.

## Data Analyst:

- Uses the data to answer question and solve problems.

## Analytics Engineer:

- Combines the data (software) engineering practices to the efforts of data analysts and data scientists


## Elements of Dimensional Modeling

ie. The Start Schema

### Fact Tables:

- measurements, metrics or facts
- corresponds to a business process
- usually defined by “verbs”

### Dimention Tables

- Corresponds to a business entity
- Provides context to a business
- usually defined by “nouns”

## The Architecture of Dimensional Modeling

Can described using the restaurant analogy:

- Staging Area
    - Raw data / not meant to be exposed to everyone
- Processing Area
    - Movement of raw data to data models
    - Focused on efficiency and standards
- Presentation Area
    - Final delivery of data to the users
    - Exposure to business stakeholders
    

## DBT:

- Tranformation tool : allows for deployment of analytic code following the engineering best practices such as modularity, portability, CI/CD, and documentation
- This is done by a development workflow.
