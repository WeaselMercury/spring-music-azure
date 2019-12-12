#!/usr/bin/env groovy
pipeline {
    agent any
        options {
        skipStagesAfterUnstable()
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                //echo 'le Build, seconde édition'
                sh 'make'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                //echo 'le Test, seconde édition'
                sh 'make check'
                junit 'reports/**/*.xml'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                //echo 'le Deploy, seconde édition'
                sh 'make publish'
            }
        }
    }
}
