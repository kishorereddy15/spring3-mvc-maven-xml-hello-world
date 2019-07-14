node { 
     def mvnHome 
    stage('getscm')
    { 
      git 'https://github.com/kishorereddy15/spring3-mvc-maven-xml-hello-world.git'
     
      mvnHome = tool 'maven'
   }
   
   stage('Build') 
   {
      
      if (isUnix()) 
        { sh "'${mvnHome}/bin/mvn'-Dmaven.test.failure.ignore clean package"
        
             }
      else 
          { 
           echo 'this is build maven artifact'
        
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean
 
         package/)
      }
   }
   
   stage ('deploy')
         {
            echo 'deployment started' bat '''copy 
       C:\\Users\\Home\\.jenkins\\workspace\\pipe-jenkins\\target\\*.war 
       C:\\Users\\Home\\Desktop\\softwares\\apache-tomcat-9.0.21\\webapps\\'''
   }
}
