# Dockerfile :whale:
 RUN을 활용한 컨테이너 활용 및 이미지 배포  
## Dockerfile 작성법
 파일이름은 Dockerfile 파일 생성시 앞에는 무조건 대문자로 시작  
 확장명을 명시하지 않는다.

## Getting started
    1. git clone https://github.com/HyunSangWon/docker.git  
    2. cd docker/docker-file-practice02
    3. ls
    4. docker build -t sangwondocker/tomcat8 . (dockerfile 이미지로 빌드)  
    5. docker image ls (전체 이미지 확인)
    6. docker container run -it -d --name tomcatcontainer -p 80:8080 sangwondocker/tomcat8 (이미지를 백그라운드로 실행)  
    7. docker ps  or docker container ls (실행중인 도커컨테이너 확인)  
## 이미지 배포하기
    1. docker login  
    2. docker push sangwondocker/tomcat8  
## Dockerfile 문법
 FROM => 어떤 이미지 베이스인지  
 MAINTAINER => 이미지를 생성한 사람의 정보 (필수 아님)  
 ADD => 특정 경로에있는 파일을 도커 이미지에 추가  
 COPY => ADD와 같으나 차이점은 압축 파일을 추가할때 압출을 해체하지 않고, 파일 URL도 사용할 수 없음  
 WORKDIR => RUN, CMD and ENTRYPOINT에서 설정한 실행 파일이 실행될 디렉터리  
 RUN => FROM에서 설정한 이미지 위에서 스크립트 혹은 명령을 실행  
 CMD => CMD는 컨테이너가 시작되었을 때 스크립트 혹은 명령을 실행  
 EXPOSE => 포워딩할 포트번호 명시  
 
## 주의사항
 컨테이너는 대부분은 최소화를 중요시. 딱 필요한 것만 설치
 
