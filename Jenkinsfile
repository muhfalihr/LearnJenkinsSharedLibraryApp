@Library("LearnJenkinsSharedLibrary@master") _

import muhfalihr.jenkins.Output;

pipeline {
    agent any
    stages {
        stage('Hello Groovy') {
            steps {
                script {
                    Output.hello(this, "Groovy")
                }
            }
        }
        stage('Hello World') {
            steps {
                script {
                    hello.world()
                }
            }
        }
        stage('Global Variable') {
            steps {
                script {
                    echo("Hallo, Saya {author.name()}")
                    echo("Saya dari perusahaan {author.company_name()}")
                }
            }
        }
    }
}