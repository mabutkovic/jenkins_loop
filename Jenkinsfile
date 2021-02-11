def list_projects = ["Project1", "Project2"]
def list_environments = ["Staging", "Prod"]
pipeline {
    agent none
    stages {
        stage('Dynamic Stages') {
            agent {node 'master'}
            steps {
                script {
                    for(int i=0; i < list_projects.size(); i++) {
                        for (int j = 0; j < list_environments.size(); j++) {
                            stage(list_projects[i]) {
                                stage(list_environments[j]) {
                                    echo "Element: $i"
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}