# IV 부 : Oracle Application Container Cloud에 BlackJack WebService 애플리케이션 직접 배포


## Oracle Application Container 클라우드 서비스(이하 OACCS) 활성화


**중요:** 클라우드 로그인 자격증명(credentials) 및 링크(links)는 Lab을 수행함에 있어 반드시 필요합니다. 오라클로부터 받은 이메일에서 확인하실 수 있습니다.

이 문서의 설명에는 EMEA에 있는 오라클 클라우드 서비스 인스턴스를 이용하였으며, 여러분은 실습환경에 주어진 데이터 센터를 선택하십시오. 

Oracle Application Container Cloud Service는 Java Platform, Standard Edition (Java SE) 및 Node.js 애플리케이션을 배포 및 실행할 수 있습니다. 이 Lab에서는 이전 Lab에서 생성한 애플리케이션 아카이브 파일들을 사용하여 ACCS에 BlackJack 애플리케이션을 배포하는 방법을 배우게 됩니다. 

아래 지침에 따라 BlackJack 애플리케이션을 웹 사용자 인터페이스(Web UI)를 이용해서 ACCS에 배포하십시오. 

1. Oracle Cloud 계정에 로그인하십시오 (로그인 방법에 대한 자세한 내용은 **개발자 클라우드 서비스 활성화** 참조) 

2. 로그인이 성공하면 시작 페이지에서 **ID 도메인 이름** 및 **사용자 이름** 을 볼 수 있습니다. 

    <img src="images/4/image1.png" width="360" height="145" />


3. 사용자 계정에 할당되어 사용할 수 있는 오라클 클라우드 서비스가 대시보드에 표시됩니다.**Application Container** 서비스가 대시보드에서 보이지 않으면 **Custom Dashboard** 를 클릭하고 **Show**를 클릭해서 대시보드에 표시되도록 합니다.

    <img src="images/4/image2.png" width="360" height="174" />


4. 대시보드에서 **Application Container** 를 클릭하여 **Service Details : Oracle Application Container Cloud** 페이지로 이동하십시오. 

    <img src="images/4/image3.png" width="324" height="111" />


## OACCS에 BlackJack 애플리케이션 직접 배포


이 Activity에서는 애플리케이션 아카이브를 ACCS에 직접 배포하는 방법을 배우게 됩니다. 이 배포에도 동일한 샘플 애플리케이션인 BlackJack을 사용합니다.

아래 지시사항에 따라 BlackJack 애플리케이션을 OACCS에 직접 배포하십시오. 

1. **서비스 콘솔 열기** 버튼을 클릭하십시오. 

    <img src="images/4/image4.png" width="385" height="148" />


2. **애플리케이션 만들기** 및 **Java SE** 버튼을 클릭하십시오.

    <img src="images/4/image5.png" width="261" height="170" />


3. **애플리케이션 만들기** 다이얼로그 박스에서 애플리케이션 이름으로 BlackJack-part3을 입력하고 Subscription 유형으로 **Monthly**을 선택하고 메모 필드에 **Deploying BlackJack Application to ACCS directly**이라고 입력하십시오. 애플리케이션 아카이브 필드에서 **아카이브 업로드**를 선택하십시오. 

    <img src="images/4/image6.png" width="248" height="291" />


4. **target** 디렉토리에서 **blackjack-part2-1.0-dist.zip** 파일을 찾아서 선택하십시오. 

    <img src="images/4/image7.png" width="366" height="221" />


5. **애플리케이션 만들기** 다이얼로그 박스에 선택한 파일이 표시됩니다. **인스턴스**에서 인스턴스 수와 메모리 크기를 검토하고 필요한 항목을 수정하십시오. **생성**을 클릭하여 애플리케이션을 Oracle Application Container Cloud에 배포하십시오. 

    <img src="images/4/image8.png" width="225" height="263" />


6. **Processing Archive**임을 나타내는 상태 메시지가 나타납니다.

    <img src="images/4/image9.png" width="295" height="207" />


7. 아카이브된 애플리케이션이 업로드되면 서비스는 아카이브가 적절하게 구성되었는지 확인합니다. 이상이 없으면 아래와 같은 대화 상자가 나타납니다. **확인**을 클릭하십시오. 

    <img src="images/4/image10.png" width="270" height="125" />


8. 애플리케이션을 배포하는 데 몇 분이 걸립니다. 진행 상태는 진행중인 활동 섹션에서 볼 수 있습니다. 

    <img src="images/4/image11.png" width="348" height="228" />


9. 애플리케이션이 성공적으로 배포되면 활동 섹션에 **Status : Succeeded** 메시지가 표시됩니다. 

    <img src="images/4/image12.png" width="480" height="112" />


10. 애플리케이션 URL을 복사하여 메모장에 붙여 넣습니다. 테스트 목적으로 이 URL이 필요합니다. 

    <img src="images/4/image13.png" width="486" height="147" />


## OACCS에 배포된 BlackJack 애플리케이션 테스트


로컬/원격 서버에 배포 된 기능을 테스트하기 위한 HTML-5 클라이언트 프로그램이 BlackJack 애플리케이션과 함께 제공되었습니다.  

아래 지시사항에 따라 BlackJack 애플리케이션을 테스트하십시오. 

1. 윈도우 파일탐색기를 열고 **cloud > BlackJack > html5-client** 디렉토리로 이동하십시오. 

2. 브라우저로 index.html 파일을 엽니다. 

3. 첫 번째 필드인 **서비스** 에 이전 Lab에서 복사한 URL인 <https://blackjack-part3-ouopc084.apaas.em2.oraclecloud.com/>를 넣으십시오.
두 번째 필드에 1에서 9 사이의 숫자를 입력한 다음 연결을 클릭하십시오. 

    <img src="images/4/image14.png" width="520" height="141" />


4. 게이밍 콘솔에 연결되면 **디버그 켜기/끄기** 버튼을 클릭하여 디버그 콘솔을 표시합니다. 

    <img src="images/4/image15.png" width="513" height="247" />


**참고:** UI에서 사용 가능한 **Hit** 및 **Stand** 버튼을 사용하여 게임을 할 수 있습니다. 

이 HTML5 클라이언트 프로그램은 클라우드의 OACCS에 배포된 BlackJack 게임 애플리케이션과 상호 작용합니다. 

이를 통해 사용자 인터페이스 및 테스트를 사용하여 ACCS에 BlackJack 애플리케이션을 직접 배포하는 작업을 성공적으로 마쳤습니다.
