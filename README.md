# ProfitPanda

ProfitPanda is an AI-powered financial analysis tool that automates the extraction and interpretation of complex Profit & Loss (P&L) statements. By leveraging advanced language models, it enables users to query financial data using natural language, making financial analysis more accessible and efficient.

## Key Features

- **Natural Language Queries**: Ask questions about your P&L data in plain English
- **Automated Data Extraction**: Seamlessly process CSV/Excel sheets containing financial data
- **AI-Driven Analysis**: Utilize state-of-the-art language models for accurate insights
- **Efficient Workflow Integration**: Structured process flow for optimized query handling and response generation
- **Database Storage**: Reliable storage and retrieval of analysis results

## Benefits

- 📈 **Automated Finance**: Reduce human error with AI-driven extraction and analysis
- ⚡ **Enhanced Efficiency**: Minimize manual intervention and optimize resource utilization
- 🚀 **Responsive Query Handling**: Get timely and accurate responses to your financial queries

## API Endpoints

- `/stats`
- `/result/{task_id}`  (for dev)
- `/call`
- `/callback`   (marketplace prod callback)

## Installation

1. **Clone the repository**:
    ```bash
    https://github.com/AbhinavNarang777/solidus_profitpanda_backend.git
    cd solidus_profitpanda_backend
    ```

2. **Create and activate a virtual environment**:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install the dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

## Running the Application

1. **Set up the environment variables** (see [Environment Variables](#environment-variables) section).

2. **Run the application manually**:
    ```bash
    uvicorn main:app --reload
    ```

   The application will be available at `http://127.0.0.1:8000`.

3. **Run the application using docker**:
   Ensure docker desktop is installed and running prior to build.
   
   Build command:
   ```
   docker build -t <your custom name here>
   ```

   Run command:
   ```
    docker run -p 8000:8000 -p 8888:8888 <your custom name here>
   ```
   The application will be available at `http://127.0.0.1:8000`.

## Environment Variables

```
$ CONFIG='{
    "PYTHON_HOST": "localhost",
    "PYTHON_TOKEN": <auto added on docker run>,
    "PYTHON_USE_HTTPS": false,
    "PYTHON_PORT": 8888,
    "SAMBANOVA_API_KEY":"<your key here>",
    "SAMBANOVA_MODEL_NAME":"<model choice>",
    "BASE_URL":"https://api.sambanova.ai/v1",
    "PUBLISHER_KEY": "",
}'
``` 

## Setting Up a Jupyter Notebook Client
If you use docker, the jupyter client will be automatically initiated and the key will be extracted and injected in config. However, if you want to do it manually, follow the below steps:

To set up a Jupyter Notebook client in the same directory as the Solidus Backend project, follow these steps:

1. **Install Jupyter Notebook**:
    If you haven't already, you need to install Jupyter Notebook. You can do this using pip:
    ```bash
    pip install notebook
    ```

2. **Start Jupyter Notebook**:
    Navigate to the project directory and start the Jupyter Notebook server:
    ```bash
    jupyter notebook
    ```

3. **Access Jupyter Notebook**:
    After running the above command, your default web browser will open and you will be able to access the Jupyter Notebook interface. Copy the token to config and set in `PYTHON_TOKEN` key.
