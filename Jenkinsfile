pipeline {
  agent any
  stages {
    stage('compilar') {
      steps {
        withMaven(jdk: 'JDK', maven: 'MAVEN', mavenSettingsFilePath: 'C:\\Users\\alumno.33\\Desktop\\Jenkins - Alumno\\maven\\conf\\settings.xml', globalMavenSettingsFilePath: 'C:\\Users\\alumno.33\\Desktop\\Jenkins - Alumno\\maven\\conf\\settings.xml') {
          bat 'mvn clean install -DskipTests'
        }

      }
    }
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat7(credentialsId: '31dee02a-5d61-4182-8dfc-8ce677fc9cd6', path: '', url:    'http://localhost:8082')], contextPath: 'WebPrueba', war: 'target/*.war'
      }
   }
  }
}
