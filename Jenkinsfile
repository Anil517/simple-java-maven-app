node 
{
    stage('Git checkout')
    {
        git 'https://github.com/surajr3/simple-java-maven-app.git'
    }
    
    stage('Building Maven')
    {
       def props = readProperties file:'/var/lib/jenkins/workspace/gkefinal/build.properties'
       def Var1= props['BUILD_PROJECT_VERSION']
       withEnv(["Var1=${Var1}"]) {
      
       }
        def mvnHome = tool name: 'Maven', type: 'maven'
        
        echo "anilanil" 
        
        def name = "')'^no!t@mrofn!\$'('" 
        sh "${mvnHome}/bin/mvn clean -DreleaseVersion=${name} -DdevelopmentVersion=${Var1}-'gkefinal'"
    }
    stage(' Mail Approval')
    {
        
        emailext body: "please go to ${env.JOB_URL}", mimeType: 'text/html', subject: "${env.BUILD_URL}", to: 'anil517929@gmail.com'
        input'?'
    }
    
   
}
