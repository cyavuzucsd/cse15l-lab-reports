# Researching commands 

Hello this is lab report 3 which will research one of the commands from less, find, and grep. For my lab report I chose to research the find command. 

--- 

## `find -type`

I was able to figure this command line option by using ChatGPT. It also happens to be the resource I used to find the rest of the three commands. This is because when I asked ChatGPT it gave me 8 commands which simplified my research!

The first example of using `find -type` was by using `find -type d` in written_2. The type command allows you to find the files of a specific type eg. files or directories. 

The output that I received was all the directories in written_2 as shown below:

```
[cs15lwi23agh@ieng6-201]:written_2:338$ find -type d
.
./non-fiction
./non-fiction/OUP
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Berk
./non-fiction/OUP/Castro
./non-fiction/OUP/Fletcher
./non-fiction/OUP/Kauffman
./non-fiction/OUP/Rybczynski
./travel_guides
./travel_guides/berlitz1
./travel_guides/berlitz2
```

This command helped find the directories in written_2. That is what the `d` stands for after `find -type`. The output was all the directories. This command is helpful to find all the directories in a specific path. 

The second example of using this command was `find -type f`. 

This was the output:

```
[cs15lwi23agh@ieng6-201]:written_2:351$ find -type f
./non-fiction/OUP/Abernathy/ch1.txt
./non-fiction/OUP/Abernathy/ch14.txt
./non-fiction/OUP/Abernathy/ch15.txt
./non-fiction/OUP/Abernathy/ch2.txt
./non-fiction/OUP/Abernathy/ch3.txt
./non-fiction/OUP/Abernathy/ch6.txt
./non-fiction/OUP/Abernathy/ch7.txt
./non-fiction/OUP/Abernathy/ch8.txt
./non-fiction/OUP/Abernathy/ch9.txt
./non-fiction/OUP/Berk/CH4.txt
./non-fiction/OUP/Berk/ch1.txt
./non-fiction/OUP/Berk/ch2.txt
./non-fiction/OUP/Berk/ch7.txt
./non-fiction/OUP/Castro/chA.txt
./non-fiction/OUP/Castro/chB.txt
./non-fiction/OUP/Castro/chC.txt
./non-fiction/OUP/Castro/chL.txt
./non-fiction/OUP/Castro/chM.txt
...
```

In the output above the three dots indicates more files that were outputted. The output indicated that `find -type f` returns all the regular files in the directory. Since there are a lot of files the output was very long and I shortened it to make sure the lab report is not unnecessarily long. This function is useful to help people find reguler files in a directory. 

## `find -size`

As I have said before I found about this command through ChatGPT. 

The `find -size` command allows you to find files with a specific size eg. 10 MB or 100 MB.

This is the first example of me using using `find -size`:

THe input was `find -size 1k`

The output was:

```
./travel_guides/berlitz1/HandRIbiza.txt
./travel_guides/berlitz1/HandRIstanbul.txt
```

This command displayed all the files in written_2 that were larger than 1 kilobyte. This function is useful in helping people figure out which files are larger than others directly from the terminal. In this case it was to figure out which files were specifically larger than 1 kilobyte. 

---

The second example of this command was:

`find -size +500`

The output was:

```
./travel_guides/berlitz1/WhereToItaly.txt
```

This function found all the files in written_2 that were bigger than 500 512-byte blocks. In this case it was only the one file in the output above. This command is useful to find specific files that are bigger than certain byte blocks. In this example it was 500 blocks. 

## `find -perm`

I found this command through ChatGPT. 

This command allows for the user to find files with certain permissions.

The first example includes making the input:

`find -perm 750`

The output:

```
./.git/hooks/commit-msg.sample
./.git/hooks/prepare-commit-msg.sample
./.git/hooks/update.sample
./.git/hooks/pre-rebase.sample
./.git/hooks/pre-merge-commit.sample
./.git/hooks/push-to-checkout.sample
./.git/hooks/pre-push.sample
./.git/hooks/pre-commit.sample
./.git/hooks/post-update.sample
./.git/hooks/pre-receive.sample
./.git/hooks/applypatch-msg.sample
./.git/hooks/fsmonitor-watchman.sample
./.git/hooks/pre-applypatch.sample
./written_2/non-fiction/OUP/Abernathy/ch1.txt
./written_2/non-fiction/OUP/Abernathy/ch14.txt
./written_2/non-fiction/OUP/Abernathy/ch15.txt
./written_2/non-fiction/OUP/Abernathy/ch2.txt
./written_2/non-fiction/OUP/Abernathy/ch3.txt
./written_2/non-fiction/OUP/Abernathy/ch6.txt
./written_2/non-fiction/OUP/Abernathy/ch7.txt
./written_2/non-fiction/OUP/Abernathy/ch8.txt
./written_2/non-fiction/OUP/Abernathy/ch9.txt
./written_2/non-fiction/OUP/Berk/CH4.txt
./written_2/non-fiction/OUP/Berk/ch1.txt
./written_2/non-fiction/OUP/Berk/ch2.txt
./written_2/non-fiction/OUP/Berk/ch7.txt
./written_2/non-fiction/OUP/Castro/chA.txt
./written_2/non-fiction/OUP/Castro/chB.txt
./written_2/non-fiction/OUP/Castro/chC.txt
...
```

