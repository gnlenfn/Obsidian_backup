- Proxy 설정?
  ![](https://i.imgur.com/2RUM5F3.png)


[2023-12-04-월요일 오전 10:56] 박수현 책임 인공지능기술팀:  
1. APM이 잘 동작하나  
2. NPM으로 네트워크 트레픽이 잘 보이나  
네트워크 트래픽은 H/U에서 음원이 올라올텐데  
그 간격이라던지 이런게 보이는지에요  
전송되는 data들의 latency?  

3. Synthetic Monitor를 통해서  
주기적으로 테스트를 할수 있을까  
자동테스트하면서 에러case를 noti해주면 좋을 것 같아요


- 모든 서비스 `ddtrace-run` 해야지 종합적으로 볼 수 있는건가?
- ***메일 이외의 모니터 어떻게?***
	- monitor 설정법?
	- threshold 등 뭐여
- ***NPM 어디에?***
	- Agent 여러개 해야 의미있는거지?
- ***로그 pipeline에서 파싱 가능한건지(logstash, promtail...) -> extract content***
	- 정해진 포맷으로 로그 남기면 자동으로 되는건지?
	- 로그 content의 내용으로 검색이 되는건지? query?
- synthetic test에서 주기적으로 테스트 가능한건지?
	- host 단순 방화벽 오픈으로 안되고 domain 혹은 공인IP 써야하는건지?
	- ***내부망에서 테스트하고 해당 내용만 agent로 스크랩 가능?***
- ***watchdog은 뭐야?***
- ***proxy 설정 -> agent 설정파일만 만져도 되는걸로 보이는데?***
- ***query 어디서 찾아볼 수 있어?***


### proxy 연결 확인
`curl -x 10.11.52.140:3128 -L -I https://datadoghq.com`
