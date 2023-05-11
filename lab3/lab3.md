# Lab 3 - More about Less 💸

## Interesting Command Line Arguments for `less` 📚 ##
Note to grader I forgot to read the instructions and now have 2 of my own examples alongside the 2 actual required examples.
---
### Line Number `-N` Poetry 🔢###

- `-N` adds line numbers to each line so you can keep track of where you are in your file!
    - This can be very helpful for you impromptu poetry sessions on your remote server
        - `less -N hamlet.txt`
        ``` 
        1 To be, or not to be, that is the question:
        2 Whether 'tis nobler in the mind to suffer
        3 The slings and arrows of outrageous fortune,
        4 Or to take arms against a sea of troubles
        5 And by opposing end them. To die-to sleep,
        6 No more; and by a sleep to say we end
        7 The heart-ache and the thousand natural shocks
        8 That flesh is heir to: 'tis a consummation
        9 Devoutly to be wish'd. To die, to sleep;
        10 To sleep, perchance to dream-ay, there's the rub:
        11 For in that sleep of death what dreams may come,
        12 When we have shuffled off this mortal coil...
        hamlet.txt (END)
        ```
    - You could also use this to debug code files. This allows you to find an error on a specific line number. 
        - `less -N Hello.java`
        ```
        1 class Hello {
        2         public static void main(String[] args) {
        3                 System.out.println("Hello")
        4         }
        5 }
        Hello.java (END)
        ```
        - No semicolon on line 3!!! **(╯‵□′)╯︵┻━┻**
- Source: [linuxize.com](https://linuxize.com/post/less-command-in-linux/)

---
### Search Pattern `/` Sleuthing 🔎###

- `/` can help you find occurences of words while you are "lessing" a document! (Using `-p<pattern>` also works!)
    - You can use this to find repeated words in text files!
        - `less hamlet.txt` then while in the less screen `/sleep`
        - <img src="img/high-hamlet.png" height="300" width="500">
        - I had to paste an image because highlights cannot appear on code blocks :/
    - You can also make your debuging life easier by finding specific errors.
        - `javac Hello.java 2> error.txt || less error.txt` then while in less `/error`
        - <img src="img/java-error.png" height="100" width="400">
        - Note: I used `||` because the first line exits with an error code, if this code succeeded I would've used `&&`. I would also change `2>` to `>`. Anyways, SEMICOLONS!!! **╰（‵□′）╯**
- Source: [phoenixnap.com](https://phoenixnap.com/kb/less-command-in-linux)

---
### Real-time `+F` Chicanery ⏱###

- `+F` can help you see your file update in real-time!
    - This can be used to keep an up to date log file to measure changes in real time, git!
        - `less +F updates.txt` is empty until I start making changes
        ```
        Waiting for data... (interrupt to abort)
        ```
        - When I make my first few changes the less screen will update!
        ```
        Ver 0.1
        Added a hello world program!

        Ver 0.2
        Added a semicolon to make hello world actually run...
        Waiting for data... (interrupt to abort)
        ```
    - I use this one to check my stock options while programming on a terminal 😎
        - `less +F stocks.txt` will show
        ```
        Apple Inc. $173.60
        Microsoft. $312.31
        Amazon. $110.19
        Waiting for data... (interrupt to abort)
        ```
        - But if I buy stocks in Circuit City my stocks.txt will update automatically!
        ```
        Apple Inc. $173.60
        Microsoft. $312.31
        Amazon. $110.19
        Circuit City. $0.01
        Waiting for data... (interrupt to abort)
        ```
        - Note it may take a second line input for the first line input to be updated. Also note that this cannot edit previous lines.
- Source: (ChatGPT)[https://chat.openai.com/]

---
### Editing Files `v` Final Boss 😈 ###

- Although less is read-only, pressing v while in less opens vim.
    - Now I can fix that pesky semicolon in my hello program on a remote computer
        - `less Hello.java` then press `v`
        ```
        class Hello {
            public static void main(String[] args) {
                System.out.println("Hello");
            }
        }
        Hello.java [dos] (20:37 10/05/2023)
        "Hello.java" [noeol][dos] 5L, 94B
        ```
        - Note: omitted `~` which are used to fill up the rest of the screen
        - Added the semicolon!!!
    - I can also update my stock portfolio with the proper values now
        - `less stocks.txt` then press `v`
        ```
        Apple Inc. $173.60
        Microsoft. $312.31
        Amazon. $110.19
        Circuit City. <BANKRUPT>
        Dogecoin. $0.08
        stocks.txt [dos] (21:43 10/0 2023)
        "stocks.txt" [dos] 5L, 100B
        ```
- Learn more [linuxhandbook.com](https://linuxhandbook.com/less-command/)


    

