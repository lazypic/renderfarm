# Renderfarm

- Lazypic 렌더팜 규칙을 설명한 페이지 입니다.
- 일반적으로 `로컬렌더링 > Sheepit렌더링` 형태로 진행합니다.
- 필요시 지원사업, 유료 클라우드팜을 사용하여 파이널 렌더링을 진행합니다.

#### 규 칙
- 모든 렌더 파일은 하나의 .blend 파일로 Archive 저장합니다.
- .blend 파일 내부 모든 경로는 상대경로(Relative)로 셋팅합니다.
- 두 조건만 잘 지켜도 어떤 OS에서라도 큰 셋팅없이 간단하게 렌더링을 지원받을 수 있습니다.

#### Sheep It 렌더링 방법
- blender 파일하나에 모든 파일을 아카이브합니다.
	- File > External Data > Make All Paths Relative 선택
	- File > External Data > Pack All Into .blend 선택
	- 아웃풋 경로도 relative 경로로 셋팅합니다.
	- 아웃풋 이미지는 jpg, png만 지원합니다.(테스트 렌더링시만 사용)
	- 이제 파일을 저장하면, 블렌더파일에 텍스처 및 필요한 파일이 포함되었습니다.
- https://www.sheepit-renderfarm.com/jobs.php?mode=add 에 위 파일을 업로드합니다.
- .blend 파일은 단일파일로 최대 500메가까지 올릴 수 있습니다.
- 만약 한프레임에 30분이상 렌더링이 지속된다면 Estimator를 작성해서 Sheep it에 정보를 제공해주세요.
- Lazypic 팀페이지 : https://www.sheepit-renderfarm.com/team.php?id=34

#### Sheep It 렌더클라언트 실행
- 자신의 컴퓨터를 렌더팜으로 만드는 방법입니다.
- 렌더 클라이언트를 켜면, 자신의 프로젝트는 항상 먼저 렌더링됩니다.
- 또한 Point가 쌓이며, 이 Point로 렌더 우선순위가 올라갑니다.
- 아래 부터는 Sheep it 렌더클라이언트를 설치하고 실행하는 방법을 설명합니다.
- Sheep it 클라이언트를 다운로드합니다.
	- https://www.sheepit-renderfarm.com/getstarted.php
- macOS에 java JRE가 설치되어있어야 합니다.
	- 설치되어있지 않다면 아래 URL에서 다운로드 및 설치를 진행합니다.
	- https://java.com/en/download/mac_download.jsp
- 터미널에서 렌더클라이언트를 실행방법은 아래와 같습니다.
```
$ java -jar sheepit-client-5.620.2885.jar
```

- 만약 GUI를 켜지않고 터미널에서만 실행하고 싶다면 아래처럼 입력합니다.
```
$ java -jar sheepit-client-5.620.2885.jar -ui oneLine -login {ID} -password {PASSWORD}
```
- oneLine모드에서는 아래 명령어를 사용할 수 있습니다.
	- status: display client status
	- priority <n>: set the priority for the next renderjob
	- block:  block project
	- pause:  pause client requesting new jobs
	- resume: resume after client was paused
	- stop:   exit after frame was finished
	- cancel: cancel exit
	- quit:   exit now

#### Lazypic에 Point 생성을 도와주고 싶다면..
- 아래처럼 터미널에서 실행하면 Lazypic에 렌더포인트를 쌓을 수 있습니다.
- Sheep it 에서 public Key를 발급하여 lazypic 계정에서 password로 사용합니다.
```
$ wget https://www.sheepit-renderfarm.com/media/applet/sheepit-client-5.620.2885.jar
$ java -jar ./sheepit-client-5.620.2885.jar -ui oneLine -login lazypic -password A0h4AqtgAzROfnXVkHYl6tIz7mI0DqpC1tglpt8M
```

#### Opendata
- 아래 사이트에 접속하시면 여러분의 컴퓨터를 벤치마킹할 수 있습니다.
- https://opendata.blender.org
