# find options    
[Link](https://linuxhandbook.com/find-command-examples/) used
<br>
## find -name 
```
[cs15lwi23aln@ieng6-201]:written_2:453$ find -name "*Italy.txt"
./travel_guides/berlitz1/HistoryItaly.txt
./travel_guides/berlitz1/IntroItaly.txt
./travel_guides/berlitz1/WhatToItaly.txt
./travel_guides/berlitz1/WhereToItaly.txt
```
```
[cs15lwi23aln@ieng6-201]:written_2:454$ find -name "*HongKong*"
./travel_guides/berlitz1/HandRHongKong.txt
./travel_guides/berlitz1/HistoryHongKong.txt
./travel_guides/berlitz1/IntroHongKong.txt
./travel_guides/berlitz1/WhatToHongKong.txt
./travel_guides/berlitz1/WhereToHongKong.txt
```
This option is probably my most used option for this command. With the -name option, you can search through directories for a file or a directory that matches the argument that you provide, as opposed to just spitting out all of the files and subdirectories of the given path. (The stars I used in search expression just mean that the filename can have any text surrounding the phrase "HongKong" as long as it contains HongKong.)

## find  -type d  
For example, if you knew the directory was "berli"-something, you could find just the directories and not include the file matches.
```
[cs15lwi23aln@ieng6-201]:written_2:468$ find -type d -iname "berli*"
./travel_guides/berlitz1
./travel_guides/berlitz2
```
  
vs. without type -d 
  
```
[cs15lwi23aln@ieng6-201]:written_2:469$ find -iname "berli*"
./travel_guides/berlitz1
./travel_guides/berlitz2
./travel_guides/berlitz2/Berlin-History.txt        
./travel_guides/berlitz2/Berlin-WhatToDo.txt       
./travel_guides/berlitz2/Berlin-WhereToGo.txt 
```  
Or to display the filetree with all the nested subdirectories:    
```
[cs15lwi23aln@ieng6-201]:written_2:455$ find -type d
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
This option restricts the search results to only be directories since, by default, the find command will display both matched files and matched directories. This option can prevent extraneous output if you know you need to look for a certain place where files are being stored and not the files themselves. It can also be useful to see the relative paths to all of the subdirectories of a given directory so that you can see what the file tree looks like and see where everything is stored.
## find -o  
```
[cs15lwi23aln@ieng6-201]:written_2:470$ find -name "*HongKong*" -o -name "*Italy*"
./travel_guides/berlitz1/HandRHongKong.txt
./travel_guides/berlitz1/HistoryHongKong.txt       
./travel_guides/berlitz1/HistoryItaly.txt
./travel_guides/berlitz1/IntroHongKong.txt
./travel_guides/berlitz1/IntroItaly.txt
./travel_guides/berlitz1/WhatToHongKong.txt        
./travel_guides/berlitz1/WhatToItaly.txt
./travel_guides/berlitz1/WhereToHongKong.txt       
./travel_guides/berlitz1/WhereToItaly.txt addition, most top-line hotels have upscale
```
```
[cs15lwi23aln@ieng6-201]:written_2:472$ find -name "*Cuba*" -o -name "*Rico*"
./travel_guides/berlitz2/Cuba-History.txt
./travel_guides/berlitz2/Cuba-WhatToDo.txt
./travel_guides/berlitz2/Cuba-WhereToGo.txt        
./travel_guides/berlitz2/PuertoRico-History.txt    
./travel_guides/berlitz2/PuertoRico-WhatToDo.txt   
./travel_guides/berlitz2/PuertoRico-WhereToGo.txt 
```  
This option allows you to search for multiple patterns within one command so that the output will displays the matches for both. This is applicable if you want to find multiple files/directories at once without having to separate your searches which would consequently separate the results. 
  
## find -maxdepth
```
[cs15lwi23aln@ieng6-201]:written_2:478$ find -maxdepth 2
.
./non-fiction
./non-fiction/OUP
./travel_guides
./travel_guides/berlitz1
./travel_guides/berlitz2
``` 
```
[cs15lwi23aln@ieng6-201]:written_2:479$ find -maxdepth 2 -iname "*berl*"
./travel_guides/berlitz1
./travel_guides/berlitz2
```
Find can be a finnicky command sometimes because it searches recursively through *all* of the subdirectories, and with some folders containing a lot of files, that can be a bit much. With the maxdepth option, the find command can kind of function as `ls` with a specfied depth of search, given that you don't use any other options. In short, the `-maxdepth` option can be useful for limiting the range of the command's search.
