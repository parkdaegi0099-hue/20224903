# 20224903
open sw homework
# 리눅스 명령어 정리

--

| 명령어 | 기능 | 예시 |
|--------|------|------|
| top    | 실시간 프로세스 확인 | top |
| ps     | 프로세스 목록 출력 | ps aux |
| jobs   | 백그라운드 작업 확인 | jobs |
| kill   | 프로세스 종료 | kill -9 PID |

##  top
### 시스템의 실시간 프로세스 상태를 보여줌
### CPU, 메모리 사용량 확인 가능
### `top`으로 프로세스 상태 확인 결과 
- 시스템 업타임: up 9 min → 컨테이너가 실행된 지 9분 경과
- 로드 평균: 0.00, 0.03, 0.02 → CPU 부하가 거의 없음
- Tasks: 총 2개 프로세스 (1 running, 1 sleeping)
- CPU 사용률: 99.4 id → CPU 대부분이 유휴 상태
- 메모리: 총 7832MB 중 4585MB 사용 가능, 680MB 사용 중
- Swap: 2048MB 전부 사용 가능, 현재 사용 없음
- 프로세스 목록:
- PID 1 → bash (쉘 프로세스)
- PID 265 → top (지금 실행한 명령어 자체)
<img width="1004" height="218" alt="image" src="https://github.com/user-attachments/assets/7e4b9421-518d-48d4-bc72-1fca88e81a72" />



##  ps
### 현재 실행 중인 프로세스 목록 출력
### `ps aux`로 전체 프로세스 확인
- 사용자: root
- 총 프로세스: 2개
- 주요 프로세스:
- PID 1 → bash (쉘 프로세스)
- PID 9 → ps aux (현재 명령어)
- CPU/메모리 사용량: 매우 낮음
<img width="895" height="90" alt="image" src="https://github.com/user-attachments/assets/528e825b-8a78-4bfb-afdf-4394c664c728" />



##  jobs
### apt update && apt install procps 를 통해 업데이트 실행
### 백그라운드 작업 목록 확인
- `sleep 100 &` 로 백그라운드 프로그램 실행 
- `jobs`로 현재 쉘에서 실행 중인 작업 확인
- 백그라운드 작업 수: 2개
- 작업 번호: [1], [2]
- 명령어: sleep 100
- 상태: Running (실행 중)
<img width="543" height="148" alt="image" src="https://github.com/user-attachments/assets/54c6690d-276c-4fde-a7bd-d74da5c841c1" />



##  kill
### 프로세스를 종료시킬 때 사용
### `kill -9 [PID]`로 강제 종료 가능
### `sleep 100 &`의 백그라운드 프로그램을 kill 명령어로 강제종료 
- 종료 대상: sleep 100 (PID 262)
- 종료 명령: kill -9 262
- 결과: 프로세스 종료 확인, jobs 목록에서 사라짐
<img width="963" height="304" alt="image" src="https://github.com/user-attachments/assets/69890867-8738-46bf-937f-535beb9c275a" />


