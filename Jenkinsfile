def services = [
    "adservice",
    "cartservice",
    "checkoutservice",
    "currencyservice",
    "emailservice",
    "frontend",
    "loadgenerator",
    "paymentservice",
    "productcatalogservice",
    "recommendationservice",
    "shippingservice"
]

pipeline {
    agent any

    stages {
        stage('Build & Push All Services') {
            steps {
                script {
                    services.each { svc ->
                        stage("Building ${svc}") {
                            withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
                                dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/${svc}/") {
                                    sh "docker build -t seyiniceman/${svc}:latest ."
                                    sh "docker push seyiniceman/${svc}:latest"
                                    sh "docker rmi seyiniceman/${svc}:latest"
                                    sh "docker system prune -a -f --volumes"
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}
// pipeline {
//     agent any

//     stages {

//         stage('adservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir('/var/lib/jenkins/workspace/Microservice_Deployment/src/adservice/') {
//                             sh "docker build -t seyiniceman/adservice:latest ."
//                             sh "docker push seyiniceman/adservice:latest"
//                             sh "docker rmi seyiniceman/adservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('cartservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/cartservice/src/") {
//                             sh "docker build -t seyiniceman/cartservice:latest ."
//                             sh "docker push seyiniceman/cartservice:latest"
//                             sh "docker rmi seyiniceman/cartservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('checkoutservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/checkoutservice/") {
//                             sh "docker build -t seyiniceman/checkoutservice:latest ."
//                             sh "docker push seyiniceman/checkoutservice:latest"
//                             sh "docker rmi seyiniceman/checkoutservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('currencyservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/currencyservice/") {
//                             sh "docker build -t seyiniceman/currencyservice:latest ."
//                             sh "docker push seyiniceman/currencyservice:latest"
//                             sh "docker rmi seyiniceman/currencyservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('emailservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/emailservice/") {
//                             sh "docker build -t seyiniceman/emailservice:latest ."
//                             sh "docker push seyiniceman/emailservice:latest"
//                             sh "docker rmi seyiniceman/emailservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('frontend') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/frontend/") {
//                             sh "docker build -t seyiniceman/frontend:latest ."
//                             sh "docker push seyiniceman/frontend:latest"
//                             sh "docker rmi seyiniceman/frontend:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('loadgenerator') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/loadgenerator/") {
//                             sh "docker build -t seyiniceman/loadgenerator:latest ."
//                             sh "docker push seyiniceman/loadgenerator:latest"
//                             sh "docker rmi seyiniceman/loadgenerator:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('paymentservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/paymentservice/") {
//                             sh "docker build -t seyiniceman/paymentservice:latest ."
//                             sh "docker push seyiniceman/paymentservice:latest"
//                             sh "docker rmi seyiniceman/paymentservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('productcatalogservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/productcatalogservice/") {
//                             sh "docker build -t seyiniceman/productcatalogservice:latest ."
//                             sh "docker push seyiniceman/productcatalogservice:latest"
//                             sh "docker rmi seyiniceman/productcatalogservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('recommendationservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/recommendationservice/") {
//                             sh "docker build -t seyiniceman/recommendationservice:latest ."
//                             sh "docker push seyiniceman/recommendationservice:latest"
//                             sh "docker rmi seyiniceman/recommendationservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('shippingservice') {
//             steps {
//                 script {
//                     withDockerRegistry(credentialsId: 'docker-hub', toolName: 'docker') {
//                         dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/shippingservice/") {
//                             sh "docker build -t seyiniceman/shippingservice:latest ."
//                             sh "docker push seyiniceman/shippingservice:latest"
//                             sh "docker rmi seyiniceman/shippingservice:latest"
//                             sh 'docker system prune -a -f --volumes'
//                         }
//                     }
//                 }
//             }
//         }

//         stage('EKS-Deployment') {
//             steps {
//                 withKubeConfig(
//                     caCertificate: '',
//                     clusterName: 'dev_myAppp-eks-cluster',
//                     contextName: '',
//                     credentialsId: 'k8s',
//                     namespace: 'webapps',
//                     restrictKubeConfigAccess: false,
//                     serverUrl: 'https://164E26B4CF9979625E425CA707EABA03.gr7.us-east-1.eks.amazonaws.com'
//                 ) {
//                     sh 'kubectl apply -f deployment-service.yaml'
//                     sh 'kubectl get pods'
//                     sh 'kubectl get svc'
//                 }
//             }
//         }

//     }
// }
