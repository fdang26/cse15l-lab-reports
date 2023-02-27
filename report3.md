## grep options/flags   
## sources:  
[Link used for options -r -B](https://www.youtube.com/watch?v=VGgTmxXp7xQ)
<br>
[Link used for option -o](https://serverfault.com/questions/51014/dont-need-the-whole-line-just-the-match-from-regular-expression)
<br>
[Link used for option -E](https://www.cyberciti.biz/faq/grep-regular-expressions/)  
## grep -r  
```
$ grep -r "fountain of youth"
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:The whole cave park is a truly awesome sight, with holes 300 ft (91 m) deep and 200 ft (61 m) across, and caves thousands of feet deep, all surrounded by pristine forest. Some say that the fountain of youth is here, in the clean water filtering through the limestone from the surface. You don’t have to believe the legends, but taste the water anyway — it’s very sweet, and it can’t hurt to wish just a little.
```
```
$ grep -r "walking their dogs"
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt:And where have all the Anglos gone? Many of the upper-middle-class variety are holding out in Westmount. This bastion of the old Montréal élite of British origin became a prime target for the more violent members of the separatist Front de libération du Québec, who in the 1960s set off bombs in Westmount’s mailboxes. Those not put off by this can still be seen in tweeds and cavalry twill, walking their dogs around Summit Park, where the Belvedere affords a fine view of the city. Head for the tree-lined Summit Road, Summit Crescent, and Summit Circle and you’ll spot their ivy-covered mansions and grey-stone turreted châteaux half-concealed behind trees and shrubbery at the top of a grassy slope. The architecture here is a wonderful compendium of French Romanesque, German Gothic, and Italian Renaissance. Westmount Square gives you a sharp but not inelegant jolt back into the 20th century, with the black steel and glass office buildings of Mies van der Rohe.
```
This option is called "recursive" and searches through all the files in the current working directory and all sub-directories for the pattern. This can be helpful if you want to search through all the subdirectories relative to your current working directory; you can execute one grep command to search through it all, rather than using grep on each individual directory.

## grep -B  
```
$ grep -B 1 "clock" WhatToHongKong.txt
        Watches. The saying “Time is money” is quite literally true
        in Hong Kong: more is spent on watches and clocks here than on cameras
```  
```
$ grep -B 1 "fun" WhatToHongKong.txt
        Honeychurch Antiques at no. 29 for furniture and silver, Tai Sing
        Company at 122 for porcelain. For fun you can visit the Low Price Shop
--
        Hong Kong has many attractions that appeal to children of
        all ages. Hong Kong’s many beaches are especially fun for children.
```
This option is called "Behind" and shows a certain number of lines before the matched line, and accepts an argument that tells it how many lines to display. This is particularly useful when coding from the command line as it allows you look at the surrounding code to provide context that can explain what the matched line does.
  
## grep -w  
```
$ grep -w "line" WhatToHongKong.txt
        outlets in Causeway Bay. In addition, most top-line hotels have upscale
```
```
$ grep -w "side" WhatToHongKong.txt 
        be more expensive than smaller “family” shops tucked away in the side
```  
This option is called "whole word" as in it matches only with words that fully match, not just partially. (e.g. "John" matches with John but not Johnson) This can be used to weed out cases that may only partially match. 
  
## grep -E  
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
(The option -r is explained above, and the option -l replaces the output to just be the name of the file where the match was found) The option -E, regex option, allows for a regular expression (regex) to serve as the pattern to match with and can be useful to search according to a pattern rather than hardcoded strings. In the examples above, I used "|" in the regex to add multiple keywords to search matches for.
