pipeline {
    agent any   
    stages {
        stage('Fetch')
        {
            steps
            {
                git url : "https://github.com/Shilpa40/Hello-World.git"
            }
        }
        stage('Build')
        {
            steps
            {
               bat "npm install"
               bat "npm run build"
            }
        }
        stage('Sonar Analysis')
        {
            steps
            {
                withSonarQubeEnv("SonarQube")
                {
                    bat "mvn sonar:sonar"
                }  
            }
        }
    }
}
