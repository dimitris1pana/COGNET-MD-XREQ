# COGNET-MD<X-REQ>
The COGNET-MD-X-REG framework is fed curated Multiple Choice Questions (MCQs) from various medical fields. This integration with IoT enables dynamic dataset updates, allowing for real-time adaptability and scalability in evaluation, which ensures that the LLM model has access to our latest and most relevant data for evaluation. When a defined threshold or specific criteria are met, the system initiates the evaluation process with the updated COGNET-MD data for requirement extraction (X-REQ), simulating real-world conditions. Images are missing due to anonymisation requirements. This code is a part of the COGNET-MD project. OpenAi models used in this use case can be replaced by others.  

## Table of Contents

- [Requirements](#requirements)
- [Usage](#usage)
- [License](#license)
- [Contact](#contact)

## Requirements

1. Python 3.9
    * Python Libraries:
    * openai
    * pandas
    * requests
    * dotenv
    * base64
    * seaborn
    * matplotlib
    * networkx
    * json
2. Enviroment variables
    *OpenAI API key stored in an .env file as API_KEY

To install the required dependencies, run the following commands:
```bash
pip install openai pandas requests python-dotenv seaborn matplotlib networkx
```
```bash
# Clone the repository
git clone https://github.com/dimitris1pana/COGNET-MD-XREQ.git

```

## Usage

The Multimodal LLM evaluation begins with data processing. Here’s a summary of the process:

1. Data Processing: A set of MCQs and their answers is selected based on domain-specific requirements. Each question is paired with an image and the correct answer, forming a structured dataset for the LLM evaluation.
2. Prompt Engineering: The Rules of Conduct define the prompt format and expected response structure from the LLM, setting essential constraints for analyzing multimodal inputs. The Configuration specifies the model type, token size, and other parameters, ensuring consistent and controlled model responses.
3. Evaluation and Scoring: Each question is presented to the LLM as an image-text pair, accompanied by defined rules and configuration settings. The model’s response includes an answer choice, which is evaluated for correctness, with detailed scores and explanations provided for each incorrect response. This structured, automated process, leveraging IoT for real-time data updates, enables a scalable and effective assessment of the LLM's performance in multimodal tasks, particularly those relevant to medical domains.

## GenPathologyQuiz: Quiz Evaluation and API Interaction

Functionality:

Reads quiz data from Excel files containing questions and image paths.
Encodes each image and sends requests to the OpenAI API for automated answers.
Evaluates responses against the correct answers and calculates a score.
Outputs evaluation results with explanations for incorrect responses.
1. Key Functions:
    * encode_image: Encodes images to base64 for API processing.
    * excel_to_array: Reads and structures Excel data for each image-question pair.
    * send_request: Sends API requests and handles retries if necessary.
    * evaluate_responses: Compares responses against correct answers and computes scores.

## analysis: Result Analysis and Visualization
Functionality:

Parses and categorizes responses from JSON files for each quiz, aggregating scores and incorrect answers.
Visualizes scores, abbreviations, and correct/incorrect answers.
Performs Named Entity Recognition (NER) on explanations and builds relationship graphs based on identified entities.

1. Key Functions:

    * json_to_csv: Converts JSON quiz data to CSV format for analysis.
    * send_request: Makes API calls for NER on explanations.
    * Network Graph Visualization: Illustrates entity relationships based on NER results using networkx.
2. Visualization. This script generates visualizations to analyze trends and evaluate the performance and extract finetuning requirements (X-REQ) of the LLM:

    * Score Distribution: Bar charts showing quiz scores.
    * Entity Frequency: Counts and distributions of named entities within incorrect and correct responses.
    * Network Graphs: Graphical relationship maps between entities to assess connections and patterns in responses

## License

This project is licensed under the Attribution 4.0 International (CC BY 4.0) license. This allows for sharing and adaptation, provided appropriate credit is given.

Learn more about this license at [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/)


## Citation

If you use this project or reference the COGNET-MD dataset or methodology in your research, please cite the following paper
@misc{panagoulias2024evaluatingllmgenerated,
      title={Evaluating LLM -- Generated Multimodal Diagnosis from Medical Images and Symptom Analysis}, 
      author={Dimitrios P. Panagoulias and Maria Virvou and George A. Tsihrintzis},
      year={2024},
      eprint={2402.01730},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2402.01730}, 
}


## Contact

Dimitrios P. Panagoulias - [panagoulias_d@unipi.gr](mailto:panagoulias_d@unipi.gr)

Project Link: [https://github.com/dimitris1pana/COGNET-MD-XREQ.git](https://github.com/yourusername/cognet-md-xreq.git)

