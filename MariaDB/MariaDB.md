*이 문서는 'K-digital IoT 프로젝트' 수업을 통해 배운 내용을 적어 놓은 복습용 파일 입니다. 따라서 순서나 주제에서 살짝 벗어난 내용이 있을 수 있습니다.*

# MariaDB 

### MariaDB란?

MariaDB사가 제작한 오픈소스 RDBMS(Relationship data base management system) 소프트웨어이다.

>  *오라클 회사가 MySQL사를 인수하면서 사용료를 내도록 바꿔, 오라클 정책에 반발한 핵심 연구원이 만든 MySQL 코드 기반 오픈소스 RDBMS 입니다.*

### SQL이란?

SQL은 Structured Query Language 로, RDBMS에서 정형화된 자료를 관리 및 처리하기 위해 설계된 언어이다.

##### SQL 언어적 특성

1.  SQL은 대소문자를 가리지 않는다.

   > *서버 환경이나 DBMS 종류에 따라 구분할 때도 있습니다.*

2. 명령어가 끝날 때 반드시 세미콜론(;)으로 끝나야 한다.

3. 주석 한 줄은 '--', 블럭은 '/* */' 으로 감싸준다.

   > *주석 단축키를 바꿔주고 싶다면, heidi-> 도구-> 환경설정-> 단축기-> sql에서 ctrl+/로 설정 가능*

4.  데이터의 고유 값은 따옴표로 감싸준다.

   ```
   SELECT * FROM (TABLE NAME) WHERE NAME='Minji';
   ```

5. SQL 객체는 백틱(``)으로 감싸준다.

   ```
   SELECT `NAME`, `TYPE` FROM ~;
   ```

   

### MariaDB 설치

- https://mariadb.org/ 접속 후 Download (자동으로 윈도우 정보를 불러와 적정 버전 알려줌)
  - 설치할 때 Root 비밀번호 잊지 않도록 주의! MariaDB 사용하는 동안 계속 기억하고 있어야 함
  - 문자셋 : UTF-8 선택 (한글 데이터도 불러올 것이므로)
  - 나머지는 디폴트로 설치!

  > *HeidiSQL 은 MariaDB의 Gui 프로세스이다.*

### 데이터 구축 

> *데이터를 구축하기 위해서 공부에 사용한 교재의 샘플 데이터베이스를 사용하였습니다.*

1. 데이터 'employees'를 c:\temp_v2\employees 에 다운로드한다.

   > *주소는 맘대로! 그러나, 사용할 주소가 길면 명령어 입력하기 귀찮아 진다.*

2. 시작 ->  MariaDB -> Command Prompt

   > *그냥 탐색기에 cmd에서 하면 안되는 이유는 MariaDB 내장 데이타가 없기 때문이다.*

3. cd 명령어로 다운받은 데이터가 있는 곳으로 워크 디렉토리 이동

   ```
   > cd \employees
   ```

4. Maria DB에 접속한다

   ```
   > mysql -u root -p
   Enter password : ****
   ...
   ...
   ...
   MariaDB[(none)] >
   ```

   > *이 때 앞서 다운로드 하면서 설정한 root 비밀번호가 항상 필요하다.*

5. employees.sql 데이터를 MariaDB에 다운로드 한다.

   ```
   MariaDB[(none)] > source employees.sql
   ...
   ...
   MariaDB[employees] > 
   ```

6.  해당 파일의 데이터베이스를 확인한다.

   ```
   MariaDB [employees]> show databases;
   ```

   