## This is a folder containing all the code scripts and library dependencies used in the code space.

#### Primarily used for Geospatial Analysis and development, having various libraries such as 
* **GDAL, 
* **Geopandas,** 
* **GEE**, 
* **Leafmap and others**

##### Important - The primary compiler run will be on Google Colab (*a jupyter notebook from google*) and having massive libraires so all of them are not going to be uploaded in the GitHub. Only specific libraries are placed for this.
---
# Setting up python env in AWS
Certainly! Here's a step-by-step guide with detailed explanations on setting up a Python environment similar to Google Colab on AWS:

1. **Create an AWS account**: If you don't already have an AWS account, you need to sign up for one. Go to the AWS website (https://aws.amazon.com/) and click on the "Create an AWS Account" button. Follow the instructions to create your account.

2. **Launch an EC2 instance**: Once you have an AWS account and are logged in to the AWS Management Console, navigate to the EC2 service. This service provides virtual servers in the cloud, known as Amazon Elastic Compute Cloud (EC2) instances.

   a. Click on the "Launch Instance" button to start the process of launching a new EC2 instance.

   b. Choose an Amazon Machine Image (AMI): An AMI is a pre-configured operating system and software stack for your EC2 instance. You can select an AMI based on your preference. For example, you can choose an Ubuntu AMI, which provides a Linux environment.

   c. Choose an instance type: Select the instance type that meets your requirements in terms of CPU, memory, storage, and networking capabilities. The available options range from general-purpose instances to high-performance instances with specialized hardware.

   d. Configure instance details: In this step, you can customize various settings such as the number of instances, network configuration, and storage options. The default settings should work for most scenarios, but feel free to adjust them based on your needs.

   e. Configure security groups: Security groups control the inbound and outbound traffic to your EC2 instance. During the launch process, you can create a new security group or select an existing one. Make sure to allow inbound traffic on port 22 (SSH) to enable SSH access to your instance.

   f. Review and launch: Review all the settings you've chosen for your instance. If everything looks correct, click the "Launch" button.

   g. Create a key pair: A key pair is used to securely connect to your EC2 instance via SSH. Choose an existing key pair or create a new one. If you create a new key pair, download the private key file (.pem) and keep it safe. You will need it later to establish an SSH connection.

   h. Launch the instance: After creating or selecting a key pair, click the "Launch Instances" button. AWS will start provisioning your EC2 instance.

3. **Connect to your EC2 instance**: Once your EC2 instance is up and running, you need to connect to it via SSH to install Python and set up the required environment.

   a. Retrieve the public IP address: In the EC2 Instances dashboard, locate your running instance and note down its public IP address. You will need this IP address to establish an SSH connection.

   b. Connect using SSH: Depending on your operating system, you can use different SSH clients. For Linux and macOS, you can use the built-in OpenSSH client. For Windows, you can use an SSH client like PuTTY.

      - For Linux/macOS: Open a terminal and run the following command:
      ```
      ssh -i <path_to_your_key_pair_file> ec2-user@<your_ec2_instance_public_ip>
      ```
      Replace `<path_to_your_key_pair_file>` with the path to your downloaded private key (.pem) file, and `<your_ec2_instance_public_ip>` with the public IP address of your EC2 instance.

      - For Windows (using PuTTY): Open PuTTY and enter your EC2 instance's public IP address in the "Host Name (or IP address)" field. Under "Connection" > "SSH" > "Auth," browse and

 select your private key (.pem) file. Click "Open" to start the SSH connection.

   c. You should now be connected to your EC2 instance via SSH.

4. **Install Python and required packages**: Once connected to your EC2 instance, you can install Python and any necessary packages using the package manager available for your Linux distribution. Here, we'll consider an Ubuntu-based instance.

   a. Update the package lists:
   ```
   sudo apt update
   ```

   b. Install Python:
   ```
   sudo apt install python3
   ```

   c. Verify the Python installation:
   ```
   python3 --version
   ```

   d. Install additional packages using `pip`, the Python package manager. For example, to install NumPy and pandas:
   ```
   pip install numpy pandas
   ```

   You can install any other required packages in a similar way.

5. **Set up a Jupyter Notebook server**: To replicate the notebook-style environment provided by Google Colab, you can set up a Jupyter Notebook server on your EC2 instance.

   a. Install Jupyter Notebook:
   ```
   pip install jupyter
   ```

   b. Start the Jupyter Notebook server:
   ```
   jupyter notebook --ip=0.0.0.0 --no-browser
   ```

   This command starts the Jupyter Notebook server and binds it to the IP address 0.0.0.0, allowing connections from any IP address. The `--no-browser` option ensures that Jupyter Notebook doesn't attempt to open a browser window.

   c. You will see output similar to the following:
   ```
   [I 09:30:00.123] [NotebookApp] JupyterLab extension loaded from /path/to/extension
   [I 09:30:00.123] [NotebookApp] JupyterLab application directory is /path/to/jupyterlab
   [I 09:30:00.123] [NotebookApp] Serving notebooks from local directory: /path/to/notebooks
   [I 09:30:00.123] [NotebookApp] Jupyter Notebook 6.4.0 is running at:
   [I 09:30:00.123] [NotebookApp] http://0.0.0.0:8888/
   ```

   Make note of the URL provided (e.g., `http://0.0.0.0:8888/`), as you will need it to access the Jupyter Notebook interface.

6. **Access Jupyter Notebook from your local machine**: With the Jupyter Notebook server running on your EC2 instance, you need to set up SSH port forwarding to access it from your local machine.

   a. Open a new terminal or command prompt on your local machine.

   b. Set up SSH port forwarding by running the following command:
   ```
   ssh -i <path_to_your_key_pair_file> -L 8888:localhost:8888 ec2-user@<your_ec2_instance_public_ip>
   ```
   Replace `<path_to_your_key_pair_file>` with the path to your private key (.pem) file, and `<your_ec2_instance_public_ip>` with the public IP address of your EC2 instance.

   c. Keep the terminal or command prompt open. It should remain active for as long as you want to use the Jupyter Notebook interface.

7. **Access Jupyter Notebook**: With SSH port forwarding set up, you can now open a web browser on your local machine and enter the following URL:
   ```
   http://localhost:8888/
   ```

   This URL corresponds to the J

upyter Notebook server running on your EC2 instance, and the SSH port forwarding redirects the traffic from your local machine to the EC2 instance.

   The Jupyter Notebook interface should load in your web browser, allowing you to create and run Python notebooks just like in Google Colab.

That's it! You now have a Python environment similar to Google Colab set up on AWS using an EC2 instance. You can create Python notebooks, install additional packages, and perform computations using the resources provided by your EC2 instance. Remember to properly manage and secure your EC2 instance to control costs and protect your data.