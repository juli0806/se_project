# 소프트웨어 공학 Mission 2

## 조원
- 팀장 신현석 C111093
- 팀원 이예지 B935343

## 개발 역할 분담
- Book, BookManager 구현: 이예지
- search_revision 구현: 신현석
- JUnit 테스트: 이예지
- PerformanceTest 구현: 신현석
- Jenkins CI/CD 구축: 신현석, 이예지

## 프로젝트 구조
- `Book.java` : Book class 객체
- `bookManager.java` : 도서 관리
  - addBook()
  - getAllBooks()
  - removeBookById()
  - findBooksByTitle()
  - findBooksByAuthor()
  - findBooksByYearOfPublication()
  - sortById()
  - search_bs()
- `BookManagerTest.java`:  JUnit 테스트 코드
- `PerformanceTest.java`: 기본 search와 search_bs 성능 테스트 코드
- `Jenkinsfile`: 신현석 Jenkins 파이프라인 정의
- `Jenkinsfile_YJ`: 이예지 Jenkins 파이프라인 정의


## Jenkins CI/CD 구축
#### 신현석
Jenkins 파이프라인 실행 로그:
```
Started by user admin
Obtained Practice/Jenkinsfile from git https://github.com/juli0806/se_project
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in C:\ProgramData\Jenkins\.jenkins\workspace\se_project
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
using credential podonamu1
 > git.exe rev-parse --resolve-git-dir C:\ProgramData\Jenkins\.jenkins\workspace\se_project\.git # timeout=10
Fetching changes from the remote Git repository
 > git.exe config remote.origin.url https://github.com/juli0806/se_project # timeout=10
Fetching upstream changes from https://github.com/juli0806/se_project
 > git.exe --version # timeout=10
 > git --version # 'git version 2.45.2.windows.1'
using GIT_ASKPASS to set credentials podonamu1
 > git.exe fetch --tags --force --progress -- https://github.com/juli0806/se_project +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe rev-parse "refs/remotes/origin/jenkins^{commit}" # timeout=10
Checking out Revision 2168c90681178590facbc417b665a764e2962111 (refs/remotes/origin/jenkins)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f 2168c90681178590facbc417b665a764e2962111 # timeout=10
Commit message: "jenkins test"
 > git.exe rev-list --no-walk 39d6d4c06fb44c8114aa4f3829b7640d361106a4 # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Checkout)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
using credential podonamu1
 > git.exe rev-parse --resolve-git-dir C:\ProgramData\Jenkins\.jenkins\workspace\se_project\.git # timeout=10
Fetching changes from the remote Git repository
 > git.exe config remote.origin.url https://github.com/juli0806/se_project # timeout=10
Fetching upstream changes from https://github.com/juli0806/se_project
 > git.exe --version # timeout=10
 > git --version # 'git version 2.45.2.windows.1'
using GIT_ASKPASS to set credentials podonamu1
 > git.exe fetch --tags --force --progress -- https://github.com/juli0806/se_project +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe rev-parse "refs/remotes/origin/jenkins^{commit}" # timeout=10
Checking out Revision 2168c90681178590facbc417b665a764e2962111 (refs/remotes/origin/jenkins)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f 2168c90681178590facbc417b665a764e2962111 # timeout=10
Commit message: "jenkins test"
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\se_project>javac -encoding UTF-8 -d classes Practice/src/Book.java Practice/src/BookManager.java Practice/src/PerformanceTest.java 
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (PerformanceTest)
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\se_project>java -cp classes PerformanceTest  1>test_results.txt 
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Declarative: Post Actions)
[Pipeline] archiveArtifacts
Archiving artifacts
[Pipeline] echo
Build and test succeeded
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
```
#### 이예지

