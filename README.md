# 과제
+ top, ps, jobs, kill 명령어에 대해서 조사

## top
+ 'top'은 리눅스 운영 체제에서 사용되는 인터랙티브한 프로세스 모니터링 도구다.
   top은 시스템의 리소스 사용률, 프로세스 목록, 메모리 사용량, CPU 사용량 등을 실시간으로 모니터링할 수 있다. 

+ top 명령어의 주요 기능과 사용법
1. top 실행:
  'top'을 실행하기 위해 터미널 또는 콘솔 창에서 'top'을 입력하고 엔터키를 누릅니다. top은 기본적으로 현재 시스템의 상태를 모니터링하는 뷰를 제공합니다.
  
2. 화면 레이아웃:
   top을 실행하면 화면에는 다음과 같은 정보가 표시됩니다:
   + 현재 시간: 상단 중앙에 시간 정보가 표시됩니다.
   + 전체 실행 시간: 상단 오른쪽에 시스템의 전체 실행 시간이 표시됩니다.
   + 로드 에버리지: 상단 오른쪽에 시스템의 로드 에버리지(Load Average)가 표시됩니다.
   + 전체 프로세스 수: 상단 중앙에 전체 프로세스 수가 표시됩니다.
   + CPU 사용량: 상단 중앙에 CPU 사용량이 표시됩니다.
   + 메모리 사용량: 상단 중앙에 메모리 사용량이 표시됩니다.
   + 프로세스 목록: 화면의 중앙에 실행 중인 프로세스 목록이 표시됩니다.
   + 키 바인딩 정보: 화면 하단에 top에서 사용할 수 있는 키 바인딩 정보가 표시됩니다.

3. 화면 갱신:
   top은 기본적으로 1초마다 화면을 갱신하여 실시간 정보를 제공합니다.
   화면을 갱신하는 주기를 변경하려면 's' 키를 눌러 갱신 주기를 설정할 수 있습니다.

4. 프로세스 정렬:
   top은 기본적으로 CPU 사용량에 따라 프로세스를 정렬하여 표시합니다.
   정렬 기준을 변경하려면 'F' 키를 눌러 정렬 옵션을 선택할 수 있습니다.
   예를 들어, 'P'를 눌러 CPU 사용량에 따라 정렬하거나 'M'을 눌러 메모리 사용량에 따라 정렬할 수 있습니다.
   
5. 프로세스 제어:
   top에서 프로세스를 제어하기 위해 다음과 같은 키를 사용할 수 있습니다:
   + 'k': 프로세스를 종료(kill)합니다. 종료할 프로세스의 PID(Process ID)를 입력하고 엔터키를 누릅니다.
   + 'r': 프로세스의 우선 순위를 변경합니다. 우선 순위를 변경할 프로세스의 PID를 입력하고 엔터키를 누른 후 우선 순위 값을 입력하고 다시 엔터키를 누릅니다.

6. 종료:
   top을 종료하려면 'q' 키를 누르면 됩니다.

top은 다양한 옵션을 지원하므로 명령어에 대한 더 자세한 정보는 'man top' 명령어를 사용하여 매뉴얼 페이지를 확인할 수 있습니다.

+ top에 관한 코드 예시


## ps

## jobs

## kill
