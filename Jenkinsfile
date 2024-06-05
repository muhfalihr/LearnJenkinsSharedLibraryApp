@Library("LearnJenkinsSharedLibrary@master") _

import muhfalihr.jenkins.Output;

pipeline {
    agent {
        node {
            label 'node172'
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
            steps {
                script {
                    def value = """
Nama : Muhammad Falih Romadhoni
Umur : 18 Tahun
Domisili : Parigi Baru, Pondok Aren, Tangerang Selatan
"""
                    writeFile(file: "datadiri.txt", text: value)
                    def size = file_size(this, "datadiri.txt")
                    echo "File Size : ${size}"
                }
            }
        }
    }
}