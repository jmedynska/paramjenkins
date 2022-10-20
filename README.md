# paramjenkins

This Repo is a short tutorial for playing with parameters in Jenkins pipelines. 
Each folder consists a simple parametrized Jenkinsfile. 


# Folders
This Repo consists of 4 folders:
1. boolean 
2. choice
3. userInput
4. combined

## Creating job in Jenkins
If you want to run these pipelines in your environment go to your Jenkins dashboard, select **New item** , enter the name of your new job, choose **pipeline** and click OK button. Next, under **General** section select **GitHub Project** and provide correct repository URL. Go to **Pipeline** section and change definition to *Pipeline script from SCM*, set **SCM** to *Git* and again paste correct repository URL. Define the branch name and script path. Script path will vary depending on folder you want to use, ex. you want to play with choice parameter, than you should write *choice/Jenkinsfile* in the **Script Path** field. After saving the configuration build your job. 

## Boolean parameter

In **boolean** folder you will find one-stage Jenkins pipeline with boolean parameter named *myBoolean*.  By default it's set to false.  

## Choice parameter

In **choice** folder you will find one-stage Jenkins pipeline with choice parameter named *deployEnv*.  It doesn't have default value field, but it would take the first value from the array if user won't choose any option.  

## userInput parameter

In **userInput** folder you will find one-stage Jenkins pipeline with string parameter named *deployEnv*.  By default it's set to "Test". This parameter allows user to write any word as an input. It can be replaced by text parameter. The main difference is that text parameter can store multiline text.  

## All three parameters in one file

In **combined** folder you will find two-stage Jenkins pipeline with if statement and all three parameters described above.  Parameters are called as follows:
boolean = "myBoolean"
choice = "choiceParam"
string = "stringParam"
User is asked to provide name as stringParam, then depending on a boolean value the code will print out message "Fantastic!" if myBoolean is set to true or "Maybe you need to practice a little more." if myBoolean is set to false. User has 5 options to choose from in choiceParam. 
