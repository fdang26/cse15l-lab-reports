# Step 4)
*Keys pressed:*
<br>
`<up>,<enter>`  
  
Having the command `ssh cs15lwi23aln@ieng6.ucsd.edu` in my local terminal's history as my most recent command made it so I could access it by pressing `<up>` just once and then entering.

# Step 5)
*Keys pressed:* 
<br>
`<Ctrl>+<V>,<enter>`
<br>
`cd lab<tab>,<enter>`  
  
I had the command `git clone git@github.com:fdang26/lab7.git` saved to my clipboard so all I had to do was paste it and then enter. While the system was 
cloning the repo I entered the second set of commands (`cd lab<tab>) and entered it to change my working directory to the repo right after it finished cloning.

# Step 6)
*Keys pressed:* 
<br>
`<up><up><up><up><up><up><up><up><up><up><up><up><up>, <enter>`  
  
In the previous attempts I had learned that it was possible to combine the compile and run commands into `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java && java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples` to save time by searching for one set of commands instead of having to search the history twice.
I pressed `<up>` thirteen times until I found the compile and run command in the search history. It was this high up because of extraneous commands I used in the previous run like `ls` and `cd`ing into the wrong directories.

# Step 7)
*Keys pressed:* 
<br>
`cp ../L<tab> .`
<br>  
The above command was a way I had found out to shorten the amount of time needed to edit the file. 
Essentially, I had an already-edited file saved in the parent directory that wasn't wiped every run. 
I would overwrite the ListExamples.java in the current working directory with that file instead of going 
into the file with nano to manually fix the bug, saving me around 20-30 seconds per run.

# Step 8)
*Keys pressed:* 
<br>
`<up><up>, <enter>`
<br>  
The saved time from combining the compile and run commands into one line adds up here since I only 
had to find one set of commands again by pressing up just twice until I found the line in the history. 

# Step 9)
*Keys pressed:* 
<br>
`git add .`  
`git commit -m "m"`  
`git push`  
<br>  
For these commands, I figured it'd be easier if I just typed them out manually, rather than searching by pressing up and potentially missing it by pressing up too many times. The commit command option `-m` was useful in skipping the vim editor that is usually opened by commiting with a message on the command line, although, admittedly, the message is not very practical.

