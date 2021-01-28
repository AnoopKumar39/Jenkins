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
            'url'('https://gitlab.com/d40/jenkins.git')
            'credentialsId'('GitUserPass')
          }
        }
        'branches' {
          'hudson.plugins.git.BranchSpec' {
            'name'('*/master')
          }
        }
      }
      'scriptPath'('jobs/studentapp-ui-ci.Jenkinsfile')
      'lightweight'(true)
    }
  }
}
