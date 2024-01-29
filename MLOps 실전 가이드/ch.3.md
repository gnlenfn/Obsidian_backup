## VM vs Containr
둘의 가장 큰 차이는 어떤 컴포넌트가 격리되어 있는 지의 차이
![](https://i.imgur.com/Hh33QsW.png)
- 물리 장비(host)에 VM을 관리하는 하이퍼바이저 소프트웨어가 존재하고 하이퍼바이저가 완전히 독립된 VM을 생성. 따라서 자체 OS를 포함하기 때문에 더 독립적이지만 무겁다
- 특정 작업을 수행하는 단일 기능만 컨테이너에 포함시켜 가볍게 사용한다. VM에서는 VM내에 OS, 앱, DB 등을 모두 포함하게 되지만 컨테이너는 특정 앱만 포함하여 가볍게 사용
	- 마이크로서비스에서는 컨테이너 사용을 지향


## 컨테이너 런타임
가장 익숙하고 많이 쓰는 런타임은 도커가 있지만 `컨테이너 == 도커`라고 생각하면 안된다.
도커가 발전하면서 [containerd 런타임을 내부적으로 사용](https://gngsn.tistory.com/128)하게 되었으며 쿠버네티스에서는 CRI-O를 전용 런타임으로 사용한다.


## Docker로 컨테이너 생성하기
### Dockerfile
- 도커를 통해 컨테이너 생성을 위한 이미지를 만드는 스크립트
- Dockerfile을 작성한 뒤 `docker build` 명령어를 통해 이미지를 만들 수 있다
	- [Dockerfile 작성법](https://docs.docker.com/engine/reference/builder/)
- Dockerfile의 각 단계는 이미지의 레이어가 되기 때문에 더 가벼운 이미지를 만들기 위해서는 레이어를 줄이는 노력이 필요

### Docker Linter
`docker run --rm -i hadolint/hadolint < Dockerfile`
도커 파일을 작성한 후 린터를 사용해 더 나은 제안을 받을 수 있음