# Lab 5 - Edstem Rubber Ducky Debugging 🦆
1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is. 
![Image](img/P1.png)
![Image](img/P2.png)

2. A response from a TA asking a leading question or suggesting a command to try.
![Image](img/A1.png)

3. Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.
    - Changed the implemetation of the filter method to not include nulls in lists by opting to use ArrayLists instead of arrays for dynamic sizing.
    - ![Image](img/after.png)
    - ![Image](img/fix.png)

4. At the end, all the information needed about the setup including:
    - The file & directory structure needed
        - Project/
            - lib/
                - hamcrest-core-1.3.jar
                - junit-4.13.2.jar
            - grade.sh
            - ListExamples.java
            - TestListExamples.java
                
    - The contents of each file before fixing the bug
        - ![Image](img/before.png)
    - The full command line (or lines) you ran to trigger the bug
        - `bash grade.sh ListExamples.java`
    - A description of what to edit to fix the bug
        - Go to `ListExamples.java`
        - Change line 14 to `List<String> result = new ArrayList<>();`
        - Change line 17 to `result.add(list.get(i));`
        - Delete line 20
        - Run `bash grade.sh ListExamples.java`
        - Profit!!!