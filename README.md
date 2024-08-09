# dockerinstallation
You can automate the installation of Docker on an Amazon Linux or Ubuntu system by writing a shell script. Here’s a sample script that you can save as install_docker.sh and run to install Docker:
#!/bin/bash

# Update the package repository
echo "Updating package repository..."
sudo yum update -y

# Install Docker
echo "Installing Docker..."
sudo yum install -y docker

# Start Docker service
echo "Starting Docker service..."
sudo systemctl start docker

# Enable Docker to start at boot
echo "Enabling Docker to start at boot..."
sudo systemctl enable docker

# Add your user to the Docker group (replace 'ec2-user' with your username if necessary)
echo "Adding current user to the Docker group..."
sudo usermod -aG docker $USER

# Verify Docker installation
echo "Verifying Docker installation..."
docker --version

echo "Docker installation complete. Please log out and log back in for group changes to take effect."

Steps to Use the Script
1.Save the Script: Copy the above code and save it to a file named install_docker.sh.

2.Make the Script Executable: Run the following command to make the script executable:
chmod +x install_docker.sh

3.Run the Script: Execute the script to install Docker:
./install_docker.sh

Explanation of the Script
Updating Package Repository: Ensures that your system’s package index is up-to-date.
Installing Docker: Installs the Docker package.
Starting Docker Service: Starts the Docker service so you can begin using it immediately.
Enabling Docker at Boot: Ensures that Docker starts automatically when the system boots.
Adding User to Docker Group: Adds the current user to the Docker group, allowing you to run Docker commands without sudo.
Verifying Installation: Prints the Docker version to confirm that the installation was successful.
After running this script, log out and back in or reboot the system for the group membership changes to take effect. Docker will be ready to use on your system.
