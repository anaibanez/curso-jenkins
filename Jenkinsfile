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
       stage('test') {
      steps {
        withMaven(globalMavenSettingsFilePath: 'C:\\Users\\alumno.33\\Desktop\\Jenkins - Alumno\\maven\\conf', mavenSettingsFilePath: 'C:\\Users\\alumno.33\\Desktop\\Jenkins - Alumno\\maven\\conf', jdk: 'JDK', maven: 'MAVEN') {
          bat 'mvn test cobertura:cobertura -Dmaven.test.failure.ignore=true'
        }
      }
       }
  
  stage('Cobertura') {
   steps {
    cobertura autoUpdateHealth: false, autoUpdateStability: false, coberturaReportFile: 'target\\\\surefire-reports\\\\cobertura\\\\coverage.xml ', conditionalCoverageTargets: '70, 0, 0', failUnhealthy: false, failUnstable: false, lineCoverageTargets: '80, 0, 0', maxNumberOfBuilds: 0, methodCoverageTargets: '80, 0, 0', onlyStable: false, sourceEncoding: 'ASCII', zoomCoverageChart: false
  }
     }
}
  }
