pipeline {
    agent any
     stages {
         stage('One') {
             steps {
                 sh label: '', script: '''echo Hello World!
                 echo Bye Bye!'''
             }
         }
         stage('Two') {
             steps {
                 sh label: '', script: '''echo -e "\e[31mHello World!\e[0m"
                 echo -e "\e[41mBye Bye!\e[0m"'''
             }
         }
     }
}
