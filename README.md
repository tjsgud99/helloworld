# 과제
+ top, ps, jobs, kill 명령어에 대해서 조사

## top
+ 'top'은 리눅스 운영 체제에서 사용되는 인터랙티브한 프로세스 모니터링 도구다.
+ top은 시스템의 리소스 사용률, 프로세스 목록, 메모리 사용량, CPU 사용량 등을 실시간으로 모니터링할 수 있다. 

#### top 명령어의 주요 기능과 사용법
1. top 실행
  + 'top'을 실행하기 위해 터미널 또는 콘솔 창에서 'top'을 입력하고 엔터키를 누릅니다. top은 기본적으로 현재 시스템의 상태를 모니터링하는 뷰를 제공합니다.
  
2. 화면 레이아웃
   top을 실행하면 화면에는 다음과 같은 정보가 표시됩니다
   + 현재 시간: 상단 중앙에 시간 정보가 표시됩니다.
   + 전체 실행 시간: 상단 오른쪽에 시스템의 전체 실행 시간이 표시됩니다.
   + 로드 에버리지: 상단 오른쪽에 시스템의 로드 에버리지(Load Average)가 표시됩니다.
   + 전체 프로세스 수: 상단 중앙에 전체 프로세스 수가 표시됩니다.
   + CPU 사용량: 상단 중앙에 CPU 사용량이 표시됩니다.
   + 메모리 사용량: 상단 중앙에 메모리 사용량이 표시됩니다.
   + 프로세스 목록: 화면의 중앙에 실행 중인 프로세스 목록이 표시됩니다.
   + 키 바인딩 정보: 화면 하단에 top에서 사용할 수 있는 키 바인딩 정보가 표시됩니다.

3. 화면 갱신
   + top은 기본적으로 1초마다 화면을 갱신하여 실시간 정보를 제공합니다.
   + 화면을 갱신하는 주기를 변경하려면 's' 키를 눌러 갱신 주기를 설정할 수 있습니다.

4. 프로세스 정렬
   + top은 기본적으로 CPU 사용량에 따라 프로세스를 정렬하여 표시합니다.
   + 정렬 기준을 변경하려면 'F' 키를 눌러 정렬 옵션을 선택할 수 있습니다.
   + 예를 들어, 'P'를 눌러 CPU 사용량에 따라 정렬하거나 'M'을 눌러 메모리 사용량에 따라 정렬할 수 있습니다.
   
5. 프로세스 제어
   + top에서 프로세스를 제어하기 위해 다음과 같은 키를 사용할 수 있습니다:
   + 'k': 프로세스를 종료(kill)합니다. 종료할 프로세스의 PID(Process ID)를 입력하고 엔터키를 누릅니다.
   + 'r': 프로세스의 우선 순위를 변경합니다. 우선 순위를 변경할 프로세스의 PID를 입력하고 엔터키를 누른 후 우선 순위 값을 입력하고 다시 엔터키를 누릅니다.

6. 종료
   + top을 종료하려면 'q' 키를 누르면 됩니다.


#### top에 관한 코드 예시
``` python
import subprocess

# top 명령어 실행
command = ['top', '-b', '-n', '1']  # '-b': 배치 모드, '-n': 실행 횟수
result = subprocess.run(command, capture_output=True, text=True)

# 결과 출력
print(result.stdout)

```
+ 위는 Python 코드를 사용하여 top 명령어의 결과를 가져오는 예시입니다.
+ 위의 예시에서 subprocess.run() 함수를 사용하여 top 명령어를 실행합니다.
+ 명령어와 옵션은 command 리스트에 저장되어 있습니다. 이 예시에서는 -b 옵션으로 배치 모드를 사용하고, -n 옵션으로 한 번만 실행하도록 설정했습니다.
+ subprocess.run() 함수의 capture_output=True는 명령어의 실행 결과를 캡처하도록 설정하고, text=True는 결과를 텍스트 형식으로 반환하도록 설정합니다.
+ 마지막으로, result.stdout을 출력하여 top 명령어의 결과를 터미널에 출력합니다.
+ 이 예시를 실행하면 top 명령어의 결과를 Python 코드에서 확인할 수 있습니다. 결과에는 현재 시스템의 상태, 프로세스 목록, CPU 사용량, 메모리 사용량 등이 포함될 것입니다.

