node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
      sh 'whoami'
      sh 'pwd'
      git url: 'https://github.com/TTFHW/jenkins_pipeline_java_maven.git'

      // Get the maven tool.
      // ** NOTE: This 'M3' maven tool must be configured
      // **       in the global configuration.           
     //def mvnHome = tool 'M3'

      // Mark the code build 'stage'....
   stage 'Build'
      // Run the maven build
      //sh "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean package"
   
      sh 'echo Hello'
   
   
      // use the id of the globally configured maven instance
      def mvnTool = tool 'LocalMAVEN'

      // execute maven
      sh "${mvnTool}/bin/mvn -v"
      sh "${mvnTool}/bin/mvn clean install"
      sh "${mvnTool}/bin/mvn -Dmaven.test.failure.ignore clean package"
      step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml']
   
      // Run the maven build
      //sh "mvn clean install"
  
    ///  sh 'mvn -v'
      ///sh "mvn -Dmaven.test.failure.ignore clean package"
     /// step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}
