## grep options/flags   
## sources:  
[Link used for options -r -B -w](https://www.youtube.com/watch?v=VGgTmxXp7xQ)
<br>
[Link used for option -o](https://serverfault.com/questions/51014/dont-need-the-whole-line-just-the-match-from-regular-expression)  
  
  
## grep -r  
```
$ grep -r "fountain of youth"
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:The whole cave park is a truly awesome sight, with holes 300 ft (91 m) deep and 200 ft (61 m) across, and caves thousands of feet deep, all surrounded by pristine forest. Some say that the fountain of youth is here, in the clean water filtering through the limestone from the surface. You don’t have to believe the legends, but taste the water anyway — it’s very sweet, and it can’t hurt to wish just a little.
```
```
$ grep -r "walking their dogs"
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt:And where have all the Anglos gone? Many of the upper-middle-class variety are holding out in Westmount. This bastion of the old Montréal élite of British origin became a prime target for the more violent members of the separatist Front de libération du Québec, who in the 1960s set off bombs in Westmount’s mailboxes. Those not put off by this can still be seen in tweeds and cavalry twill, walking their dogs around Summit Park, where the Belvedere affords a fine view of the city. Head for the tree-lined Summit Road, Summit Crescent, and Summit Circle and you’ll spot their ivy-covered mansions and grey-stone turreted châteaux half-concealed behind trees and shrubbery at the top of a grassy slope. The architecture here is a wonderful compendium of French Romanesque, German Gothic, and Italian Renaissance. Westmount Square gives you a sharp but not inelegant jolt back into the 20th century, with the black steel and glass office buildings of Mies van der Rohe.
```
This option is called "recursive" and searches through all the files in the current working directory and all sub-directories for the pattern.

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
This option is called "Behind" and shows a certain number of lines before the matched line, and accepts an argument that tells it how many lines to display.
  
## grep -w  
```
$ grep -w "line" WhatToHongKong.txt
        outlets in Causeway Bay. In addition, most top-line hotels have upscale
```
```
$ grep -w "side" WhatToHongKong.txt 
        be more expensive than smaller “family” shops tucked away in the side
```  
This option is called "whole word" as in it matches only with words that fully match, not just partially. (e.g. "John" matches with John but not Johnson)
  
## grep -o  
```
$ grep -o "The" WhatToHongKong.txt 
The
The
The
The
The
The
The
The
The
The
...
``` 
```
$ grep -o "where" WhatToHongKong.txt 
where
where
where
where
where
where
where
where
```
This option displays only the match in the printed message, rather than the whole line that contains the match.
