# COMPASS: Process Mining based Methodology for Prompt Optimization of LLM Agents

COMPASS (COMprehensive Process AnalySiS) is a methodology for optimizing prompts for Large Language Model (LLM) based agents through process mining techniques. COMPASS systematically applies process mining techniques to discover, analyze, and guide agent behavior.  This repository contains the artifacts from our case study applying COMPASS to a natural language to SPARQL query transformation agent.

## Use Case: Natural Language to SPARQL Query Transformation

Our case study applies COMPASS to [Graf-von-Data (GvD)](https://graf.ti.rw.fau.de/), an agent that transforms natural language questions into SPARQL queries by exploring knowledge graphs. GvD implements the ReAct framework and utilizes three specialized tools:

1. **Search**: Identifies entity URIs based on natural language keywords
2. **Describe**: Extracts incoming and outgoing triples from specified entity URIs
3. **Query**: Executes generated SPARQL queries on the knowledge graph and returns result sets

The agent is deployed on a semiconductor industry supply chain knowledge graph that models semiconductor organizations, their sites, and supply relations. The dataset contains 33,755 triples and represents realistic complexity typical of industrial knowledge graphs.

### Knowledge Graph and Queries

The knowledge graph and evaluation queries are available in a separate repository under version v0.1:
- [SupplyBench Repository](https://github.com/wintechis/supplybench/tree/v0.1)
- The evaluation queries are all queries from the [SupplyBench Evaluation](https://github.com/wintechis/supplybench/blob/v0.1/query-corpus/queries.n3) that are tagged as "one triple pattern", "two triple patterns", "three triple patterns", or "four triple patterns".

### Project Structure

- **`data/`**: Contains trajectories, event logs, and evaluation results
  - `trajectories/`: Raw agent trajectories across optimization iterations
  - `event-logs/`: Processed event logs for process mining analysis
  - Evaluation result files comparing different prompt versions
- **`pm4py-data-analysis/`**: Analysis notebooks and scripts using [PM4Py](https://github.com/process-intelligence-solutions/pm4py)
- **`pmtk-data-analysis/`**: Analysis results from the paper using [PMTK](https://processintelligence.solutions/pmtk)
- **`prompts/`**: Different versions of the agent prompts developed through COMPASS


