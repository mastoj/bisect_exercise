# Small git bisect exercise

The task is to find the commit that introduced a bug in the code. The bug is the text "this is a bug" in the file hello. Use the `git bisect` command to start a bisect process and locate the commit that introduced the bug. To make the testing easier you can use the script below (bash or write a similar using powershell) to test if the bug is present or not. The script will exit with 0 if the bug is present and 1 if the bug is not present. To use the script copy the code into a `test.sh` file and then you can run it with `git bisect run` after you have started the bisect process.

You can also do the whole 


```
#!/bin/bash

# if content of file hello is "hello world" exit with 0
# else exit with 1
if [ "$(cat hello)" = "this is a bug" ]; then
    echo "It is this is a bug"
    exit 1
else
    echo "Not this is a bug"
    exit 0
fi
```

Hints:
* `git bisect start`
* `git bisect bad HEAD`
* `git log --oneline`
* `git bisect good <ref>`
* `git bisect run ./test.sh`