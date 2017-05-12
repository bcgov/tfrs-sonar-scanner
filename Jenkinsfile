node('maven') {
   stage('checkout tfrs-sample-sonar')
   git url: 'https://github.com/bcgov/tfrs-sonar-scanner.git'
   
   stage('list root dir')
   sh 'ls -l -srt'

   stage('change to working dir')
   dir('tfrs-sample-project'){
       stage('list dir')
       sh 'ls -l -srt'
   
       stage('execute sonar')
       sh './gradlew sonarqube -Dsonar.host.url=http://sonarqube-mem-tfrs-tools.pathfinder.gov.bc.ca -Dsonar.verbose=true --stacktrace'
   }
}
