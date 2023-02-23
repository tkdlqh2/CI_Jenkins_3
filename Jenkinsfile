node {
  stage('SCM') {
    checkout scm
  }

  stage('SonarQube Analysis') {
    withSonarQubeEnv() {
      sh 'chmod +x gradlew'
      sh "./gradlew sonar"
    }
  }

  //jacoco 까지 사용할 거면 밑에 내용도 추가해주세요
      jacoco(
          execPattern: 'build/*.exec',
          classPattern: 'build/classes',
          sourcePattern: 'src/main/java',
          exclusionPattern: 'src/test*'
    )
}