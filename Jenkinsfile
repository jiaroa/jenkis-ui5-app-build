@Library('piper-lib-os') _
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('build') {
        mtaBuild script: this
    }    
	stage('deploy') {
		cloudFoundryDeploy script: this,
			cfHome: 'https://api.cf.us10.hana.ondemand.com/'
	}	
}
