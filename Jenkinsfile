pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh ''' #!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'

                # TODO fill out the path to conda here
                python -m venv mlip_lab
                source mlip_lab/bin/activate
                pip install pytest numpy pandas scikit-learn -c conda-forge

                # TODO Complete the command to run pytest
                pytest test_utility.py

                # echo 'pytest not runned'
                # exit 1 #comment this line after implementing Jenkinsfile
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
