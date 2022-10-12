# __weak 명령어

## __weak 명령어란 무엇인가 ??
> ### c 컴파일 과정
> #### 전처리( *.i ) -> 컴파일( *.s ) -> 어셈블러( *.o ) -> 링커( 실행파일 )
> #### 이중에서 링커의 기준으로 보았을 때에는 심볼을 2가지로 분류가능함
> ##### - 정의 위치 : 현재파일 | 다른 파일에서 참조되는 전역 심볼 | 전역 변수 및 non-static 함수 (non-static 은 약간 전역 변수 함수 버전 같은 느낌)
> ##### - 정의 위치 : 다른파일 | 현재 파일에서 참조되는 전역 신볼 | extren 으로 정의된 함수 및 변수
> ##### - 정의 위치 : 현재파일 | 현재 파일에서 참조되는 전역 심볼 및 모든 전역 변수를 의미
> 이렇게 3개로 나눌 수 있음
> ### 이런 것들을 링커입장에서는 심볼 테이블로부터( 재배치 가능한 오브젝트 파일 ) 기본키 같이 하나만 존재하는 심볼의 정의를 참조함 그리고 심볼 참조를 해석함.<br>지역 심볼은 쉽게 해석됨 근데 전역 심볼은 조금 어려움ㅠ
> ### 컴파일러는 전역 심볼들을 strong 혹은 weak 한 상태로 만듬 , 함수들과 초기화 된 전역 변수들은 strong , 초기화 안된 변수는 weak 으로 만듬
> ### 그럼 링커는 strong 한거는 이미 초기화가 된거니까 안건듬
> ### 이름이 같은 2개의 심볼 함수가 weak 과 strong을 가지고 있다면 당연히 초기화 되어 있는 거를 선택함 명령어의 순위가 `strong > weak` 이렇게 됨
> ### weak 심볼들이 있으면 걍 아무거나 선택함

<a href="https://damduc.tistory.com/338">참고 사이트</a>