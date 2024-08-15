### **GenSummit: Elevate Long-Form Insights**

**GenSummit: Elevate Long-Form Insights** is a demonstration project showcasing the use of Amazon Bedrock and Generative AI to translate text from one language to another. This Proof of Concept (POC) provides users with the ability to generate long-form content, leveraging the Claude 3 model within Amazon Bedrock. The repository includes a basic frontend application, enabling users to quickly set up and test the translation capabilities in various formats, such as plain text, chat, or file-based inputs.

### **Goal of this Repository:**

The primary goal of this repository is to offer a straightforward way for users to experiment with Amazon Bedrock's capabilities in generating long-form content. By providing a simple frontend interface, users can interact with the application to translate text, assess the fluency and accuracy of the generated content, and easily adapt the code for other use cases or models within Amazon Bedrock.

### **Architecture and Flow:**

The architecture consists of a simple frontend application that communicates with Amazon Bedrock for translation tasks. Users can interact with the app through three different interfaces:

1. **Text Interface:**
   - Users input a prompt or use a default prompt.
   - The prompt is sent to Amazon Bedrock for translation.
   - The translated text is returned and displayed in the frontend.

2. **Chat Interface:**
   - Users input a chat-based conversation.
   - The chat is processed and sent to Amazon Bedrock.
   - The translated chat content is displayed in the frontend.

3. **File Interface:**
   - Users upload a text or PDF file for translation.
   - The file content is sent to Amazon Bedrock.
   - The translated file content is displayed in the frontend.

### **Step-by-Step Guideline:**

#### **Prerequisites:**
1. **Amazon Bedrock Access and CLI Credentials:** Ensure you have access to Amazon Bedrock and proper FM model access configured in the Amazon Bedrock console.
2. **Python 3.10 Installation:** Install Python 3.10, as it is the most stable version for the required packages. Download it [here](https://www.python.org/downloads/release/python-3100/).

#### **Step 1: Clone the Repository**
1. Open your terminal and run the following command to clone the repository:
   ```bash
   git clone https://github.com/aws-samples/genai-quickstart-pocs.git
   ```
2. Navigate to the cloned repository in your preferred code editor. The repo structure includes key files:
   - **Text.py, Chat.py, File.py:** Frontend application files for the corresponding interfaces.
   - **amazon_bedrock_translation.py:** Contains methods for interacting with Amazon Bedrock.
   - **requirements.txt:** Lists all the dependencies needed for the project.

#### **Step 2: Set Up a Python Virtual Environment**
1. Install `virtualenv`:
   ```bash
   pip install virtualenv
   ```
2. Create and activate a virtual environment in the root directory:
   ```bash
   python3.10 -m venv venv
   source venv/bin/activate  # For Linux/MacOS
   venv\Scripts\activate  # For Windows
   ```
3. Install the required packages from `requirements.txt`:
   ```bash
   pip install -r requirements.txt
   ```

#### **Step 3: Configure Environment Variables**
1. Create a `.env` file in the root directory of the repository.
2. Add your AWS CLI profile name to the `.env` file:
   ```bash
   profile_name=<AWS_CLI_PROFILE_NAME>
   ```
3. Ensure your AWS CLI profile has access to Amazon Bedrock. Adjust the region in `prompt_finder_and_invoke_llm.py` (line 23) if needed:
   ```python
   bedrock = boto3.client('bedrock-runtime', 'us-east-1', endpoint_url='https://bedrock-runtime.us-east-1.amazonaws.com')
   ```

#### **Step 4: Run the Application**
1. With the environment set up and all dependencies installed, start the application by running:
   ```bash
   streamlit run app.py
   ```
2. The application will open in your browser. You can now interact with the app to translate text, chats, or files.

By following these steps, you can easily set up and explore the capabilities of Amazon Bedrock in generating long-form content with translation tasks using the Claude 3 model.
