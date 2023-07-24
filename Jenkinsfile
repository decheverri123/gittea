pipeline {
    agent any

    stages{

        stage('Checkout'){
            steps{
                url: 'https://github.com/decheverri123/gittea'
                echo "Git information: ${env.GIT_URL} and ${env.GIT_BRANCH}"
                setBuildStatus("Build complete", "SUCCESS")
            }
        }


    }
}

void setBuildStatus(String message, String state) {
    step([
        $class: "GitHubCommitStatusSetter",
        reposSource: [$class: "ManuallyEnteredRepositorySource", url: "https://github.com/decheverri123/gittea"],
        contextSource: [$class: "ManuallyEnteredCommitContextSource", context: "ci/jenkins/build-status"],
        errorHandlers: [[$class: "ChangingBuildStatusErrorHandler", result: "UNSTABLE"]],
        statusResultSource: [ $class: "ConditionalStatusResultSource", results: [[$class: "AnyBuildResult", message: message, state: state]] ]
    ])
}
