//@Library('piper-library-os') _  --> will be set by the testing framework

node() {
    stage('INIT') {
        def scmInfo = checkout scm
        setupCommonPipelineEnvironment script: this
        scmInfo.GIT_COMMIT
        commonPipelineEnvironment.setGitCommitId(scmInfo.GIT_COMMIT)
        echo "GIT_COMMIT: ${commonPipelineEnvironment.gitCommitId}"
    }
    stage('TMS_UPLOAD') {

        echo "GIT_COMMIT 2: ${this.commonPipelineEnvironment.gitCommitId}"

        tmsUpload script: this,
                  mtaPath: 'dummy.mtar',
                  nodeName: '__piperIntegrationTest',
                  credentialsId: 'tmsUpload',
                  verbose: true,
                  customDescription: 'test123'
    }
//    stage('VALIDATION') {
//        sh '''#!/bin/bash
//              curl --header \
//                   -vvv \
//                   --fail \
//                   https://transport-service-app-backend.tshotfix.cfapps.eu10.hana.ondemand.com/nodes/1/transportRequests?status=in
//           '''
//    }
}
