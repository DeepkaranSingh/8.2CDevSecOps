stage('SonarCloud Analysis') {
    steps {
        withCredentials([string(credentialsId: 'SONAR_TOKEN', variable: 'SONAR_TOKEN')]) {
            sh '''
                # Download SonarScanner CLI
                curl -sSLo sonar-scanner.zip https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.7.0.2747.zip
                
                # Unzip the scanner
                unzip sonar-scanner.zip
                
                # Add scanner to PATH
                export PATH=$PATH:$PWD/sonar-scanner-4.7.0.2747/bin
                
                # Run scanner with token
                sonar-scanner -Dsonar.login=$SONAR_TOKEN
            '''
        }
    }
}