## ps
+ 'ps'는 리눅스와 유닉스 기반 운영 체제에서 실행 중인 프로세스의 정보를 표시하는 명령어입니다. 
+  ps 명령어를 사용하면 현재 실행 중인 프로세스의 목록, 프로세스 ID (PID), CPU 및 메모리 사용량, 실행 시간 등 다양한 정보를 확인할 수 있습니다. 

#### ps 명령어의 주요 기능과 사용법
1. ps 실행
   + 'ps' 명령어를 터미널 또는 콘솔 창에서 실행하고 엔터키를 누릅니다. 기본적으로 ps는 현재 사용자에게 속한 프로세스 목록을 표시합니다.
   
2. 출력 형식
   + ps 명령어는 다양한 출력 형식을 지원합니다. 기본적으로 실행 중인 모든 프로세스를 표시하는 "ps aux" 형식이 자주 사용됩니다.
   + 여기서 "a"는 모든 사용자 프로세스를 표시하고, "u"는 상세 정보를 표시하며, "x"는 터미널에 연결되지 않은 프로세스를 표시합니다.
   + 예를 들어, "ps aux" 명령을 실행하면 PID, CPU 사용량, 메모리 사용량, 실행 시간 등이 포함된 프로세스 목록이 표시됩니다.
   
3. 정렬
   + ps 명령어는 프로세스 목록을 정렬하여 출력할 수 있습니다.
   + 가장 일반적인 정렬 옵션은 "-e" (PID 순), "-C" (명령어 이름 순), "-u" (사용자 이름 순) 등이 있습니다.
   + 예를 들어, "ps aux --sort=-%cpu" 명령을 실행하면 CPU 사용량을 기준으로 내림차순으로 프로세스를 정렬하여 표시합니다.
   
4. 필터링
   + ps 명령어는 특정 조건에 맞는 프로세스만 표시하기 위해 필터링할 수 있습니다.
   + 일반적인 필터링 옵션으로는 "-e" (모든 프로세스), "-u" (특정 사용자 프로세스), "-C" (특정 명령어로 시작하는 프로세스) 등이 있습니다.
   + 예를 들어, "ps aux --user=myuser" 명령을 실행하면 사용자 "myuser"에 속한 프로세스만 표시합니다.
   
5. 상세 정보
   + "ps aux" 형식을 사용하면 프로세스에 대한 상세 정보를 표시합니다.
   + 이 정보에는 사용자, CPU 사용량, 메모리 사용량, 시작 시간, 실행 시간, 명령어 등이 포함될 수 있습니다.
   + 출력되는 상세 정보는 출력 형식과 운영 체제에 따라 다를 수 있습니다.
   
#### ps 에 관한 코드 예시
``` python
import subprocess

# ps 명령어 실행
command = ['ps', 'aux']
result = subprocess.run(command, capture_output=True, text=True)

# 결과 출력
print(result.stdout)

```
+ 위의 예시에서 subprocess.run() 함수를 사용하여 ps 명령어를 실행합니다.
+ 명령어는 command 리스트에 저장되어 있으며, 'ps', 'aux'는 기본적인 형식으로 모든 사용자 프로세스에 대한 상세 정보를 표시합니다.
+ subprocess.run() 함수의 capture_output=True는 명령어의 실행 결과를 캡처하도록 설정하고, text=True는 결과를 텍스트 형식으로 반환하도록 설정합니다.
+ 마지막으로, result.stdout을 출력하여 ps 명령어의 결과를 터미널에 출력합니다.
+ 이 예시를 실행하면 ps 명령어의 결과를 Python 코드에서 확인할 수 있습니다. 결과에는 프로세스 ID (PID), 사용자, CPU 사용량, 메모리 사용량, 실행 시간, 명령어 등이 포함될 것입니다.

## jobs
+ jobs'는 리눅스 및 유닉스 기반 운영 체제에서 쉘(Job Control Shell)에서 실행 중인 작업(Job)의 목록을 표시하는 명령어입니다.
+ jobs 명령어를 사용하면 백그라운드(background) 또는 중지(stopped)된 작업들의 상태와 관련 정보를 확인할 수 있습니다

#### jobs 명령어의 주요 기능과 사용법
1. jobs 실행
   + 'jobs' 명령어를 터미널 또는 콘솔 창에서 실행하고 엔터키를 누릅니다.
   + jobs 명령어는 현재 실행 중인 쉘 세션에서 관리하는 작업 목록을 표시합니다.

