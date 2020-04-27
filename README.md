Steps

clone the repo 

get the full path where is code clone


config.vm.synced_folder "paste the your system repo complete path here", "/home/ubuntu"

vagrant up

vagrant ssh



For ASSIGMENT part


after the vagrant up go inside the vagrant and copy and past nginx.conf in to below path
/etc/nginx/sites-enabled/default
and restart the nginx server.

in my case url is https://192.168.10.5/login?from=%2F

go to this location of your system cat /var/jenkins_home/secrets/initialAdminPassword
copy the password and past on the https://192.168.10.5/login?from=%2F login page.Pleae also see the picture 1.

For User Tracking we will use Martrix bases auth plugins





PLEASE THIS PART CAREFULLY BECAUSE IT IS GUI BASED CONFIGRATIONS




and copy the nginx.conf file in default file 

edit the default file with your system file below

"server your_system_ip:8080 fail_timeout=0"

after close and save restart the nginx server

service nginx restart

in my case url is https://192.168.10.5/login?from=%2F

go to this location of your system cat /var/jenkins_home/secrets/initialAdminPassword

copy the password and past on the https://192.168.10.5/login?from=%2F login page.Pleae also see the picture 1.

For User Tracking we will use Martrix bases auth plugins

after sucessfully login install the recommended plugins jenkins will install the necessary plugins which we will need for basic operation.

in jenkins for user activity tracking and audit we will use matrix based authencation plugin however there are many other auth plugins are availible but this best fit for us.

for matrix based auth we have to enable it it has very versitile in the sence let we want a specific user only build a specific build and see the specific pipeline etc.

go to the 

mange jenkins --> configure global security ---> enable jenkins's own user database ---> enable project bases matrix authorization stragey

and the user here which you want under this auth.

but before doing this please create the user as

click on people --> create user ---> enter the relevant detail of the user.

These steps enable security for user so that we can easilty track the user activity. 


Now comes the build part as

for enabling and trigering jenkins on every commit here is the setting in jenkins

click new item ----> enter the job name ----> enter free style project -----> save ----> enable 

after saving you will get into the main page click on the free style project name that you have just given 

click configure -------> enable the radio for  "GitHub project" and enter the project url as in my case https://github.com/Wasbas/Assinment/

enable the radio for "git" and enter the git url as https://github.com/Wasbas/Assinment.git no credential require because this repo is alreday public

in the same page you will see BUILD heading under this heading you will executes the shell commands even for single build.


                                         But before the doing this enable the github plugins for integrations

for this plugin installation

go to the "mange jenkins"  ----> mange plugins ----> click on the availble tab -------> here you will search "GitHub Integration Plugin" after that install and enable it.
this activity enable enables our required plugins.

THE END.


for windows install gitbash
for linux ubuntu
apt install git

git clone https://github.com/Wasbas/Assinment.git

cd Assinment

remove .git folder in linux rm -rf .git

git clone your repo url here


copy the Assingment foler in your new repo

directory structue look like
newrepofolder/Assinment/

git add .
git commit -m "myassignment one"

git push origin master

now check your github console

