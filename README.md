운영체제 - myshell 구현

- 이 과제는 linux에서 실행되는 자신의 shell을 간단한 형태로 구현합니다. 
- shell의 기본 동작은 강의자료를 참고하십시오.
- myshell은 다음과 같이 동작해야 합니다.
1. myshell을 실행시키면 다음 예와 같이 prompt를 표시합니다.
 (예) myshell > ls
2.prompt에 다음 예와 같이 명령을 입력합니다. (리눅스 상의 모든 실행 명령 입력 가능해야 함)
(예) myshell > ps | wc
- myshell은 입력된 명령 문자열을 구분(parsing)하여 fork / exec 시스템콜을 통해 입력된 명령을 실행함
- 이 때, execvp 시스템콜을 사용할 것 (이 시스템콜은 PATH 정보를 이용해 기존에 설치된 프로그램 들을 찾아 실행시켜줌)
- execvp에 전달하는 인자 예:
입력 명령문이 hello world일 경우, argv[0]="hello", argv[1]="world", argv[2]=0을 지정하고, execvp("hello", argv); 형식으로 exec을 실행해야 함.
