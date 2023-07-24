pipeline {
    agent any

    stages{

        stage('Checkout'){
            steps{
                url: 'https://github.com/decheverri123/gittea'
                echo "Git information: ${env.GIT_URL} and ${env.GIT_BRANCH}"
            }
        }


    }
}
