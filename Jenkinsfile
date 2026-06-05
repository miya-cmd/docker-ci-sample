stage('Checkout') {
    steps {
        checkout([
            $class: 'GitSCM',
            branches: [[name: '*/main']],
            userRemoteConfigs: [[
                url: 'https://github.com/miya-cmd/docker-ci-sample.git',
                credentialsId: 'github-token'
            ]]
        ])
    }
}
