---
layout: page
title: "Instructor Setup"
sharing: false
footer: true
---

As an instructor, you will use an Instructor VM that will allow you to run scenarios and observe the scoring
events that you can use for assessment. The edurange code that runs the two scenarios that we have is
already installed on the Instructor VM and it launches new VM instances and configures them. Currently,
we have created one instructor machine that you can use or you can make a copy and customize it for your
class. You can start and stop different exercises from the Instructor machine. The AWS console gives you
a way to start and stop the instructor machine and to kill any Amazon Instances (AMIs) that were created
by the instructor machine. For each scenario, there a YAML file in the edurange directory that specifies the
exercise. It includes the number of students and what their passwords are. These can be changed in the
YAML file subject to the resource limitations of the account. In general, students will each have their own
EC2 instances to log into and work on the exercises (first they connect through an external IP address to a
Gateway). The next section will lead you through starting an instructor machine and how to use it to create
the scenarios. There are two modes for using EDURange. You may be using your own account or you may
be using the EDURange group account. The use of those two modes will described separately.

### Starting the instructor machine from the EDURange account ###
If you are going to use the EDURange account, you will need the URL for the EDURange account, a username and password, and you will need to be a member of the edurange group or the edufac group. In the future, we will provide a form on this website for you to request access, but for now send e-mail. Once you have an account, the URL to sign in will be https://edurange.signin.aws.amazon.com/console 

After you login to the console, you can navigate to EC2. Once you log in, you will navigate to EC2. At the upper right, there will be a dropdown tab for the different AWS centers. You want East (N Virginia) and you should see a heading called Resources. Under that, click on the link to Running Instances. You should see a list of instances. You want one of the instructor instances, e.g. locasto-instructor.

#### Starting the instructor machine ####
1. Scroll down to Locasto-Instructor machine. Look at its instance status. If it is ”running” then it will have an external IP address and you can login to it. You can login to this VM with the credentials ubuntu/edurange12. If it is stopped, then click on the box next to the instance and go to the Actions pull-down tab at the top, and you can start it. You can also right click on the word “stopped” and you should see an option to start it. The circle in the status will turn from red to yellow and finally, to green. This can take 5 minutes. It will first say initializing, but eventually the status check will be complete and you can login. On the lower part of the screen, you will see the public IP address, using ssh client (on Windows you can use PuTTY), Be sure to stop the machine when you are done with the exercise. Do not terminate it, since that will remove it completely.
2. If you created your own Instructor machine, you must configure it. You can set the username and password, as well as a key pair, in the AWS console. AWS can generate a key pair for you.
Note: If you are new to EDURange, you can just use the existing Instructor machine and start it.
3. After logging in to the instructor machine,
    cd edurange

### Usage ###
    
We now have two scenarios - 
- recon.yml, a host discovery game with a scoring site (github.com/sboesen/edurange_scoring)
- elf.yml, an scenario with an instances with where 'ls' has an elf infection. Scoring is being developed to support elf and other scenarios.

Browse to http://ip:3000/scenarios/new, and select from a template if you want to use one of them.

### Contributing ###

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
