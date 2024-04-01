# WebQuery-Chatbot

Welcome to the WebQuery-Chatbot project! While Large Language Models (LLMs) like OpenAI's GPT have brought us leaps forward in understanding and generating human-like text, they aren't always up-to-date with the latest web content. My curiosity led me to wonder: could we create a chatbot that not only taps into the power of these models but also fetches real-time information from the web?

Here's why I embarked on this project:
- **Stay Current:** I wanted to fetch the latest web content for any query, bridging the gap between the static knowledge of LLMs and the dynamic nature of the internet.
- **Context Matters:** By integrating LLMs with a direct pipeline to web content, the goal was to create more relevant and context-aware responses, tailored specifically to the user's current needs.

## Getting Started

### Prerequisites

- Ensure you have Python installed on your machine. This project is developed using Python 3.10.
- It's recommended to use a virtual environment for Python projects to manage dependencies effectively.

### Installation

1. **Clone the Repository**: Clone the project to your local machine.
    ```bash
    git clone https://github.com/Raunak-Sarmacharya/WebQuery-Chatbot.git
    ```
    
2. **Navigate to the Project Directory**:
    ```bash
    cd WebQuery-Chatbot
    ```

3. **Set Up a Virtual Environment** (Optional but recommended):
    - For Conda users:
        ```bash
        conda create --name webquery-chatbot python=3.10
        conda activate webquery-chatbot
        ```
    - For venv users:
        ```bash
        python3 -m venv webquery-chatbot-env
        source webquery-chatbot-env/bin/activate  # On Windows use `webquery-chatbot-env\Scripts\activate`
        ```

4. **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

5. **Set Up Environment Variables**: Create a `.env` file in the project root directory and add your OpenAI API key.
    ```plaintext
    OPENAI_API_KEY=your_api_key_here
    ```
    Replace `your_api_key_here` with your actual OpenAI API key.

### Running the Application

To run the WebQuery-Chatbot on your machine:
```bash
streamlit run src/app.py
```

## Process Model

The WebQuery-Chatbot operates through a sophisticated process involving several components, each playing a vital role in fetching, processing, and generating responses based on web content. Here is an overview of the application's process model:

```plaintext
[User Interaction with Streamlit UI]
                |
                V
   [Query & Website URL Input] ---> [WebQuery-Chatbot Application]
                |
                V
           [Lang Chain]
                |
                V
  [Content Fetch & Process] ---> [Chroma Vectorization]
                |                        |
                V                        V
    [OpenAI's GPT Model] <--------- [Vectorized Content]
                |
                V
      [Response Generation] ---> [Display in Streamlit UI] ---> [User]
```

## Detailed Steps in the Process

### 1. **User Interaction with Streamlit UI**
Users initiate the process by inputting their query and the target website URL through the Streamlit interface.

### 2. **Query & Website URL Input**
These inputs are then forwarded to the main WebQuery-Chatbot application for processing.

### 3. **Lang Chain**
Acts as the intermediary between the application and OpenAI's GPT models, enhancing the chatbot's understanding of both the query and the web content's context.

### 4. **Content Fetch & Process**
The specified website's content is fetched and pre-processed to identify and structure the information relevant to the user's query.

### 5. **Chroma Vectorization**
This crucial step involves converting the fetched web content into vectorized format, enabling efficient information retrieval and context understanding.

#### Why Vectorization Matters
- **Efficient Information Retrieval:** Vectorization allows for quick similarity searches, identifying the most relevant content pieces to the user's query.
- **Enhanced Context Understanding:** Vectors capture semantic relationships, aiding the AI in generating semantically aligned responses.
- **Scalability and Speed:** Vectorization makes the analysis and response generation processes more scalable and faster.
- **Precision in Response Generation:** Operating within a vector space improves the precision of AI-generated responses, ensuring they are informative and contextually relevant.

### 6. **OpenAI's GPT Model**
Utilizes the vectorized content to understand the query's context and generates a coherent, detailed response.

### 7. **Response Generation**
The AI-crafted response is prepared to be displayed back to the user.

### 8. **Display in Streamlit UI**
The response is showcased through the Streamlit UI, providing the user with the sought-after information.

### 9. **User Receives Response**
Completes the interaction loop, offering the user a direct, insightful answer based on the web content's context.
