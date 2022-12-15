# for-pwnable
- [Dockerfile.u2204] dockerfile ubuntu 22.04
    - build & run
        ```
        > docker build -t pwn-u2204 -f Dockerfile.u2204 .
        > docker run -it pwn-u2204
        ```
    - 컨테이너 내부에서 path 설정
        ```
        > find / -name checksec 2>/dev/null -exec dirname {} \;
        /usr/local/lib/python3.10/dist-packages/bin
        > export PATH=/usr/local/lib/python3.10/dist-packages/bin:$PATH
        ```
    - 추가로 해야될 작업  
        - 컨테이너 내부에서 path 설정 자동화 (도커파일에 추가)
        - 공격 테스트 시 docker-compose 로 묶을 수 있도록 backround 로 돌려도 죽지 않게 entry point 설정  