pipeline{ agent any stages{
stage("Git build"){ steps{
git branch: 'main', credentialsId: '', url: https://github.com/AbhirakshakDhiman/Q2_DevOps_Ans'
}
}
stage("Build Docker Image"){ steps{
bat 'docker build -t my-maven-app:01 . '
}
}
stage("Run the test"){ steps{
bat 'docker run --name app5 my-maven-app:01'
bat 'docker cp app5:/usr/src/app/target/surefire-reports .' bat 'docker rm -f app5'

}

}
stage("Report test result"){ steps{
bat 'dir'
junit '/surefire-reports/*.xml'
}
}

}

}


