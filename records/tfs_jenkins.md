![tfs_jenkins_illustration](https://github.com/Semant1ka/pictures/blob/master/illustrations/jenkins_001.jpg)

My setup was TFS 2015 and latest Jenkins TFS Plugin.

1. Push all the results in the end of pipeline
  `step([$class: 'TeamCollectResultsPostBuildAction', requestedResults: [[includes: '**/*tests.xml', teamResultType: 'JUNIT']]])`
  
2. Check only *Capture console output and wait for completion* in Queue Jenkins Job step setup,
   and *Capture pipeline output and wait for pipeline completion* should be left unchecked.

3. All parameters that you want to pass from TFS build should be referenced in Jenkins with this kind of notation
  `"${params.BRANCH}"`, refence like `branch = BRANCH` will not work in pipeline.
