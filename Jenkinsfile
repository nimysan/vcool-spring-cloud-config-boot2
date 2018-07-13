pipeline {
    agent any

    stages {
        stage ('package Stage') {

            steps {
                withMaven(maven : 'm3') {
                    sh 'mvn clean package'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'm3') {
                    sh 'mvn test'
                }
            }
        }


        stage ('build docker image Stage') {
            steps {
                withMaven(maven : 'm3') {
                    sh 'mvn dockerfile:build'
                }
            }
        }
        
    }
}
