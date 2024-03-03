pipeline{ 
    agent any 
    parameters{ 
        string(name:'TOOL', defaultValue: 'Mr Jenkins', description: 'Who Should i Say hello to?') 
        text(name:'DESC', defaultValue:'', description: 'Enter some information about the persion') 
        booleanParam(name: 'SONOAR', defaultValue: true, description: 'Toggle this Value') 
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a passwod') 
        choice(name:'STAGE',choices: "Build\ntest\nDeploy\n", description: 'delimiters within stage') 
        file(name:"FILE", description: "Choose File") 
    } 
    stages{ 
        stage("Tool"){ 
            steps{ 
                echo "$TOOL or ${params.TOOL} both are same" 
            } 
        } 
        stage("Choice"){ 
            steps{ 
                echo "My choice is $STAGE" 
            } 
        } 
        stage("SONAR"){ 
            steps{ 
                script{ 
                    if(params.SONAR){ 
                    echo "Sonar steps will execute" 
                    } 
                } 
            } 
        } 
        stage("Execuing Stages") { 
            steps { 
                script { 
                    if(params.STAGE=='Build'){ 
                        echo "The code is execuing in Build Environment" 
                    } 
                    else if(params.STAGE=='Test'){ 
                        echo "The code is execuing in Test Environment" 
                    } 
                    else { 
                        echo "The code is execuing in Deploy Environment" 
                    } 
                } 
            } 
        } 
    } 
} 