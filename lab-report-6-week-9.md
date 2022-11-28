AutoGrader Tracing (By Dean Bisco) 

```
CPATH=".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"

rm -rf student-submission
git clone $1 student-submission

cp TestListExamples.java student-submission
cp lib/hamcrest-core-1.3.jar student-submission
cp lib/junit-4.13.2.jar student-submission

cd student-submission

if [ -f "ListExamples.java" ]
then
        echo "ListExamples.java found!"
else
        echo "File Not Found!"
        echo "Grade: 0/2; 0%"
        exit
fi

javac ListExamples.java 2> err.txt > out.txt
if [ $? -ne 0 ]
then
        echo "Compiler Error!"
        echo "Grade: 0/2; 0%"
        exit
fi

javac -cp $CPATH TestListExamples.java 2> err.txt> out.txt
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples 2> err2.txt > out.txt

if [ $? -ne 0 ]
then
        echo "You passed all 2 Tests!"
        echo "Grade: 2/2; 100%"
        exit
else
        grep -c "Error(s) Found:" err.txt > result.txt
        cat result.txt
        echo "tests failed. There were a total of 2."
        exit
fi
```

The script was run on the following repositories: corrected, compiler-error, and filename


![](https://aquazap.github.io/cse15l-lab-reports/lab-report-6-screenshot-1.png)

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-6-screenshot-2.png)

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-6-screenshot-3.png)


Tracing grade.sh on a repository with a missing file (Screenshot 3): 

Line 3: Deletes the directory student-submission if it has already been created. Return code is 0.

Line 4: Starts the cloning process of the repository into the directory student-submission. Return code is 0.

Lines 6-8: Copies the the files necessary to run JUnit Tests and the file TestListExamples.java, which does not exist in this context. Return code for all 3 lines is 0.

Line 10: Changes directories from list-examples-grader to student-submission. Return code is 0.

Line 12: Checks if file "ListExamples.java" is in the directory. In this case, it does not exist, therefore this line does not fully run. Return code is nonzero.

Lines 13 + 14: Would echo that the File was found, but in this case where the file does not exist, then these lines do not run at all and are thus skipped.

Line 15: The start of an else statement. Return code is 0.

Lines 16 + 17: Echos that the file is not found, and gives a grade of 0/2 or 0% to the submission because of the missing file. Return code for both lines is 0.

Line 18: Exits the code entirely. Because it successfully exits after the two echo statements, the return code is nonzero.

Lines 19-end: These lines are all skipped because the code was exited beforehand.


