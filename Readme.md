# GraphDB vs RelationalDB

This project compares the performance and efficiency of a **Graph Database (Neo4j)** and a **Relational Database (MySQL)** using a real-world dataset derived from academic research data. It evaluates how each database handles complex relationships and multi-perspective queries, with a focus on execution time and query structure.

## Project Overview

While relational databases are optimized for transactional processes and structured data, graph databases excel in representing and querying complex, interconnected data. This project explores those differences by:

- Creating equivalent relational and graph data models
- Running a set of real-world queries in both MySQL and Neo4j
- Measuring query execution times using Python
- Analyzing the efficiency and suitability of each database type for various use cases

## Dataset and Use Case

The dataset is based on research articles, researchers, affiliations, publishers, DB indexers, and research projects. Data was obtained via:

- **Web scraping** from Google Scholar
- **Manual augmentation** with structured metadata (e.g., generated researcher IDs, affiliations)
- **Storage** in CSV files which were imported into MySQL and Neo4j

## Technologies Used

| Tool         | Purpose                              |
|--------------|--------------------------------------|
| Python       | Web scraping, query automation       |
| MySQL        | Relational database implementation   |
| Neo4j        | Graph database implementation        |
| SQL          | Querying MySQL                       |
| Cypher       | Querying Neo4j                       |
| BeautifulSoup| Web scraping                         |


## Evaluation Methodology

A Python script was used to:
- Connect to both MySQL and Neo4j
- Run equivalent queries in each database
- Record execution time for each query

**Sample Queries:**
- Retrieve article-author-publisher relations
- Filter articles by funding source
- Aggregate researchers and affiliations
- Identify unpublished research projects with leads/co-leads

## Key Findings

| Query Description                                                   | MySQL Time | Neo4j Time |
|---------------------------------------------------------------------|------------|------------|
| Article with DBID = 'IEEE3'                                        | 0.004s     | 0.002s     |
| Articles with DBID = 'ACM5' and PID = 'QAP1'                        | 0.002s     | 0.002s     |
| Articles with funding ≥ 15000                                      | 0.005s     | 0.002s     |
| Research projects not yet published with lead/co-lead info         | 0.016s     | 0.009s     |
| Full multi-join article-author-affiliation-project-type extraction | 0.06s      | 0.013s     |

**Neo4j outperformed MySQL** in complex queries involving multiple relationships and joins.

## Citation

Paper Inspiration:
> *University Research Graph Database for Efficient Multi-Perspective Data Analysis using Neo4j*  
> IEEE ITIS 2020 – [Read here](https://ieeexplore.ieee.org/document/9320965)

---



