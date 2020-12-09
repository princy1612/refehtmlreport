node{
  
    stage('test advance script') {
checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'adf05bd0-541b-40d0-b33f-a6aae4f95c10', url: 'https://github.com/princy1612/refehtmlreport.git']]])
       echo " SERVICE_NAME = 'html report'"
            echo "current build number: ${currentBuild.number}"
            echo "previous build number: ${currentBuild.previousBuild.getNumber()}"
             //echo 'BRANCH_NAME =     
    }
    stage("checkuot")
    {
checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'adf05bd0-541b-40d0-b33f-a6aae4f95c10', url: 'https://github.com/princy1612/refehtmlreport.git']]])
bat 'npm install'
    }
    stage("execution of code")
    {
     checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'adf05bd0-541b-40d0-b33f-a6aae4f95c10', url: 'https://github.com/princy1612/refehtmlreport.git']]])
     bat ''' src//banK $ node Bank.js '''
    }
  stage("installation of jasmine")
  {
    bat ''' npm install jasmine-node '''
  }
  stage("set the jasmine")
  {
    bat''' npx jasmine init'''
  }
  stage("exexute the jasmine")
  {
    bat''' npx jasmine spec/bank.js'''
    
    stage("html report")
    {
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'C:\\Users\\40010003\\Desktop\\JS-Jasmineminiproject-main\\Jasmine Frame Work', reportFiles: 'SpecRunner.html', reportName: 'HTML Report', reportTitles: ''])
    }
 
}

    }
    
 
