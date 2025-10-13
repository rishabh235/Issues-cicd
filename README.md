stage('udeploy: import-artifact') {
    logStage('udeploy-import-artifact') {

        def foundationKey = pcfFoundation.toLowerCase()
        def pcfDevManifest = manifestFiles.get(foundationKey, manifestFiles['dev-west'])

        echo "Foundation: ${pcfFoundation}"
        echo "Manifest selected: ${pcfDevManifest}"

        uDeployDevVersionImport(gitRepositoryName, appVersion, pcfDevManifest, pcfRoute)
    }
}
