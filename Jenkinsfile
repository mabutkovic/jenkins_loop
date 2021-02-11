def list_projects
def list_environments
pipeline {
    agent none
    stages {
        stage('Create List') {
            agent {node 'master'}
            steps {
                script {
                    // you may create your list here, lets say reading from a file after checkout
                    list_projects = ["Project1", "Project2"]
                    list_environments = ["Staging", "Prod"]
                }
            }
        }
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