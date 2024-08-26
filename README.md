# Local GPT (Run AI Locally on your PC)
Run AI locally on your computer with out connecting to Internet or other AI services and use AI privately.

## Step 1 - Installing WSL (Windows Sub-System for Linux) and Ubuntu 
To begin, open the Terminal application on your Windows system. Next, install WSL using the following command:
`wsl --install`
This process may prompt you to reboot your system. If so, restart your computer and allow the installation to complete automatically after the reboot.

Once the installation is finished, you will be prompted to set up a UNIX username and password. Follow the prompts to create your account.

After completing the setup process, wait for the WSL installation to finish. You should eventually see the "Welcome to Ubuntu" message, indicating that the installation was successful.

![installing Ubuntu](https://github.com/user-attachments/assets/927c1b3a-528d-4fb2-8418-88ac6aaeae10)

## Step 2 - Updating Packages
To ensure that your Ubuntu system has the latest software updates, run the following commands:
`sudo apt update` and `sudo apt upgrade -y`

- `sudo apt update`: This command updates the package index to reflect the availability of the latest packages in the Ubuntu repository. It's a best practice to keep the package list up-to-date before upgrading or installing new software.
- `sudo apt upgrade -y`: This command upgrades all installed packages to their latest versions, using the updated package list from the previous step. The `-y` flag is used to automatically answer "yes" to any prompts that may appear during the upgrade process.

![2-sudo update](https://github.com/user-attachments/assets/542500e7-7db4-4acf-8364-c56c294dfaa0)

![3-sudo upgrade](https://github.com/user-attachments/assets/1e6ae289-b8d3-44be-a451-9db99c65a538)

## Step 3 - Installing Ollama 
To install LLaMA, follow these steps:
- Visit "Ollama.ai" and select "Linux" as the installation option.
- Copy the provided code snippet and paste it into your terminal application.

![4-download ollama](https://github.com/user-attachments/assets/a5c36504-e786-4e64-935e-1c52fd63be09)
  
Once you've pasted the code, wait for the installation to complete. You'll know it's finished when you see the message "Install Complete".

![5-installation-successful](https://github.com/user-attachments/assets/ef71f5a6-2cbc-4bdc-8fa2-040bc71732fa)

Verification: To confirm that LLaMA is running successfully, you can open a web browser and navigate to `http://localhost:11434`. If Ollama is installed correctly, you should see the Ollama is running.

![6-localhost-running](https://github.com/user-attachments/assets/9f292ba6-0b3d-48ef-bd69-b9f5fb633ff6)

## Step 4 - Pulling and Running LLaMA model in CLI
Now that we have Ollama installed, let's pull down the LLaMA-3 model using the following command:
`ollama pull llama3`

This will download and install the LLaMA-3 model. Once the installation is complete, you should see the output "success".

![7-install_llama3](https://github.com/user-attachments/assets/5c3af434-fbcf-4e9c-a859-f014716f9e60)

### Running the Model: 
To interact with the LLaMA-3 model in a command-line interface (CLI), use the following command:
`ollama run llama3`

This will launch the CLI and allow you to chat with the LLaMA-3 model. You can ask it questions or engage in conversation. To quit the conversation type `/bye`.

![8-running llama3 in CLI](https://github.com/user-attachments/assets/bfde63d8-22bb-4b97-9372-106f30e7450c)


## Step 5 - Installing Docker on Ubuntu for Open WebUI 
To use Open WebUI with LLaMA, you need to install Docker. The following commands add Docker's official GPG key and repository to your system.
- First, update the package index `sudo apt-get update` and then install necessary packages for Docker installation `sudo apt-get install ca-certificates curl` and `sudo install -m 0755 -d /etc/apt/keyrings`.
- Create a new directory and install Docker's official GPG key `sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc`.
- Set the permissions for the GPG key `sudo chmod a+r /etc/apt/keyrings/docker.asc`.
- Add Docker's repository to Apt sources - `echo
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" |
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`. This allows you to install Docker from the official repository.
- Finally, update the package index again `sudo apt-get update` to reflect the newly added repository.


![11 WebUI-Docker-initial_requirement](https://github.com/user-attachments/assets/0b033dab-c03d-4205-86bd-f314de179832)

### Installing Docker: 
To install docker and its command-line interface (CLI), container runtime (containerd.io), buildkit plugin and compose plugin use this command -
`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`

![12-Installing Docker](https://github.com/user-attachments/assets/7da44126-ab1f-4204-bd87-27a60054c296)

You can verify the installation using command - `sudo docker ps`

![13-verify_install](https://github.com/user-attachments/assets/b0a88aca-4719-4446-b5be-77bb02043293)

These commands are specific to Ubuntu and might vary slightly depending on your Linux distribution or version.

## Step 6 - Accessing Open WebUI 
Now that we have Docker installed, let's access Open WebUI on our local machine.

Open a web browser and navigate to `http://localhost:8080`. You should see the Open WebUI interface.

- Sign-up and Initial Setup: Click "Sign-up" and create an account. The first person to sign up locally will have admin access.
- Accessing the interface: You can view a similar Ui to OpenAI's ChatGPT. You need to select the model which you have installed - Llama3

## Congratulations !!!

You can now use Llama3 locally and there are many features imbedded into Open WebUI. You can use different chats and you can use voice, attack documents and many more. 

If you want to install other models to your machine locally, navigate to Ollama.ai and navigate to models. You can choose your required model, run the command - `ollama pull model_name` to use it in Open WebUI locally.

## Credits 
This project was developed through NetworkChuck's youtube video - [host ALL your AI locally](https://youtu.be/Wjrdr0NU4Sk?si=H-38TUSBJWRurCgc)
For additional help and other features you can view his youtube channel - [NetworkChuck](https://www.youtube.com/@NetworkChuck)

Follow his website - [NetworkChuck](https://networkchuck.com)
Follow his academy - [NetworkChuck Academy](https://academy.networkchuck.com)
