#!/usr/bin/env groovy
@Library('my-shared-library@master') _ //explicit call to sl
pipeline {
  agent {
    label 'ec2'
  }
  stages {
    stage ('Build') {
      steps {
        builder('build','trainSchedule.zip')
      }
    }
    stage ('check logs') {
      steps {
        filterLogs('Warning',1)
      }
    }
  }
}
