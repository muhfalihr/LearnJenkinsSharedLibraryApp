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
        stage('List Parameter Implementaion') {
            steps {
                script {
                    def fileNames = ["falih", "yusep", "romy"]
                    write_display(this, fileNames)
                }
            }
        }
        stage('Map Parameter Implementation') {
            steps {
                script {
                    def personalData = [
                        [fullname: "Muhamad Falih Romadhoni", age: "18 yo", birthdate: "10-11-05"],
                        [fullname: "Romy Saputra Sihananda", age: "18 yo", birthdate: "22-12-05"]
                    ]
                    personal_data(this, personalData)
                }
            }
        }
        stage('Library Resource') {
            steps {
                script {
                    def config = libraryResource("config/build.json")
                    def jsonObject = jsonToMap(config)
                    def type = jsonObject.getClass().getSimpleName()
                    
                    echo "jsonObject = ${jsonObject}"
                    echo "Data Type from jsonObject is ${type}"
                }
            }
        }
    }
}