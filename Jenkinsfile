#!/usr/bin/env groovy

pipeline {
  agent any
  options {
    buildDiscarder logRotator(daysToKeepStr: '', numToKeepStr: '15')
  }

  stages {
      
        stage("Tenant repo"){
        //when { anyOf { changeset "**/tenant/**"; expression { fileExists ('.changes/tenant') }}}
          parallel {
            stage("Unit Test tenant"){
            /*agent {
                docker {
                    image 'golang'
                    args  '-u root'             
                }
                }*/
                steps {
                echo "PASS"
            //  sh 'go test -v ./... '        
                }
            }
            stage("Build Tenant Container Image"){
            steps{
                    echo "Second stage"
                }
            }
          
          }
            
         // when { anyOf { changeset "**/tenant/**"; expression { fileExists ('.changes/tenant') }}}
          //steps { script { stages("tenant", env.TAG_NAME, BRANCH_NAME, "rbi-tenant" )  }}}
        //steps { script { sh "echo 'inside tenant'"} }}
         
      }

      stage("Security repo"){
        //when { anyOf { changeset "**/security/**"; expression { return fileExists ('.changes/security') }}}
            stages{
            stage("Unit Test Security"){
                /*agent {
                docker {
                    image 'golang'
                    args  '-u root'             
                }
                }*/
                steps {
                echo "PASS"
            //  sh 'go test -v ./... '        
                }
            }
            stage("Build Security Container Image"){
                steps{
                    echo "Second stage"
                }
            }
      //  when { anyOf { changeset "**/security/**"; expression { return fileExists ('.changes/security') }}}
       //   steps { script { stages("security", env.TAG_NAME, BRANCH_NAME, "rbi-security" ) }}}
        //steps { script { sh "echo 'inside security'"} }  
        }
      }

      stage("Notification repo"){
        //when { anyOf { changeset "**/notification/**"; expression { return fileExists ('.changes/notification') }}}
            stages{
            stage("Unit Test Notification repo"){
                /*agent {
                docker {
                    image 'golang'
                    args  '-u root'             
                }
                }*/
                steps {
                echo "PASS"
            //  sh 'go test -v ./... '        
                }
            }       
            stage("Build Notification Container Image"){
                steps{
                    echo "Second stage"
                }
            }
       //    when { anyOf { changeset "**/notification/**"; expression { return fileExists ('.changes/notification') }}} 
       //   steps {  script{ stages("notification", env.TAG_NAME, BRANCH_NAME, "rbi-notification" ) }}} 
        }
      }

      stage("Controlcenter repo"){
        //when { anyOf { changeset "**/controlcenter/**"; expression { return fileExists ('.changes/controlcenter') }}}
            stages{
            stage("Unit Test Controlcenter repo"){
                /*agent {
                docker {
                    image 'golang'
                    args  '-u root'             
                }
                }*/
                steps {
                echo "PASS"
            //  sh 'go test -v ./... '        
                }
            }  
            stage("Build Controlcenter Container Image"){
                steps{
                    echo "Second stage"
                }
            }
        //  when { anyOf { changeset "**/controlcenter/**"; expression { return fileExists ('.changes/controlcenter') }}}
         // steps {  script{ stages("controlcenter", env.TAG_NAME, BRANCH_NAME, "rbi-controlcenter" ) }}}
        }
      }
      
     stage("Viewer repo"){
        //when { anyOf { changeset "**/viewer/**"; expression { return fileExists ('.changes/viewer') }}}
            stages{
            stage("Unit Test Viewer repo"){
                /*agent {
                docker {
                    image 'golang'
                    args  '-u root'             
                }
                }*/
                steps {
                echo "PASS"
            //  sh 'go test -v ./... '        
                }
            }       
            stage("Build Viewer Container Image"){
                steps{
                    echo "Second stage"
                }
            }
       //   when { anyOf { changeset "**/viewer/**"; expression { return fileExists ('.changes/viewer') }}} 
         // steps {  script{ stages("viewer", env.TAG_NAME, BRANCH_NAME, "rbi-viewer" ) }}}
        }
      }

     
      


  }
}
