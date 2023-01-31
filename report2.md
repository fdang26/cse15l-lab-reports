![](/docs/assets/stringSever.png)
![](/docs/assets/heyther.png)
This calls the handleRequest method within Handler and provides the url as an arguement. The instance variables of Handler are initialized to an empty string for message and 0 for messageCount. The message variable is updated and appends the query string into the message string. messageCount is also updated is incremented by one.

![](/docs/assets/howsitgoin.png)
This calls the handleRequest method again and also provides the url as an argument. The instance variables are updated: message is updated with a new line as well as the part of the query after the equals sign being appended, and message count is incremented. 

Part 2
Choose one of the bugs from lab 3.

Provide:

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.

Part 3
In a couple of sentences, describe something you learned from lab in week 2 or 3 that you didn’t know before.



