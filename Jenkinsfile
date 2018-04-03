node (kubernetes-node) {
  stage('Find current image tag') {
    MY_APP = "my-app"
    RELEASE_VERSION = sh (
      script: """
        kubectl get deployment ${MY_APP} -o=jsonpath='{\$.spec.template.spec.containers[:1].image}' | awk -F ":" '{print \$2}'
      """,
      returnStdout: true
    ).trim()
  }
}
