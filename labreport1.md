# How to log into a course specific account on ieng6

Hello, this blog post will teach you and give you steps on how to log into your ieng6 account.

---

## Step 1: Visual Studio Code

In order to access your ieng6 account you will need to have a terminal. The Visual Studio Code editor has a terminal we can use and is where you will most likely do your programming assignments in the future. 

To download Visual Studio Code click this link:

[Link](https://code.visualstudio.com/)

Once on screen click the button on the top right of the page to download the app as shown on the image below.

<img width="337" alt="Screenshot 2023-01-12 at 11 34 17 AM" src="https://user-images.githubusercontent.com/122561946/212163749-449e9143-8cea-44d5-9b20-de70e5f39ba4.png">

After downloading and opening the app your screen should look like this:

<img width="1252" alt="Screenshot 2023-01-12 at 11 40 11 AM" src="https://user-images.githubusercontent.com/122561946/212164871-976aaeb8-2b01-4b43-89b3-87fc37b04b6d.png">

---

## Step 2: Remotely connecting

Once in Visual Studio Code you will want to press the sqaure with a rectangle on the bottom as shown in the image below:

<img width="1249" alt="Screenshot 2023-01-12 at 9 34 56 PM" src="https://user-images.githubusercontent.com/122561946/212245092-30187bbb-ddfa-4b9d-8f73-b1ee40c5fa67.png">

Your terminal should look like below with the words specified for your device.

<img width="1254" alt="Screenshot 2023-01-12 at 9 45 45 PM" src="https://user-images.githubusercontent.com/122561946/212246344-8ee00a60-6afe-4316-a7c3-a15404fbb3b3.png">

Since I am a Mac user I did not have to download bash since it was already on my laptop. Fow Windows users you may have to download bash which is a step I skipped since it was not necessary for me.

After your terminal is open you want to copy the command below, but replace the three dashes with your unique code given to you:

`ssh cs15lwi23---@ieng6.ucsd.edu`

Once the screen asks your for your password:

<img width="485" alt="Screenshot 2023-01-12 at 9 51 01 PM" src="https://user-images.githubusercontent.com/122561946/212247468-f5bb814e-fa2a-404f-8bba-91b8f2860e33.png">

Enter the password you have created for your account.

Then you need to answer the following input as yes asking you if you would like to trust this computer.

Once you are connected it should look like below:

<img width="1244" alt="Screenshot 2023-01-12 at 9 53 59 PM" src="https://user-images.githubusercontent.com/122561946/212247622-7ba6a074-b619-4096-802c-8d277451776c.png">


Hooray! You have remotely connected!

---

## Step 3: Trying some commands

Now that you are remotely connected it is time for you to try some commands. You can experiment with the commands we learned in class or try some of the ones below:

`cd ~`
`cd`
`ls -lat`
`ls -a`
`cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`
`cat /home/linux/ieng6/cs15lwi23/public/hello.txt`
`ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lwi23/cs15lwi23---`, where --- is one of the other group members’ username

While I was in the lab I tried `ls -lat` whicgh gave me this output:

<img width="1232" alt="Screenshot 2023-01-12 at 10 15 03 PM" src="https://user-images.githubusercontent.com/122561946/212250557-a3762191-1806-49f9-9475-e03da3633622.png">

Then I tried `ls -a`: 

<img width="1203" alt="Screenshot 2023-01-12 at 10 16 14 PM" src="https://user-images.githubusercontent.com/122561946/212250665-ef4ab172-a45f-4fd3-980c-b1c5467d825e.png">

I also tried `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`:

<img width="1211" alt="Screenshot 2023-01-12 at 10 17 15 PM" src="https://user-images.githubusercontent.com/122561946/212250835-5c92d523-1691-4642-99c5-4140ce4cd110.png">

I ran all the commands which were on the week 1 website for CSE15L. I only included three screenshots to not make the lab report unnecessarily long. 

Congratulations! You have completed all the steps!

