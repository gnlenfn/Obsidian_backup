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
- 로그 수집이 왜 안돼요
	- 로그파일에 권한 644
	- conf.yaml dd-agent 644
	- `sudo datadog-agent status`
	- Status: Error: could not find any file matching pattern /home/dpm/logs/\*.log, check that all its subdirectories are executable
		- permission denied
- 메일 이외의 모니터 어떻게?
- NPM 어디에?
- synthetic test에서 주기적으로 테스트 가능한건지?