# C# Code Challenge

* Write a command line program to run the `ping` utility, collect, process, and display the results.
* When run the program should present the user with a prompt. This prompt should accept `start <target>`, `stop <target>`, and `quit` commands.
* Once a `start` command is issued for a `target` the program should execute the system `ping` utility repeatedly every 5 seconds for this target.
    * `<target>` can be an IP address or hostname.
    * Each execution only needs to send a single request, limit this with the `-n` argument.
* Multiple `start` commands can be issued before a `stop`
* The `stop <target>` command should stop the execution of the ping command for the specified `<target>` only and display any unprocessed results collected up to that point.
* The `quit` command should exit the program in an orderly fashion.
* The output of each execution of `ping` should be parsed and stored.
* The collected output should be processed every 1 minute and a mininum/maximum/average for the round trip time should be calculated for each 1 minute period.
  * The individual samples should be taken from the `time` value in the ping output.
* These aggregate 1 minute results should be printed continuously as they are generated.

## Suggested Output

```
$ dotnet run
> start 8.8.8.8
> 
2023-08-01 16:00:00 8.8.8.8 MIN 4.091ms MAX 5.838ms AVG 4.614ms
2023-08-01 16:01:00 8.8.8.8 MIN 3.526ms MAX 7.867ms AVG 6.0175ms
> stop 8.8.8.8
> quit
$ 
```

## General Approach and Assumptions

* This program should be written in C# using a recent version of .NET (5.0 or greater)
* The program should be built with the .NET SDK and use standard tooling and no thirdparty dependencies other than the ping utility.
* Ping is located at `/usr/bin/ping` on typical Linux distributions, `/sbin/ping` on macOS, and at `C:\Windows\System32\ping.exe` on Windows.
* You only need to support a single operating system, whichever you find convenient but please specify in comments, program output, or a README which you support.

## Criteria

* You will not be evaluated on the UI design, but rather your ability to separate the concerns of the UI from the rest of code and to correctly handle any ansynchronous interaction. Given the nature of the problem it is likely that output of result data might interfere with user input echo.
* Consistency of coding style.
* Correct error handling.
* Appropriate unit tests.
* Your solution must build and run cleanly by executing `dotnet run` from a clean clone of your repository. 
    * Depending on your project structure it is ok to require a `cd` into a sub directory.
* Your solution tests must build and run by executing `dotnet test` from a clean clone of your repository.
    * Depending on your project structure it is ok to require a `cd` into a sub directory but it should not be necessary for the tests.

## How to Submit Your Work

1. Fork this repository on GitHub.
2. Commit your solution preferably in multiple commits demonstrating your development process.
3. When you're finished, send us the URL of your public repository.