# Six Steps to Data Science
A quick set of steps to getting up and running with jupyter notebooks on your computer


# 1. Docker
Docker runs natively on Mac, Windows, and Linux.  Find the appropriate version for your computer here: 
- [Docker for Mac](https://docs.docker.com/docker-for-mac/)
- [Docker for Windows](https://docs.docker.com/docker-for-windows/)
- Docker for Linux: [go here and find your distro](https://docs.docker.com/)

I recommend using the “stable” branch. Make sure you have about 10 gigabytes of disk space free, then follow the installation instructions. 
[In addition to the [docs](https://docs.docker.com/), here’s [a cheat sheet](https://github.com/wsargent/docker-cheat-sheet) for when you want to explore more.]

# 2. The Command Line
Now that you have docker installed, go to the command prompt (here are instructions for [windows](http://www.digitalcitizen.life/7-ways-launch-command-prompt-windows-7-windows-8), [mac](https://developer.apple.com/library/content/documentation/OpenSource/Conceptual/ShellScripting/BeforeYouBegin/BeforeYouBegin.html#//apple_ref/doc/uid/TP40004268-CH1-SW1), [linux](https://www.linux.com/learn/how-use-linux-command-line-basics-cli)) and type the following commands: 

`> mkdir jupyternotebooks`    
(This will create a new directory for your work. Alternatively, you could just use your documents folder, or any folder in which you would like to store code and data.)

`> docker run -v /jupyternotebooks:/home/jovyan/work -d -p 8888:8888 jupyter/datascience-notebook`    
(This will install jupyter, link its folder to your working directory, and make its http port accessible to your browser.)


While you wait for docker to do its thing, you can read more about this jupyter “docker stack” [here](https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook).  (Or, if you want to really impress nerds with your command line mastery, you can learn about [vim](http://www.labnol.org/internet/learning-vim-for-beginners/28820/), [grep](https://quickleft.com/blog/command-line-tutorials-finding-grepping/), [sed and awk](https://quickleft.com/blog/command-line-tutorials-sed-awk/).)

# Not a Step: What is going on here? 
You just installed a “container engine” inside your computer that can host lots of different types of “contained” computer images.  This is great because:
* _Science!_ Everything you do is now [fully reproducible](https://arxiv.org/pdf/1410.0846.pdf) on any computer that runs an open source container engine. No more “which version of which software on which platform?” 
* _Isolation = fewer conflicts._ No more messing with your computer’s settings or having conflicting apps. Everything is “contained” in a container.  
* _Isolation = better security._ Because docker containers are relatively isolated, you can configure each with distinct passwords, encryption, secure connections to private github accounts, etc. 
* _Scalable._ You can -- when you are a bit more advanced -- do the same thing on a much more powerful computer (or cluster of computers) in the cloud. 
