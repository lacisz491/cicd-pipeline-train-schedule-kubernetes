pipeline {
    agent any
    environment {
        //be sure to replace "willbla" with your own Docker Hub username
        DOCKER_IMAGE_NAME = "willbla/train-schedule"
    }
    stages {
        stage('DeployToProduction') {
            when {
                branch 'master'
            }
            steps {
                //implement Kubernetes deployment here
                kubernetesDeploy(
                    kubeconfigId: 'kubeconfig-1',
                    configs: 'train-schedule-kube.yml',
                    enableConfigSubstitution: true
                    )
            }
        }
    }
}
