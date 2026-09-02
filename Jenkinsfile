pipeline {
    agent any
    tools { jdk 'jdk21'; maven 'maven3' }
    stages {
        stage('Build') { steps { bat 'cd /d E:\\project-GBGHMVNNEXSONJEN && mvn clean package -DskipTests' } }
        stage('Deploy to Nexus') { steps { bat 'cd /d E:\\project-GBGHMVNNEXSONJEN && mvn deploy -DskipTests' } }
        stage('SonarQube') { steps { bat 'cd /d E:\\project-GBGHMVNNEXSONJEN && mvn org.sonarsource.scanner.maven:sonar-maven-plugin:5.0.0.4389:sonar -Dsonar.projectKey=project-GBGHMVNNEXSONJEN -Dsonar.host.url=http://localhost:9000 -Dsonar.token=sqp_YOUR_TOKEN -Dsonar.scanner.skipJreProvisioning=true' } }
    }
}
