pipeline {
    agent any
    parameters { 
        choice(name:'VERSION' choices: ['1.1.0', '1.2.0','1.3.0'], description: '')
        booleanparam(name: 'executeTests', defaultvalue: true, description:'')
    }
    stages {
        stages("init") {
            script {
                gv = load "script.groovy"
            }
        }
    }
        stage('Build') {
            steps {
                echo 'Building the application'
            }
        }
        stage('Test') {
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                echo 'Testing application'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application'
                echo "deploying version ${VERSION}"
            }
        }
    }
}
