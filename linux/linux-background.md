# linux background 실행시키기
```
$ ./test.c &
이렇게 치면 background로 실행되서 어떤 파일을 실행하고 있을 때 다른 명령어를 사용 가능함
```

### 백그라운드에 실행되고 있는 프로세스 확인
```
$ ps        // bg에 실행되고 있는 프로세스 보여줌
$ ps -e     // bg말고 모든 프로세스를 보여줌
$ ps -ef    // 풀리스트로 다 보여줌
```

### 사용 예시
백그라운드에 실행되고 있는 파이썬 파일을 찾아서 멈추게 하고 싶을 때
```
$ ps -ef | grep python

$ kill -9 id( 아까 해서 찾은 프로세스의 아이디 )
```
