# NasdaqGPT

The main goal of our project is to develop a chatbot that serves as a financial advisor, providing quick and accurate answers to questions about companies listed on NASDAQ. For context, NASDAQ is one of the largest stock exchanges in the world, known for its high-tech stocks and innovative companies.

## Requirements

- Python >= 3.10.12
- pip
- Access to AWS with the necessary credentials

## Project Configuration

1. Clone this repository:

    ```bash
    git clone https://github.com/tu-usuario/aws_s3_data_downloader.git
    cd aws_s3_data_downloader.git
    ```

2. Create and activate a virtual environment:

    For Unix (Linux/MacOS):

    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

    For Windows:

    ```bash
    python -m venv venv
    venv\Scripts\activate
    ```

3. Install the dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Create a `.env` file in the project root directory with the following content, replacing the values ​​with your AWS credentials:

    ```env
    AWS_ACCESS_KEY_ID=your_access_key_id
    AWS_SECRET_ACCESS_KEY=your_secret_access_key
    BUCKET_NAME=anyoneai-datasets
    PREFIX=nasdaq_annual_reports/
    LLAMAPARSE_API_KEY='YOUR_LLAMAPARSE_API_KEY'
    OPENAI_API_KEY='YOUR_OPENAI_API_KEY'
    ```
5. Run all cells in data_exploration.ipynb

## Use

You have two options to run the chatbot.  
1. Generate a virtual environment and run the following command in your terminal to install all the dependencies:
```bash
streamlit run index.py
```
2. Run the following command in your terminal to build a docker image with the DockerFile, after the process finished, go to the next url in a browser: `http://localhost:8501/`, just remember to execute [data_exploration.ipynb](notebooks%2Fdata_exploration.ipynb) before it, to generate the vectorestore. 
```bash
docker build .
```



## Questions Examples

You can try for example this questions:

Question: What was 1-800-Flowers.com, Inc.'s cost of revenues in 2022?  
Expected Answer: In 2022, 1-800-Flowers.com, Inc.'s cost of revenues was $1,386.1 million.  
Reference:NASDAQ_FLWS_2022_page66.

Question: What type of cloud services did 21Vianet Group, Inc. start offering in 2013 and 2014?  
Expected Answer: In 2013, 21Vianet Group, Inc. started offering public cloud services, and in 2014, private cloud services and hybrid cloud services.  
Reference PDF: NASDAQ_VNET_2015_page 67

Question: What was 21Vianet Group, Inc.'s basic loss per share in 2018 and 2019  
Expected Answer: 21Vianet Group, Inc.'s basic loss per share in 2018 was (0.30) RMB, and in 2019 it was (0.27) RMB (0.04 USD).  
Reference PDF: NASDAQ_VNET_2019_page_4#   F i n A d v i s o r  
 