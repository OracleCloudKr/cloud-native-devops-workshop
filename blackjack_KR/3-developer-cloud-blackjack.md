# PART III : BlackJack 웹서비스 애플리케이션 테스트, 빌드 및 배포


## 저장소(Repository)에서 BlackJack 프로젝트 다운로드


로컬 컴퓨터에 [blackjack.zip](BlackJack.zip) 파일 다운로드 

## 로컬 서버에 BlackJack 애플리케이션 배포


아래 지침에 따라 프로젝트와 함께 제공(bundle)되는 Apache Tomcat Server에 BlackJack 애플리케이션을 배포하십시오. 

1. 윈도우 파일탐색기를 열고 **cloud** 디렉토리로 이동하십시오. 

2. **cloud** 디렉토리 내에 **BlackJack** 디렉토리를 만들고 이전 Lab에서 다운로드한 **BlackJack.zip** 파일을 복사하십시오. 

3. **BlackJack.zip** 파일을 **cloud** > **BlackJack** 디렉토리에 압축을 풉니다. 

4. 바탕화면의 바로가기를 사용하여 Netbeans를 실행합니다. 

5. Netbeans에서 **blackjack-part2** 프로젝트를 엽니다. 

    <img src="images/3/image1.png" width="314" height="163" />


**참고 :** 프로젝트 이름에 \[Unloaded] 태그가 표시되면 프로젝트를 마우스 오른쪽 단추로 클릭하고 **프로젝트 문제 해결**을 선택한 다음 해결 버튼을 클릭하십시오. Netbeans가 Maven 관련 파일을 다운로드 할 때까지 기다렸다가 닫기 버튼을 클릭하십시오. 

6. 프로젝트에서 마우스 오른쪽 클릭하고 **Clean and Build** 옵션을 선택하십시오. 

    <img src="images/3/image2.png" width="132" height="167" />


7. 프로젝트에서 마우스 오른쪽 클릭하고 **Run**을 선택하여 Tomcat 서버에 프로젝트를 배포합니다. 

    <img src="images/3/image3.png" width="138" height="173" />


8. 사용가능한 메인 클래스 목록에서 **com.example.blackjack.rest.Application**을 선택하고 **Select Main Class** 버튼을 클릭하십시오. 

    <img src="images/3/image4.png" width="252" height="245" />


9. 출력창에 “Started Application in <<seconds>> seconds (JVM running for 5.19)” 과 같은 메시지가 나타납니다. 

    <img src="images/3/image5.png" width="490" height="280" />


**참고 :** 포트 충돌 문제로 인해 프로젝트를 실행할 때 문제가 발생할 수 있습니다. 이 애플리케이션은 Apache Tomcat Server에 배포되며 클라이언트 요청을 수신하기 위한  **8080** 로컬 포트 ​​번호가 필요합니다.**8080** 로컬 포트 ​​번호에서 실행중인 서비스를 중지하십시오. 

**TCPView**도구는 이 포트 번호를 사용하여 프로세스를 식별하고 종료하는 데 사용할 수 있습니다. 

