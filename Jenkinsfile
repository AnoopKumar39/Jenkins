//StudentApp-UI-CI
pipelineJob('StudentApp-UI-CI') {
  parameters {
        stringParam('RELEASE_VERSION', '', 'RELEASE_VERSION Ex: 0.0.1')
  }
  configure { flowdefinition ->
    flowdefinition << delegate.'definition'(class:'org.jenkinsci.plugins.workflow.cps.CpsScmFlowDefinition',plugin:'workflow-cps') {
      'scm'(class:'hudson.plugins.git.GitSCM',plugin:'git') {
        'userRemoteConfigs' {
          'hudson.plugins.git.UserRemoteConfig' {
            'url'('https://github.com/AnoopKumar39/Jenkins.git')
            'credentialsId'('Git-cred')
          }
        }
        'branches' {
          'hudson.plugins.git.BranchSpec' {
            'name'('*/master')
          }
        }
      }
      'scriptPath'('jobs/student-ci')
      'lightweight'(true)
    }
  }
}
