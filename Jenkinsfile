pipeline {
        agent {label 'Slave'}

    stages {

        stage ("Getting Souce Code From Git") {
            steps {
                git branch: 'develop', url: 'https://github.com/Sai-Test1208/Sai-Test2408-Repo2.git'
            }
        }

        stage ("SonarQube analysis") {
            steps {
        sonarqube_server_name: "SonarScanner_Server"
        sonar_runnner_tools_name: "sonarscanner"
        full_scan: "yes"
         sonar_conf:
//             sonar.projectKey: GITMVN1
//             sonar.projectName: github_maven1
//             sonar.projectVersion: 1.0.0
//             sonar.sources: src
//             sonar.language: java
//             sonar.java.binaries: target
//             sonar.java.libraries: ${env.HOME}/.m2/repository/**/**/**/**/*.jar
//             sonar.exclusions: ''
//             sonar.sourceEncoding: UTF-8
// //             sonar.web.host: sonarqube.broadcom.net
//             sonar.web.port: 443
//             sonar.login: SonarScanner_Server
//             # Excluded as we do not have a common domain module, some domains are duplicated across modules and this causes a false positive
// #             sonar.exclusions: '**/domain/*.java'
//                 }
            }
	}
			
        stage ("Compiling The Source Code") {
            steps {
                sh 'mvn compile'
            }
        }

        stage ("Testing The Source Code") {
            steps {
                sh 'mvn test'
            }
        }

        stage ("Generating Artifact") {
            steps {
                sh 'mvn package'
            }
	}
	    
// 	 stage ("Building docker image and launching container") {
//             steps {
// 		 sshPublisher(publishers: [sshPublisherDesc(configName: 'Docker-host', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'sudo docker build -t saitomcat:1.0 /dockerfiles/dockerfile; sudo docker login; sudo docker tag saitomcat:1.0 saikirangude/dockerfiles:1.0; sudo docker push saikirangude/dockerfiles:1.0; sudo docker run -d -p 8080:8080 saikirangude/dockerfiles:1.0 --name=tomcat-container', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '/jenkins_home/workspace/Tasks/Tasks-1/Jenkins_Pipeline_2/target/', sourceFiles: '/jenkins_home/workspace/Tasks/Tasks-1/Jenkins_Pipeline_2/target/trucks.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
// 	    }
// 	}
    }      
}