[**Download Link**](https://technet.microsoft.com/en-us/sysinternals/bb897437) 

## 로컬에 배포된 BlackJack 애플리케이션 테스트


로컬/원격서버에 배포된 후 기능을 테스트하기 위한 HTML-5 클라이언트 프로그램이 이미 BlackJack 애플리케이션과 함께 제공되었습니다.

아래 지시사항에 따라 BlackJack 애플리케이션을 테스트하십시오. 

1. 윈도우 파일탐색기를 열고 **cloud> BlackJack> html5-client** 디렉토리로 이동하십시오. 

2. 브라우져를 실행해서 index.html 파일을 엽니다. 

3. 첫번째 필드인 **Service**가 **<http://127.0.0.1:8080/>** 로 값이 입력되어 있는지 확인하십시오. 두 번째 필드에 1에서 9 사이의 값을 입력한 다음 연결(connect)을 클릭하십시오. 

    <img src="images/3/image6.png" width="528" height="229" />


4. 게이밍 콘솔에 연결되면 오른쪽 상단의 **디버그 켜기/끄기** 버튼을 클릭하여 디버그 콘솔을 볼 수 있습니다. 

    <img src="images/3/image7.png" width="535" height="251" />


UI에서 **Hit** 및 **Stand** 버튼을 사용하여 게임을 할 수 있습니다. 

이 HTML5 클라이언트 프로그램은 컴퓨터에서 로컬로 실행되는 Tomcat Server에 배포된 BlackJack 게이밍 애플리케이션과 상호동작합니다. 테스트가 완료되면 이 HTML5 클라이언트 프로그램을 닫습니다. 

## BlackJack 애플리케이션을 위한 애플리케이션 아카이브 파일들 생성


Oracle Application Container Cloud(이하 ACCS)는 Java Platform, Standard Edition (Java SE) 및 Node.js 애플리케이션을 배포 및 실행할 수 있습니다. 먼저 애플리케이션을 배포하기 위해 필수 구성정보가 포함된 **ZIP** 또는 **Gzipped Tar (TGZ)** 아카이브 파일로 애플리케이션을 압축(compress)합니다. 

아래 지시사항에 따라 애플리케이션 아카이브를 생성하십시오. 

1. Netbeans에서 blackjack-part2 애플리케이션을 아직 Open하지 않았으면 Open합니다. 

2. 프로젝트에서 마우스 오른쪽 클릭하고 **Clean** 을 클릭하십시오. 

    <img src="images/3/image8.png" width="165" height="192" />


3. 윈도우 파일탐색기를 열고 **cloud> BlackJack> blackjack-part2** 디렉토리로 이동하여 디렉토리 구조와 그 내용을 확인하십시오. 

    <img src="images/3/image9.png" width="444" height="102" />


**참고 :** manifest.json 파일은 Oracle Application Container Cloud Service에 배포되는 모든 애플리케이션에 필요합니다. 이 파일이 .zip, .tar 또는 .tar.gz 파일의 루트 디렉토리에 없으면 배포(deploy)가 실패(fail)합니다. 이 파일에 최소한 런타임 환경의 주(Major) 버전과 실행(launch) 명령어을 지정해야 합니다.

**이 예제에서 manifest.json 파일의 내용**: 

```json
    {
      "runtime": {
        "majorVersion": "8"
      },
      "command": "java -jar blackjack-part2-1.0.jar",
      "release": {
        "version": "1.0",
        "build": "1",
        "commit": "1A2B345"
      },
      "notes": "Blackjack Web Service"
    }
```


4. Netbeans로 이동(switch)하고 프로젝트에서 마우스 오른쪽 클릭한 다음 **Build** 를 클릭하십시오.

    <img src="images/3/image10.png" width="184" height="237" />


5. **cloud > BlackJack > blackjack-part2** 디렉토리로 이동해서 **target** 이라는 새로운 디렉토리가 만들어졌는지 확인합니다. 

6. **target** 디렉토리를 확인하십시오. **.zip 및 .tar.gz** 배포 파일이 생성되었음을 알 수 있습니다. 이것들은 OACCS에 배포하는 데 사용할 수 있는 애플리케이션 아카이브 파일입니다. 

    <img src="images/3/image11.png" width="466" height="178" />


## 개발자 클라우드 서비스(이하 DevCS)에서 새 프로젝트 만들기


아래 지시사항에 따라 Developer Cloud Service(DevCS)에서 빈(empty) 프로젝트를 생성합니다. 

1. Oracle 클라우드 계정에 로그인하십시오. 

2. 대시보드에서 **Developer Cloud Service** 를 클릭하여 **ServiceDetails : developer85599 (Oracle Developer Cloud Service)** 페이지로 이동하십시오. 

    <img src="images/3/image12.png" width="466" height="137" />


3. **서비스 콘솔 열기** 버튼을 클릭하십시오. 

    <img src="images/3/image13.png" width="460" height="225" />


4. **새 프로젝트** 를 클릭하십시오. 

    <img src="images/3/image14.png" width="378" height="232" />


5. 아래 스크린샷과 같이 프로젝트 이름과 설명을 입력하고 **다음** 을 클릭하십시오. 

    <img src="images/3/image15.png" width="378" height="268" />


6. **빈 프로젝트** 템플릿을 선택하고 **다음** 을 클릭하십시오. 

    <img src="images/3/image16.png" width="378" height="271" />


7. Wiki Markup 드롭다운 목록에서 **MARKDOWN** 을 선택하고 **Finish**를 클릭하십시오.

    <img src="images/3/image17.png" width="388" height="280" />


8. BlackJack-Part2 프로젝트의 프로비저닝에는 몇 분이 소요될 수 있습니다. 모든 모듈들이 프로비저닝 되고나서 BlackJack-Part2 홈 스크린으로 리디렉션 될 때까지 기다리십시오. 

    <img src="images/3/image18.png" width="444" height="161" />


## Developer Cloud Service에서 GIT 저장소 만들기


아래 지시사항에 따라 DevCS에 빈 GIT 저장소를 만듭니다. 

1. **REPOSITORIES** 섹션에서 **New Repository** 버튼을 클릭하십시오. 

    <img src="images/3/image19.png" width="426" height="154" />


2. New Repository 창에서 아래 스크린샷과 같이 저장소 이름과 설명을 입력하고 **Create**를 클릭합니다. 

    <img src="images/3/image20.png" width="426" height="362" />


3. 저장소를 만드는 데 몇 분이 걸릴 수 있습니다. BlackJack-Part2Repo 저장소가 만들어지고 홈 페이지로 리다이렉트 될 때까지 기다리십시오. 

    <img src="images/3/image21.png" width="426" height="112" />


4. BlackJack-Part2Repo 홈 페이지에서 HTTP 탭을 클릭하고 URL을 복사합니다. 

    <img src="images/3/image22.png" width="546" height="143" />


## GIT 저장소 복제(Clone)


아래 지시사항에 따라 DevCS의 GIT 저장소에 BlackJack-Part2 프로젝트를 복제(clone)하십시오. 

1. GIT 저장소를 복제(clone)하려면 먼저 저장소의 루트 디렉토리인 cloud/BlackJack 디렉토리로 이동(Change)하십시오. 

2. `git clone https://ora1@developer.em2.oraclecloud.com/developer85599-ouopc084/s/developer85599-ouopc084\_blackjack-part2\_4112/scm/BlackJack-Part2Repo.git` 명령어를 실행합니다.

    <img src="images/3/image23.png" width="507" height="166" />


**노트:** 

- 메시지가 나타나면 클라우드 계정 사용자 이름과 암호를 입력하십시오. 
- 사용자 이름과 암호를 입력하라는 메시지가 표시되지 않고 이 명령이 403 오류로 실패하면 암호를 명시적으로 넣으십시오.
  예를 들어: `git clone https://ora1@developer.em2.oraclecloud.com/developer85599-ouopc084/s/developer85599-ouopc084\_blackjack-part2\_4112/scm/BlackJack-Part2Repo.git`

- 이 명령어의 출력은 아래 명령어의 출력과 유사해야 합니다.


3. **cloud/BlackJack** 디렉토리 내에 **BlackJack-Part2Repo** 라는 새 디렉토리가 생성됩니다. 

4. **blackjack-part2** 프로젝트 디렉토리를 **cloud/BlackJack** 디렉토리에서 **BlackJack-Part2Repo** 디렉토리로 복사해서 붙여 넣습니다. 

**참고 :** **BlackJack-Part2Repo** 디렉토리의 내용은 아래 스크린샷과 일치해야 합니다. 

<img src="images/3/image24.png" width="535" height="94" />


5. **BlackJack-Part2Repo** 디렉토리로 이동(Change)하십시오. 

        cd BlackJack-Part2Repo


6. 프로젝트 루트 디렉토리에서 GIT에 소스 파일들을 추가하십시오. 

        git add .


7. 변경사항들을 commit합니다. 

        git commit –m "commiting changes to BlackJack-Part2Repo repository"


8. DevCS의 저장소로 파일을 푸시(push)합니다. 

        git push origin master


**참고 :** 모든 파일이 저장소로 푸시될 때까지 기다리십시오. 

9. DevCS로 전환하여 저장소에 푸시된 파일들을 확인합니다. 

10. **BlackJack-Part2** 홈 페이지에서 **BlackJack-Part2Repo.git** 을 클릭하십시오. 

    <img src="images/3/image25.png" width="474" height="178" />


11. **blackjack-part2** 프로젝트 디렉토리가 DevCS의 저장소로 푸시되었음을 알 수 있습니다. 이것을 클릭하고 내용을 확인하십시오. 

    <img src="images/3/image26.png" width="478" height="154" />


## DevCS에서 프로젝트 빌드(Build)


아래 지시사항에 따라 DevCS에서 BlackJack-Part2 프로젝트를 빌드하십시오. 

1. 왼쪽 탐색 패널 창에서 **빌드(Build)** 를 누른 다음 **새 작업(New Job)** 을 누르십시오. 

    <img src="images/3/image27.png" width="421" height="190" />


2. 새 작업 창에서 작업 이름 필드에 **BlackJack-Part2BuildJob**을 입력하고 **저장**을 클릭하십시오. 

    <img src="images/3/image28.png" width="421" height="147" />


3. **메인(Main)** 탭에서 다음 값을 입력하십시오. 

- 수정이 필요한 경우 작업 이름을 수정하십시오. 
- 설명을 입력하십시오. 
- **JDK** 를 **JDK 8** 으로 설정하십시오.

    <img src="images/3/image29.png" width="421" height="188" />


4. **소스 제어(Source Control)** 탭을 클릭하십시오. 

- **Git** 을 저장소로 선택하십시오. 
- **URL** 의 경우 Git 저장소의 URL을 선택하십시오. 

    <img src="images/3/image30.png" width="391" height="203" />


5. **트리거** 탭을 클릭하십시오. 

- "SCM 폴링 일정에 기반" 체크박스를 체크하세요.

    <img src="images/3/image31.png" width="391" height="178" />


**참고 :** 이 설정은 DevCS의 자동 배포 기능을 활성화합니다. 애플리케이션이 수정되고 변경사항이 DevCS의 GIT 저장소에 커밋(commit)되면 업데이트된 코드가 자동으로 선택되어 배포됩니다. 

6. **빌드 단계(Build Steps)** 탭을 클릭하십시오. 

- `빌드 단계 추가` 를 클릭하고 `Invoke Maven 3`를 선택하십시오. 
- **목표** 를 `clean package`로 설정하십시오. 
- **POM 파일** 의 위치를 `blackjack-part2/pom.xml`로 설정하십시오. 

    <img src="images/3/image32.png" width="397" height="171" />
    <img src="images/3/image33.png" width="397" height="216" />


7. **Post Build** 탭을 클릭하십시오. 

- `Archive the artifacts`를 선택하십시오. 
- **Files To Archive** 을 blackjack-part2/target/blackjack-part2-1.0.jar, blackjack-part2/target/blackjack-part2-1.0-dist.zip 로 설정합니다.
- 압축 유형을 **NONE**으로 설정하십시오. 

    <img src="images/3/image34.png" width="451" height="186" />


8. **저장** 을 클릭한 다음 **지금 빌드** 를 클릭하십시오. 

빌드가 성공적으로 완료되면 **마지막 성공 빌드의 아티팩트들(Artifacts of Last Successful Build)** 섹션에 아래 2개의 파일이 표시됩니다. 
    -   blackjack-part2/target/blackjack-part2-1.0.jar
    -   blackjack-part2/target/blackjack-part2-1.0-dist.zip

파일 이름을 클릭하면 다운로드 할 수 있습니다. 

빌드가 실패한 경우 빌드 작업 구성을 다시 확인하거나 **Git Logs**를 클릭하여 오류에 대한 자세한 정보를 확인하십시오. 

<img src="images/3/image35.png" width="451" height="181" />


## DevCS에서 ACCS로 프로젝트 배포


아래 지시사항에 따라 BlackJack-Part2 프로젝트를 DevCS에서 Oracle Application Container Cloud Service(이하 OACCS)를 배포하십시오. 

1. 왼쪽 탐색 패널에서 **배포** 를 클릭한 다음 **새 구성** 을 클릭하십시오. 

    <img src="images/3/image36.png" width="436" height="171" />


2. **새 배포 구성** 페이지에서 아래와 같이 **구성 이름** 및 **애플리케이션 이름** 을 입력하십시오 

    <img src="images/3/image37.png" width="436" height="173" />


3. **Deployment Target** 필드에서 **New** 를 클릭하고 **Application Container Cloud** 를 선택하십시오. 

    <img src="images/3/image38.png" width="233" height="119" />


4. **Deploy to Application Container Cloud**창에서 아래 값들을 입력하고**연결 테스트**를 클릭합니다. 

- 데이터 센터 
- ID 도메인 
- 사용자 이름 
- 비밀번호 

    <img src="images/3/image39.png" width="273" height="131" />


5. **성공** 메시지가 표시되면 **연결 사용** 을 클릭하십시오. 

    <img src="images/3/image40.png" width="273" height="131" />


6. 아래 값들을 입력하고 **저장** 을 클릭하십시오. 

- **Type:** 자동 (선택: Deploy stable build only) 
- **Job:** BlackJack-Part2BuildJob 
- **Runtime:** Java 
- **Subscription:** Monthly 
- **Artifact:** blackjack-part2/target/blackjack-part2-1.0-dist.zip

    <img src="images/3/image41.png" width="393" height="137" />


7.  기어 아이콘<img src="images/3/image42.png" width="51" height="28" />을 클릭하고 **시작**을 선택하여 Oracle Application Container Cloud Service에 애플리케이션을 배포하십시오. 

8. 배포가 성공적으로 완료되면 Blackjack-Part2 프로젝트 이름에서 마우스 오른쪽 클릭하고 URL을 복사합니다 

    <img src="images/3/image43.png" width="393" height="130" />


## DevCS에서 OACCS에 배포된 BlackJack 애플리케이션 테스트


로컬/원격서버에 배포된 후 기능을 테스트하기 위한 HTML-5 클라이언트 프로그램이 이미 BlackJack 애플리케이션과 함께 제공되었습니다. 

아래 지시사항에 따라 BlackJack 애플리케이션을 테스트하십시오. 

1. 윈도우 파일탐색기를 열고 **cloud > BlackJack > html5-client** 디렉토리로 이동하십시오. 

2. 브라우저로 index.html 파일을 엽니다. 

3. 첫번째 필드인 **Service** 에 이전 Lab에서 복사한 URL - <https://blackjack-part2-ouopc084.apaas.em2.oraclecloud.com/> - 이 입력되어 있는지 확인하고, 두번째 필드에서 1 과 9 사이의 숫자를 입력한 다음 연결을 클릭하십시오. 

    <img src="images/3/image44.png" width="513" height="230" />


4. 게이밍 콘솔에 연결되면 **Debug on/off** 버튼을 클릭하여 디버그 콘솔을 표시합니다. 

    <img src="images/3/image45.png" width="513" height="247" />


**참고 :** UI에서 사용 가능한 **Hit** 및 **Stand** 버튼을 사용하여 게임을 플레이할 수 있습니다. 

이 HTML5 클라이언트 프로그램은 클라우드의 OACCS에 배포된 BlackJack 게임 애플리케이션과 상호 작용합니다.
