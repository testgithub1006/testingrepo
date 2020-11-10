
  
node {
    stage('Preparation') { 
    
    choice1= new ChoiceParameterDefinition('AppEnvironment',['app-dev','app-stg','app-prd']as String[],'Choose Environment for Build')

     sh '''
     
     git ls -remote -h  https://github.com/testgithub1006/hello-world.git  | awk '{print $2}' | awk -F 'refs/heads/' {print $2}' > branches

       '''
       
       def file1 = new File("${pwd()}/branches")
       
       def branches = file1.readLines()
       
       
     choice2 = new ChoiceParameterDefinition('SelectedBranch', branches as String[] , 'Choose Branch')
     
     def userInput = input(id:'userInput' , message:"Let\'s Build Image ?",Parameters : [choice1,choice2])
     
     git branch: userInput['SelectedBranch'], url:'https://github.com/testgithub1006/hello-world.git',credentialsId:''
     
     echo "----- Branch name is ${userInput}"
     
     env.SELECTED_APP_ENV=userInput['AppEnvironment']
     
       sh "echo $SELECTED_APP_ENV"
       
      env.SELECTED_BRANCH=userInput['SelectedBranch']
       sh "echo $SELECTED_BRANCH"
         
    }

}