2. 작업 목록
   jobs 명령어는 다음과 같은 정보를 포함하는 작업 목록을 표시합니다:
   + 작업 번호: 작업을 구별하기 위한 번호입니다.
   + 작업 상태: 작업이 백그라운드(background)에서 실행 중인지, 중지(stopped)된 상태인지를 나타냅니다.
   + 작업 ID: 작업의 고유 식별자인 작업 ID(Job ID)입니다.
   + 작업 명령어: 실행 중인 작업에 대한 명령어 또는 스크립트의 이름입니다.

3. 백그라운드 작업
   + jobs 명령어는 쉘에서 실행 중인 백그라운드 작업들의 상태를 표시합니다.
   + 백그라운드 작업은 쉘 세션에서 실행 중이지만 터미널에 표시되지 않는 작업입니다.
   + 보통 백그라운드 작업을 실행하기 위해 명령어 뒤에 '&'를 추가합니다.

4. 중지된 작업
   + jobs 명령어는 중지된 작업들의 상태를 표시합니다.
   + 중지된 작업은 실행 중인 작업을 중지하거나 Ctrl+Z 키를 사용하여 일시 중단한 작업입니다.
   + 중지된 작업은 다시 실행하거나 종료할 수 있습니다.

5. 작업 제어
   + jobs 명령어는 작업을 제어하기 위해 다음과 같은 명령어를 사용할 수 있습니다:
   + 'fg': 백그라운드나 중지된 작업을 다시 포그라운드(foreground)로 가져옵니다. 'fg' 뒤에 작업 번호나 작업 ID를 입력하여 특정 작업을 가져올 수 있습니다.
   + 'bg': 중지된 작업을 백그라운드로 이동시킵니다. 'bg' 뒤에 작업 번호나 작업 ID를 입력하여 특정 작업을 이동시킬 수 있습니다.
   + 'kill': 작업을 종료합니다. 'kill' 뒤에 작업 번호나 작업 ID를 입력하여 특정 작업을 종료할 수 있습니다.

## kill
+ kill'은 리눅스 및 유닉스 기반 운영 체제에서 프로세스를 종료하는 명령어입니다.
+ kill 명령어를 사용하여 특정 프로세스나 프로세스 그룹에 종료 신호를 보낼 수 있습니다.

####  kill 명령어의 주요 기능과 사용법
1. kill 명령어 사용 형식
  + kill 명령어는 다음과 같은 형식으로 사용됩니다
  ``` bash
  kill [옵션] [프로세스 ID 또는 신호]...
  ```
  
  
2. 프로세스 종료
  + kill 명령어를 사용하여 특정 프로세스를 종료할 수 있습니다.
  + 종료할 프로세스를 식별하기 위해 프로세스 ID(PID)를 사용합니다.
  + 예를 들어, PID가 1234인 프로세스를 종료하려면 다음과 같이 입력합니다
  ``` bash
  kill 1234
  ```
  
  
3. 신호 전송:
  + kill 명령어를 사용하여 특정 신호를 프로세스에 전송할 수도 있습니다.
  + 신호는 종료 시그널을 나타내며, 기본적으로 TERM (15번) 신호가 사용됩니다.
  + TERM 신호는 프로세스를 정상적으로 종료하는데 사용됩니다.
  + 다른 종류의 신호를 전송하려면 -s 옵션을 사용합니다.
  + 예를 들어, PID가 1234인 프로세스에 INT (2번) 신호를 전송하려면 다음과 같이 입력합니다
``` bash
kill -s INT 1234
```


4. 프로세스 그룹 종료:
  + kill 명령어를 사용하여 프로세스 그룹을 종료할 수도 있습니다.
  + 그룹 ID를 사용하여 프로세스 그룹을 식별하며, - 기호를 그룹 ID 앞에 붙입니다.
  + 예를 들어, 그룹 ID가 5678인 프로세스 그룹을 종료하려면 다음과 같이 입력합니다
  ``` bash
  kill -5678
  ```


5. 다양한 옵션:
kill 명령어에는 다양한 옵션을 사용할 수 있습니다. 자주 사용되는 옵션은 다음과 같습니다
+ -s, --signal: 특정 신호를 지정합니다.
+ -l, --list: 사용 가능한 신호 목록을 표시합니다.
+ -a, --all: 모든 프로세스에 신호를 전송합니다.
+ -u, --user: 특정 사용자의 프로세스에 신호를 전송합니다.

