pipeline{
    agent any
    stages{
        stage('Build if branch master'){
            when { 
                    GIT_BRANCH = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                    return GIT_BRANCH == 'origin/master'
                     } 
            steps {
                echo "Building from Master Branch"
            }
        }

        stage('Build if branch not master'){
            when { 
                    GIT_BRANCH = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                    return !(GIT_BRANCH == 'origin/master')
                     } 
            steps {
                echo "Building from ${GIT_BRANCH} Branch"
            }
        }

      
        }
}
