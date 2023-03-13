## find options/flags   
## sources:  
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
  
vs.  
  
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
$ grep -w "side" WhatToHongKong.txt 
        be more expensive than smaller “family” shops tucked away in the side
```  
 
  
## find -maxdepth
```
$ grep -Erl "Hong Kong|Taiwan"
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HistoryHongKong.txt
written_2/travel_guides/berlitz1/IntroHongKong.txt
written_2/travel_guides/berlitz1/WhatToHongKong.txt
written_2/travel_guides/berlitz1/WhatToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt        
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt       
written_2/travel_guides/berlitz2/California-WhereToGo.txt   
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/China-History.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
...
``` 
```
$ grep -Erl "kayak|paddleboard"
written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/WhatToIsrael.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt       
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt       
written_2/travel_guides/berlitz2/Crete-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt      
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
(The option -r is explained above, and the option -l replaces the output to just be the name of the file where the match was found) The option -E, regex option, allows for a regular expression (regex) to serve as the pattern to match with and can be useful to search according to a pattern rather than hardcoded strings. In the examples above, I only used "|" in the regex to add multiple keywords to search for, but the -E flag can have many different applications.
