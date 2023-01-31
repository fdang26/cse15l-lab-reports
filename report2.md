## Part 1
![](/docs/assets/stringSever.png)
![](/docs/assets/heyther.png)
This calls the handleRequest method within Handler and provides the url as an arguement. The instance variables of Handler are initialized to an empty string for message and 0 for messageCount. The message variable is updated and appends the part of the query string after the equals sign into the message string. messageCount is also updated is incremented by one.

![](/docs/assets/howsitgoin.png)
This calls the handleRequest method again and also provides the url as an argument. The instance variables are updated: message is updated with a new line as well as the part of the query after the equals sign being appended, and message count is incremented. 

## Part 2
Choose one of the bugs from lab 3.

```
@Test
  public void testAverageWithoutLowest(){
    double[] input1 = { 1.0, 1.0, 2.0, 4.0, 5.0};
    assertEquals(3.0, ArrayExamples.averageWithoutLowest(input1), 0.0);
  }
```
```
@Test
  public void TestAverageWithoutLowest(){
    double[] input1 = { 1.0, 4.0, 5.0 };
    assertEquals(4.5, ArrayExamples.averageWithoutLowest(input1), 0.0);
  }
```
![1 Failed Test](/docs/assets/tests.png)

**BEFORE**
```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```
**AFTER**
```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
       sum += num;
    }
    int average = (sum - lowest) / (arr.length - 1);
    return average;
  }
```
This fixes the issue because instead of skipping over all the instances of the lowest variable, which might subtract too many values, it removes the lowest value from the average just once by subtracting lowest once from the sum of the double array.

## Part 3
These recent labs have taught me how to use JUnit testing to creater unit testers for my code, more specifically the assertEquals method within the JUnit library. While I will still use System.out.println statements within my code to test it, Junit testing serves as a structured method of ensuring my code is matching my expectations.


