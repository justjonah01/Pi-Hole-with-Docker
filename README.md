# Pi-Hole-with-Docker on Windows
### Project showcasing how I set up Pi-Hole inside a Docker container.
This document both a reference for me and a guide for beginners.

## 1. Install Docker Desktop and Set Up


This can be done at the following [link]([url](https://docs.docker.com/desktop/setup/install/windows-install/?utm_source=chatgpt.com#wsl-verification-and-setup)). Run through the default options it gives once the intstaller loads.

Now open PowerShell and run "docker --version", this will confirm that the installation went through fine.

If this is your first time using Docker on your machine there is a good chance you will be promtped to update Windows Subsystem in Linux (WSL). Run a ipconfig in CMD to get the IP of your current machine, you will need this later.

## 2. Create a Folder and Put Stuff In It!

In Powershell, go ahead and make a directory for your Pi-Hole Project. Depending on how organized you want to be you can just make one folder. I went ahead and make two, one for my future containers and one for this project.

<img width="522" height="187" alt="image" src="https://github.com/user-attachments/assets/bb0f2f48-ad99-4cb7-82fd-3089ee345987" />

Then you will need to make a file called "docker-compose.yml". These files are necessary for running Docker containers.

The command for making a file in Powershell is New-Item so the command is "New-Item docker-compose.yml". Then you will need to open said file with "Invoke-Item docker-compose.yml". You can use my .yml document in this repo, it should satisfy the requirement for this project.

## 3. The Fun Part

Now we actually are able to get into cool stuff.

Inside the project folder, run the command "docker compose up -d" in Powershell. If you see a bunch of stuff starting to run, you are on the right track!

Well what did you just run exactly? The command "docker compose up -d" is basically telling Docker to run what you just had in the compose file. That is the (docker compose up) part of the command. The flag -d tells Docker to run the process in the background, letting you still use your precious Powershell window.

Remember your IP you logged earlier with ipconfig? Well now go to your browser to choice and enter in the IP with a "/admin"
 on the end of it. You should see the image below in your browser if done correctly so far.

 <img width="477" height="535" alt="image" src="https://github.com/user-attachments/assets/39687e5f-592a-44c4-ab87-59fe9a8f9a06" />
 

Go ahead and use the password in the .yml file or if you have replaced it use yours instead.

##

Below is the dashboard of what your Pi-Hole should look like.

<img width="924" height="895" alt="image" src="https://github.com/user-attachments/assets/c863ad6d-4317-4e4a-bfc4-e70b08613357" />


## 4. Putting This Into Action

You will have to now tell your router to use the Pi-Hole. For me this is done in my routers app as it does not have a web dashboard. I headed to the app and went into DNS settings. Finally I changed the DNS to the IP that we used earlier to use it as our DNS instead. Finally reboot your router if it has already not given you the option to.

Just like that you have Pi-Hole in a Docker Container.
