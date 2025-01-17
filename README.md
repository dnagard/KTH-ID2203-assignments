# ID2203 Exercises
There are three different ways to run the lab exercises:
- Virtual Machine
- Docker container
- Local installation

This guide will focus on the Docker container method as it is completely automated and requires no manual installation of dependencies while the developer can use their host machines IDE to develop the exercises. However, you can find a guide for the other methods on the Canvas course.
## Prerequisites
You should have docker installed on your machine. If you don't have it installed, you can follow the instructions [here](https://www.docker.com/).
I suggest you to use VSCode as your IDE, as it is the one that I have tested, however, feel free to use any other IDE that supports remote development.
## Setting up VSCode
Before starting you should add the Remote - Containers extension to your VSCode. You can do this by going to the extensions tab and searching for Remote - Containers (`ms-vscode-remote.remote-containers`).
![remote-containers-vscode](https://github.com/user-attachments/assets/66b8bec0-7770-48db-bfb0-3129aac37d3b)
If it has been successfully installed, you should see a blue icon on the bottom left corner of your VSCode window (the colour might be different if you are using a custom theme).
![remote-container-icon-vscode](https://github.com/user-attachments/assets/a3a889b4-f791-442e-b6fc-f206fd387e06)
## Opening the project in a container
First, you must clone our template repository. You can do this by running the following command in your terminal:
```bash
git clone https://github.com/datasys-lab/KTH-ID2203-assignments.git
```
After cloning the repository, you should open the project in VSCode. At this moment a notification should appear in the bottom right corner of your screen asking you to reopen the project in a container. Click on the `Reopen in Container` button.
![reopen-in-container-vscode](https://github.com/user-attachments/assets/e1762a5b-7366-4e77-aff4-bc3ecb0a5d5f)
If the notification does not appear, you can open the command palette by pressing `Ctrl+Shift+P` and typing `Dev Container: Reopen in Container` or clicking on the left bottom icon and selecting `Remote-Containers: Reopen in Container`. This will initiate the process of building the container and installing all the dependencies, as it is the first time the container is being built, it might take a while (around 2 minutes), but do not worry, the next time you open the project it will be instantaneous.

When the window is ready, you should see a terminal at the bottom of your screen, this terminal will have all the dependencies required for doing the assignments. You can run the lab exercises by running the following command:
```bash
sbt run
```
It should work but sometimes the first run returns an error that looks like this:
![sbt-kompics-error](https://github.com/user-attachments/assets/366542a3-7020-40fb-8caf-f23a032be740)
If this happens, you can fix it by running the following command:
```bash
sbt clean
```
And then running the `sbt run` command again. Now everything should work as expected and you should see a success message in the terminal.
![kompics-succeed](https://github.com/user-attachments/assets/409875af-9353-4197-8609-2e4c3911a83e)
As you can see even though it has succeeded the output says that not all properties are satisfied, this is because the exercises have not been implemented yet, but you can start implementing them now. After completing your exercise the outputs should say that all properties are satisfied and return a token that you should paste into the header of the file before submitting it on canvas.

For the following assignments just add the scala exercise file to ``src/main/scala/se/kth/edx/id2203/templates`` and use sbt to execute it.

HAVE FUN! 🎉
