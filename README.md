# phonenumbers-qa
This repository aims for Quality Assurance Plivo's phone numbers related features and tests their quality in an automated way. </br>
Python(2.7) and robot framework are used in this automation framework. </br>
This automation code has beed tested on python 2.7 </br>

# Getting Started
These instructions will let you set up testing environment on your local machine for automation. </br>
## Setting up
Refer to the [requirements.txt](https://github.com/plivo/phonenumbers-qa/blob/master/requirements.txt) file.
Requirements could be installed as :
```
$ pip install -r /path/to/requirements.txt
or
 pip install --user -r requirements.txt
```
## Robot Framework
QuickStart guide to robot framework can be found [here](https://github.com/robotframework/QuickStartGuide/blob/master/QuickStart.rst). </br>
Further, [Robot Framework Documentation](http://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html)
# Running Tests
The robot test cases are organised accordingly into directories. Please refer to the repository for the directory hierarchy.
Every directory represents module/feature under test. Test cases are put into test suites with .robot extension.
keywords or Libraries could be found under Library directory and module named directory.

Tests can be run in the following ways : </br>
### Invoking testcase file.
For example, To test a basic outbound call, automated in file MakeCall.robot
Either full path of file name could be provided or ** could be used instead of single directory like :
If running from parent directory of the project,
```
$ robot phonenumbers-qa/Functional/PlivoAPI/tests/Number.robot
```
```
$ robot **/**/**/Number.robot
```
The above command will run all cases in MakeCall.robot and put the log and results in the same directory(ie from where the command is invoked) </br>
To run with results to be put in separate dir, use -d option(as mentioned in 'robot --help' :
```
$ robot -d /local/results **/**/**/Number.robot
```
### Invoking tag names
By calling tags tests could be run as : 
```
$ robot --include <tag_name> /path/to/tests/<test_suite.robot>
```
Above run will run all the tags matching in the given specific robot file name.

```
$ robot --include <tag_name> **/**/**/**.robot
```
Above run will run all the tags matching in all robot files in the specified directory.

### Combining tags
 Combines test cases containing tag_name_1 AND tag_name_2, </br>
```
$ robot --include <tag_name_1>AND<tag_name_1> /path/to/tests/<test_suite.robot>
```
Similarly, 'OR', 'NOT' can also be used to combine tag names.
### Run all the test suites
To run all the robot files from a /tests directory using a single command, </br>
```
$ robot /path/to/tests/**.robot
```
For example, To run all the test suites in /Call directory,
```
$ robot phonenumbers-qa/Functional/PlivoAPI/tests/**.robot
```
### Using desired log level
The default log level is INFO. List of available log levels, INFO, WARN, DEBUG, ERROR, TRACE. </br>
```
$ robot --loglevel <log_level> /path/to/tests/<test_suite.robot>
```
### Post processing test results
To change the path of the generated output, log and report files,
```
$ robot --output /path/to/output.xml --log /path/to/log.html --report /path/to/report.html /path/to/tests/<test_suite.robot>
```

Basic ones are mentioned above.
For more options please read robot --help or documentation as given above. </br>

# Results/Logs : </br>
As per used output dir, results and logs are placed in there. </br>
Three files get generated after run: </br>
1. log.html : All the testcases run status is placed in this dir.Results could be figured by test cases color and by expanding the testcases of a scenario. </br>
2. report.html : This is used to report statistics related to testcase(s) run. </br>
3. output.xml : This is used for custom reporting/parsing such as in CI. </br>