Jenkins 파이프라인 실행 로그:
```
Started by user unknown or anonymous
Obtained Practice/Jenkinsfile_YJ from git https://github.com/juli0806/se_project.git/
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in C:\ProgramData\Jenkins\.jenkins\workspace\Hongik
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
using credential Hongik-Test
 > git.exe rev-parse --resolve-git-dir C:\ProgramData\Jenkins\.jenkins\workspace\Hongik\.git # timeout=10
Fetching changes from the remote Git repository
 > git.exe config remote.origin.url https://github.com/juli0806/se_project.git/ # timeout=10
Fetching upstream changes from https://github.com/juli0806/se_project.git/
 > git.exe --version # timeout=10
 > git --version # 'git version 2.45.1.windows.1'
using GIT_ASKPASS to set credentials Hongik-Test
 > git.exe fetch --tags --force --progress -- https://github.com/juli0806/se_project.git/ +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe rev-parse "refs/remotes/origin/master^{commit}" # timeout=10
Checking out Revision 793dc74440f2ab57dc82dad2f240f2fc43767e1c (refs/remotes/origin/master)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f 793dc74440f2ab57dc82dad2f240f2fc43767e1c # timeout=10
Commit message: "Create Jenkinsfile_YJ"
 > git.exe rev-list --no-walk d0ae8b8d9514804fbbce2b74d04566df88c3c6ca # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Checkout)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
using credential Hongik-Test
 > git.exe rev-parse --resolve-git-dir C:\ProgramData\Jenkins\.jenkins\workspace\Hongik\.git # timeout=10
Fetching changes from the remote Git repository
 > git.exe config remote.origin.url https://github.com/juli0806/se_project.git/ # timeout=10
Fetching upstream changes from https://github.com/juli0806/se_project.git/
 > git.exe --version # timeout=10
 > git --version # 'git version 2.45.1.windows.1'
using GIT_ASKPASS to set credentials Hongik-Test
 > git.exe fetch --tags --force --progress -- https://github.com/juli0806/se_project.git/ +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe rev-parse "refs/remotes/origin/master^{commit}" # timeout=10
Checking out Revision 793dc74440f2ab57dc82dad2f240f2fc43767e1c (refs/remotes/origin/master)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f 793dc74440f2ab57dc82dad2f240f2fc43767e1c # timeout=10
Commit message: "Create Jenkinsfile_YJ"
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\Hongik>javac -encoding UTF-8 -d . Practice/src/Book.java Practice/src/BookManager.java Practice/src/PerformanceTest.java 
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (PerformanceTest)
[Pipeline] dir
Running in C:\ProgramData\Jenkins\.jenkins\workspace\Hongik\Practice\src
[Pipeline] {
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\Hongik\Practice\src>java PerformanceTest  1>test_results.txt 
[Pipeline] }
[Pipeline] // dir
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Declarative: Post Actions)
[Pipeline] archiveArtifacts
Archiving artifacts
[Pipeline] echo
Build and test succeeded
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
```

#### test_result
 결과가 'test_results.txt'에 저장됨 :
```
모든 책에 대한 기본 Search 시작
모든 책에 대한 기본 Search 종료
소요 시간(ns) : 166948900 ns
소요 시간(초) : 0.1669489 초
모든 책에 대한 Binary Search 시작
모든 책에 대한 Binary Search 종료
소요 시간(ns) : 598121000 ns
소요 시간(초) : 0.598121 초
기본 Search가 Binary Search보다 0.4311721 초만큼 빠르다.
```

## Git 및 Jenkins 에러 메시지

### Jenkins 에러 메시지

1. 경로 실수 에러
```
remote: error: GH001: Large files detected. You may want to try Git Large File Storage - https://git-lfs.github.com.
remote: error: Trace: 5b1b5b3c9c5d6a1234567890abcdef12
remote: error: See http://git.io/iEPt8g for more information.
remote: error: File build/reports/performance/performance-test-results.pdf is 112.12 MB; this exceeds GitHub's file size limit of 100.00 MB
```
 2. 자바 환경변수 꼬임 에러
```
C:\ProgramData\Jenkins\.jenkins\workspace\Hongik>java -d classes Practice/src/PerformanceTest 
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
Unrecognized option: -d
```
 3. 파일 권한 에러
```
C:\ProgramData\Jenkins.jenkins\workspace\Hongik\Practice\src>java PerformanceTest  1>..
액세스가 거부되었습니다.
```
 4. 파이프라인 설정 에러
![jenkins_pipeline_connot](https://github.com/juli0806/se_project/assets/76528783/73c36aa6-eb88-492e-ad01-487dbe45a25e)

 5. cannot found book 에러
  ![jenkins_book_notfound](https://github.com/juli0806/se_project/assets/76528783/68b59674-8d53-4b88-a380-6e40e71c23e2)

### Git 에러 메시지
  1. commit message 미입력 에러 
  ![git_commit_message](https://github.com/juli0806/se_project/assets/76528783/8774e3f1-f657-4d61-8a5b-ae40493440cd)

  2. push 과정 에러

      ![git_push_error](https://github.com/juli0806/se_project/assets/76528783/4e131d41-fe9d-4efa-a4bf-6cd1f3ef2786)



## 프로젝트 저장소
https://github.com/juli0806/se_project.git

