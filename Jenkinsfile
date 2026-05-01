#!/usr/bin/env groovy

pipeline {
    parameters { 
        booleanParam(name: 'SBOM_STUDIO', defaultValue: true, description: 'Enable CyBeats SBOM Studio')
    }
    agent any
    stages {
        stage('Stage 0') {
            steps {
                echo 'Testing Jenkins SBOM Studio Plugin'
                sh 'pwd'
                sh 'ls -al'
            }
        }

        stage('Stage 1') {
            steps {
                echo 'Check General Functionality'
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE'){
                    sbomStudio filePath:'sbom/test.cdx.json',
                                manufacturerId:'CyBeats',
                                supplierId:'CyBeats' 
                                pkgType:'', 
                                sbomComponentName:'', 
                                sbomComponentNamespace:'', 
                                sbomComponentVersion:'', 
                                subType:'application'
                }
            }
        }
    }
}

