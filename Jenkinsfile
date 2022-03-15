import groovy.json.JsonSlurperClassic
def jsonParse(def json) {
    new groovy.json.JsonSlurperClassic().parseText(json)
}
pipeline {
    agent any
    stages {
        stage("Paso 1: Testear JMeter"){
            steps {
                script {
                sh "echo 'Ejecutar prueba de performance!'"
                // Run Maven on a Unix agent.
                sh "mvn verify -Pperformance"
                }
            }
        }    
    }
    post {
        always {
            sh "echo 'fase always executed post'"
        }
        success {
            sh "echo 'fase success'"
        }
        failure {
            sh "echo 'fase failure'"
        }
    }
}


