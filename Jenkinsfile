pipeline{
    agent{
        label 'docker'
    }
    stages{
        //stage('checkout git'){
        //    steps{
        //        git branch: 'main', credentialsId: 'edbe325c-d85b-40c0-ba03-7254dc08a2a8', url: 'git@github.com:sergeychernyshov/elastic-role.git'
        //    }
        //}
        stage('install molecule'){
            steps{
                sh 'pip3 install -r test-requirements.txt'
                sh 'echo ===install finish==='
            }
        }
        stage('run molecule test'){
            steps{
                sh 'molecule test' 
                //sh 'sleep 35'
                sh 'echo ===molecule test finish==='
                cleanWs()
            }
        }
    }
}