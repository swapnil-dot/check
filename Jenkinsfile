node {
    checkout scm
    docker.image('ubuntu').withRun('-e "MYSQL_ROOT_PASSWORD=my-secret-pw"') { c ->
        docker.image('swapy25/maven').inside("") {
            /* Wait until mysql service is up */
            sh 'mvn --version'
        }
        docker.image('swapy25/vim').inside("") {
            /*
             * Run some tests which require MySQL, and assume that it is
             * available on the host name `db`
             */
            sh 'vim --version'
        }
    }
}
