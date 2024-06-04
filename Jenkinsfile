@Library("LearnJenkinsSharedLibrary@master") _

import muhfalihr.jenkins.Output;

pipeline {
    environment {
        PATH = '/home/datadiri.txt'
    }
    agent {
        node {
            label 'node1'
        }
    }
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
                    echo "Hallo, Saya ${author.name()}"
                    echo "Saya dari perusahaan ${author.company_name()}"
                }
            }
        }
        stage('Default Function') {
            steps {
                script {
                    echo "Username Telegram Saya : @${author()}"
                }
            }
        }
        stage('Parameter implementation') {
            steps [
                script {
                    def value = """
Nama : Muhammad Falih Romadhoni
Umur : 18 Tahun
Domisili : Parigi Baru, Pondok Aren, Tangerang Selatan
"""
                    writeFile(file: "${env.PATH}", text: value)
                    cat(this, "${env.PATH}")
                }
            ]
        }
    }
}