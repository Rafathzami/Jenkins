# Jenkins_windows
This contains jenkins installation methods 
# Jenkins Installation Guide (Windows)

This guide provides step-by-step instructions for installing Jenkins on Windows and adding SSL certificates.

## Prerequisites

- Windows operating system
- Administrator access to the machine

## Installation Steps

1. **Download Jenkins:**
   - Go to the official Jenkins website: [https://www.jenkins.io/](https://www.jenkins.io/)
   - Click on the "Download Jenkins" button.
   - On the Downloads page, select the Windows installer package (.msi file) that matches your system architecture (32-bit or 64-bit).
   - Save the .msi file to your local machine.

2. **Install Jenkins:**
   - Locate the downloaded .msi file and double-click on it to start the installation process.
   - If prompted, allow the installer to make changes to your device.
   - Follow the on-screen instructions:
     - Click "Next" in the "Welcome to the Jenkins Setup Wizard" window.
     - Choose the installation directory where you want to install Jenkins or accept the default location.
     - Select the desired options for Jenkins (components to install, whether to install as a Windows service).
     - Choose the port number for Jenkins (default is 8080).
     - Choose the service user for Jenkins (default system user or specify a custom user).
     - Review the installation settings and click "Install" to start the installation process.
     - Wait for the installation to complete.

3. **Complete the Setup Wizard:**
   - Once the installation is finished, the Setup Wizard will launch automatically.
   - Retrieve the initial administrator password:
     - Open the file called "initialAdminPassword," located in the Jenkins installation directory (e.g., C:\Program Files\Jenkins\secrets\initialAdminPassword).
     - Copy the password.
   - Return to the Setup Wizard and paste the copied password into the "Administrator password" field.
   - Click "Continue" to proceed.

4. **Customize Jenkins (Optional):**
   - In the "Customize Jenkins" page, you can choose to install recommended plugins or select specific plugins based on your requirements.
   - Click "Install" to begin the plugin installation process.

5. **Create an Admin User:**
   - In the "Create First Admin User" page, enter the details for the Jenkins administrator account (username, password, full name, and email address).
   - Click "Save and Finish" to complete the setup process.

6. **Adding SSL Certificates:**
   - Obtain the SSL certificate and private key files from a trusted certificate authority or generate a self-signed certificate.
   - Copy the SSL certificate file (.crt) and the private key file (.key) to a secure location on your machine.
   - Open the Jenkins installation directory (e.g., C:\Program Files\Jenkins).
   - Rename the SSL certificate file to `jenkins.crt` and the private key file to `jenkins.key`.
   - Open a command prompt as an administrator and navigate to the Jenkins installation directory.
   - Run the following command to import the SSL certificate:
     ```
     java -jar jenkins.war --httpPort=-1 --httpsPort=8443 --httpsKeyStore="jenkins.jks" --httpsKeyStorePassword="<password>"
     ```
     Replace `<password>` with a password of your choice.
   - Access Jenkins using the HTTPS URL: [https://localhost:8443](https://localhost:8443)

Congratulations! You have successfully installed Jenkins on Windows and added SSL certificates.

For more information and advanced configuration options, refer to the [Jenkins Documentation](https
