@Library('piper-lib-os') _

node() {
    stage('INIT') {
        def scmInfo = checkout scm
        setupCommonPipelineEnvironment script: this
        scmInfo.GIT_COMMIT
        commonPipelineEnvironment.setGitCommitId(scmInfo.GIT_COMMIT)
        echo "scm: ${scm.class.name}"
    }
    stage('TMS_UPLOAD') {

       // tmsUpload script: this,
       //           mtaPath: 'dummy.mtar',
       //           nodeName: '__piperIntegrationTest',
       //           credentialsId: 'tmsUpload',
       //           verbose: true
                  // customDescription: 'test123'
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