This function displays all the files with the permission 750. This permission means all the files that the user can read, write, and execute. All the files group can read and execute. In addition to other not being able to do anything. This function can be useful to find these files with this specific permission. This might allow the user to understand which files they can read, modify, or execute. 

The permissions can be etter understood through the table at this link:

[https://www.multacom.com/faq/password_protection/file_permissions.htm]

---

The second example is:

`find -perm 700`

The output was nothing. In this case there was no file that fitted this permission. So there was no file that only allowed the user to read, write, and execute. This command can be useful in allowing the user to understand if they can even edit any files or not by placing a 0 instead of the 7. Furthermore the same goes for group and other. 

## `find -path`

I was able to find this command through ChatGPT. 

This command allows the user to find certain files in the path you specified.  

The first example of this command is:

`find -path '*/non-fiction/OUP*'`

The output was:

```
./non-fiction/OUP
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Abernathy/ch1.txt
./non-fiction/OUP/Abernathy/ch14.txt
./non-fiction/OUP/Abernathy/ch15.txt
./non-fiction/OUP/Abernathy/ch2.txt
./non-fiction/OUP/Abernathy/ch3.txt
./non-fiction/OUP/Abernathy/ch6.txt
./non-fiction/OUP/Abernathy/ch7.txt
./non-fiction/OUP/Abernathy/ch8.txt
./non-fiction/OUP/Abernathy/ch9.txt
./non-fiction/OUP/Berk
./non-fiction/OUP/Berk/CH4.txt
./non-fiction/OUP/Berk/ch1.txt
./non-fiction/OUP/Berk/ch2.txt
./non-fiction/OUP/Berk/ch7.txt
./non-fiction/OUP/Castro
./non-fiction/OUP/Castro/chA.txt
./non-fiction/OUP/Castro/chB.txt
...
```

This function finds all the files under the `/non-fiction/OUP` path in written_2. This is useful for users to learn which files are under a certain path for them to properly navigate through directories. In this case it was the `/non-fiction/OUP`.

---

The next example was:

`find -path '*/travel_guides/berlitz2*`

The output was:

```
./travel_guides/berlitz2
./travel_guides/berlitz2/Algarve-History.txt
./travel_guides/berlitz2/Algarve-Intro.txt
./travel_guides/berlitz2/Algarve-WhatToDo.txt
./travel_guides/berlitz2/Algarve-WhereToGo.txt
./travel_guides/berlitz2/Amsterdam-History.txt
./travel_guides/berlitz2/Amsterdam-Intro.txt
./travel_guides/berlitz2/Amsterdam-WhatToDo.txt
./travel_guides/berlitz2/Amsterdam-WhereToGo.txt
./travel_guides/berlitz2/Athens-History.txt
./travel_guides/berlitz2/Athens-Intro.txt
./travel_guides/berlitz2/Athens-WhatToDo.txt
./travel_guides/berlitz2/Athens-WhereToGo.txt
./travel_guides/berlitz2/Bahamas-History.txt
./travel_guides/berlitz2/Bahamas-Intro.txt
./travel_guides/berlitz2/Bahamas-WhatToDo.txt
./travel_guides/berlitz2/Bahamas-WhereToGo.txt
./travel_guides/berlitz2/Bali-History.txt
./travel_guides/berlitz2/Bali-WhatToDo.txt
./travel_guides/berlitz2/Bali-WhereToGo.txt
./travel_guides/berlitz2/Barcelona-History.txt
...
```

This function finds all the files under the `/travel_guides/berlitz2` path in written_2. This helps users to learn which files are under a certain path for them to understand the directories. This time the user learned about the files in the path `/travel_guides/berlitz2`.

