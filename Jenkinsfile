node {
    stage ('Preparation'){
        git clone 'https://github.com/tabmy/gildedrose.git'
    }
    stage ('Build'){
        sh 'docker run -i --rm --name my-maven-project -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn install'
    }
    stage ('Results') {
        jUnit '**/target/surefire-reports/TEST-*.xml'
        archive '/target/* .jar'
    }
}
