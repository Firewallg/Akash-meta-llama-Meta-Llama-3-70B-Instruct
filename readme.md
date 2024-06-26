# How to run `Akash-meta-llama-Meta-Llama-3-70B` On Akash Network
- Prepare your application for deployment:

    - Ensure that Llama 3 70B with 16-bit quantization is properly packaged and ready for deployment. This includes all necessary files, dependencies, and configurations.

- Make sure you have a Huggingface account with access to the Llama 3 models
- Wallet with AKT tokens. You'll need these to pay for deployment  costs     

- Create a deployment manifest:

   - Create a deployment manifest (usually in YAML format) specifying the details of your application, such as image, resources, environment variables, and any other required configurations. You can refer to the 
      Akash documentation for the structure of this manifest.
   - Use [this](https://github.com/Firewallg/Akash-meta-llama-Meta-Llama-3-70B-Instruct/blob/main/yaml.yaml) yaml file for this build.

- Now, go to http://console.akash.network and log in with your AKT wallet.  Click on "Deploy" and select "Build Your Template"
- Switch to the YAML editor
- Use [this](https://github.com/Firewallg/Akash-meta-llama-Meta-Llama-3-70B-Instruct/blob/main/yaml.yaml) yaml file for this build and paste in the yaml editor
- In the deployment file, set your Huggingface access token as an  environment variable. This will allow you to access the Llama 3 models
- Click "Create Deployment" and monitor bids from providers coming  in. Choose a provider that meets your requirements and create a lease
- Then, wait for the deployment to boot up - this may take some time because the model is 130GB
- Once the deployment is up and running, check the logs for a  throughput message every 10 seconds. This indicates that the deployment  has successfully started
- You can now access your Llama 3 70B endpoint  by clicking on url  provided by the deployment provider.
     
# Interacting With The Chat Meta/llama-3 bot

- After successful deployment use the [code]() to interact with the chat meta bot.
- For Testing on Postman API use the following
 ```
  Method: POST
Endpoint: http://<host>/v1/chat/completions
Headers:
Content-Type: application/json

Body (raw JSON):
      
  {
    "model": "meta-llama/Meta-Llama-3-70B-Instruct",
    "messages": [
        {"role": "user", "content": "What is the weather forecast for tomorrow?"}
    ]
}


      
  ```
- Make sure to replace <host> with the actual host where the model is deployed
- Adjust the question and user ID in the JSON body as needed
- After setting up the request in Postman with these details, you can simply hit the Send button to interact with the chatbot. You'll receive the response from the API containing the chatbot's answer.
- Enjoy

# Test Resluts
![image](https://github.com/Firewallg/Akash-meta-llama-Meta-Llama-3-70B-Instruct/assets/97313245/94015a44-d0c5-4117-a4d0-ddc9530599cd)
# Link to the [screen recording](https://youtu.be/iluT2lOf7Bg) of the model test run.
