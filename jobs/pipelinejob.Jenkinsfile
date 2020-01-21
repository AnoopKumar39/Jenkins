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
                 sh label: '', script: '''echo -e "\e31mHello World!\e0m"
                 echo -e "\e41mBye Bye!\e0m"'''
             }
         }
     }
}
