node {
    printMessage("Pipeline Start")

    stage("Fetch Source Code") {
        git 'https://github.com/mandeepmails/ActivityA'
    }

    dir('ActivityA') {
        stage("Install Requirements") {
            sh 'makefile install'
        }

        stage("Run Tests") {
            sh 'makefile jenkins_test'
        }

        stage("Deploy") {
            if (env.BRANCH_NAME == "main") {
                printMessage("Deploying to main branch")
            } else {
                printMessage("No deployment specified for this branch")
            }
        }
    }

    printMessage("Pipeline End")
}

def printMessage(message) {
    echo "${message}"
}




















/*
node {
    printMessage("Pipeline Start")

    stage("Fetch Source Code") {
        git "https://github.com/mandeepmails/ActivityA"
    }

    dir('Lesson5/ActivityA') {
        stage("Install Requirements") {
            sh 'make install'
        }

        stage("Run Tests") {
            sh 'make jenkins_test'
        }

        stage("Deploy") {
            if (env.BRANCH_NAME == "main") {
                printMessage("deploying master branch")
            } else {
                printMessage("no deployment specified for this branch")
            }
        }
    }

    printMessage("Pipeline End")
}

def printMessage(message) {
    echo "${message}"
}
*/