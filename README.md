## Towards Mitigating API Hallucination in Code Generated by LLMs with Hierarchical Dependency Aware

This repository provides the resources for our work on mitigating API hallucination in code generation based on hierarchical dependency. It includes the constructed benchmarks and the prompt templates designed for evaluation and analysis.


### APIHulBench

#### Benchmark Resources

We provide the necessary project repositories for constructing the benchmark, which can be downloaded from the following Google Drive link: [Download Project Repositories](https://drive.google.com/file/d/12c46In9w9fqJyU-qAAKccMSVycFIszOz/view?usp=sharing)

#### Benchmark Files

* [APIHulBench-F](https://github.com/yujiachen99/APIMitigation/blob/main/APIHulBench_F.jsonl): Represents early-stage programming with limited code context.
* [APIHulBench-M](https://github.com/yujiachen99/APIMitigation/blob/main/APIHulBench_M.jsonl): Represents later-stage programming with richer code context.

#### JSONL Format
Each line in the file represents a sample with the following fields:

* **project_path**: Path to the project repository.
* **project_description**: Brief description of the project.
* **file_path**: Path to the file containing the incomplete function.
* **incomplete_function**: The incomplete function requires an API call.
* **line_location**: The line number of the API call.
* **ground_truth**: The correct API call for the incomplete function.

### Prompt Template

The [prompt template](https://github.com/yujiachen99/APIMitigation/blob/main/prompt_template.py) integrates hierarchical dependency information to provide a structured context for LLMs. It includes:

* **Project Description**: A brief overview of the project's purpose, providing essential background for the LLM.
* **Global Dependency**: Simplified skeletons of related and current files, including class definitions, member fields, and function signatures, to represent the broader project structure.
* **Local Dependency**: Called functions and reference APIs that are directly relevant to the incomplete function, serving as its immediate context.
* **Incomplete Function**: The target function.

