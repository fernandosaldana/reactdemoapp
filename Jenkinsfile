node{
    stage("Git Clone"){
        git branch: 'main', credentialsId: 'GIT_HUB_CREDENTIALS', url: 'https://github.com/fernandosaldana/reactdemoapp'
    }
    stage("Docker Build"){

        sh 'docker build -t myfsdcc_pipeline .'
        sh 'docker tag myfsdcc_pipeline fernandosaldana/fsdreactdemo:latest'

    }

    stage("Push image to Dockerhub"){
	sh 'docker login -u fernandosaldana -p 9C3r@#8144'
        sh 'docker push fernandosaldana/fsdreactdemo:latest'
    }
}
