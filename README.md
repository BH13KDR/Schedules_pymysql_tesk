# Schedule Manager (Python + PyMySQL)

간단한 콘솔 기반 일정 관리 프로그램입니다.  
Python과 MySQL을 사용하여 일정을 추가, 조회, 완료 처리할 수 있습니다.

---

## 기능
- 일정 추가 (제목, 설명, 시작/종료 시간)
- 일정 조회 (완료/미완료 상태 표시)
- 일정 완료 처리 (ID 기준)
- 프로그램 종료

---

## 설치 & 실행

### 1. 레포지토리 클론
```bash
git clone https://github.com/BH13KDR/Schedules_pymysql_tesk.git
cd Schedules_pymysql_tesk
2. 가상환경 생성 및 PyMySQL 설치
bash
코드 복사
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate

pip install pymysql
3. MySQL DB 준비
sql
코드 복사
CREATE DATABASE schedule_db;

USE schedule_db;

CREATE TABLE schedules (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(200) NOT NULL,
    description TEXT,
    start_datetime DATETIME NOT NULL,
    end_datetime DATETIME,
    is_completed BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
4. 프로그램 실행
bash
코드 복사
python schedule_manager.py
사용 시 주의
시간 입력 형식: yyyymmddhhmmss

MySQL 접속 정보(host, port, user, password)는 코드 내 get_db_connection 함수에서 수정 가능
