node {
    stage ('Example') {
        if (env.BRANCH_NAME == 'MASTER') {
            echo 'I only execute on the master branch'
        } else {
            echo 'I execute elsewhere'
        }
    }
}