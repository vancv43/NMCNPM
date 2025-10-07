# 🛠️ Software Engineering Project – [Tên dự án]

## 📌 Giới thiệu
Dự án này được phát triển trong môn **Nhập môn Công nghệ Phần mềm**.  
Mục tiêu là áp dụng quy trình phát triển phần mềm, từ **phân tích yêu cầu, thiết kế, lập trình, kiểm thử và triển khai**.  

## 👥 Thành viên nhóm
- Họ tên 1 – Vai trò (Leader, Developer, Tester, …)
- Họ tên 2 – Vai trò
- Họ tên 3 – Vai trò
- Họ tên 4 – Vai trò  

## 🎯 Use Case chính
- Quản lý người dùng
- Quản lý sản phẩm/dịch vụ
- Xử lý giao dịch
- Báo cáo & thống kê  

(Sơ đồ use case có thể chèn hình ảnh vào đây)

## 📐 Thiết kế hệ thống
- **Use Case Diagram**: ![Use Case](./docs/usecase.png)
- **Sequence Diagram**: ![Sequence](./docs/sequence.png)
- **ERD (Entity Relationship Diagram)**: ![ERD](./docs/erd.png)

## 💻 Công nghệ sử dụng
- Ngôn ngữ: Java / Python / JavaScript / PHP
- IDE: Visual Studio Code
- CSDL: MySQL / PostgreSQL
- Quản lý phiên bản: Git + GitHub
- Mô hình phát triển: Agile – Scrum  

## 🚀 Cài đặt & chạy thử
1. Clone repo:
   ```bash
   git clone https://github.com/vancv43/[ten-repo].git
   cd [ten-repo]


Software Engineering Lab | Lecture – 01-05

Lab 01 – Thiết lập môi trường & Quản lý dự án trên GitHub
•	Mục tiêu: Sinh viên làm quen với GitHub, Git, và công cụ lập trình.
•	Nội dung:
o	Tạo tài khoản GitHub, tạo repository riêng cho môn học.
o	Cấu hình Git (clone, commit, push, pull).
o	Cập nhật profile cá nhân trên README.md.
o	Upload bài tập đơn giản: file text giới thiệu bản thân.
 
Lab 02 – Phân tích yêu cầu & Thiết kế Use Case
•	Mục tiêu: Sinh viên học cách mô tả yêu cầu hệ thống bằng UML.
•	Nội dung:
o	Chọn Mini Project (ví dụ: hệ thống quản lý đặt phòng khách sạn, hệ thống bán hàng online).
o	Vẽ Use Case Diagram mô tả chức năng chính và các tác nhân.
o	Viết Use Case Description cho ít nhất 2 chức năng quan trọng.
o	Upload bản vẽ (dạng ảnh hoặc file .drawio) lên GitHub.
 
Lab 03 – UML Thiết kế (Use case-UC, Sequence Diagram-SQ)
•	Mục tiêu: Sinh viên mô tả luồng tương tác chi tiết của hệ thống.
•	Nội dung:
o	Dựa trên  ATM Mini Project, vẽ  UC, SQ cho một quy trình nghiệp vụ.
o	Giải thích các đối tượng tham gia và thông điệp trao đổi.
o	Upload diagram lên GitHub cùng file mô tả.
 
Lab 04 – Coding giao diện đăng nhập (Form Login)
•	Mục tiêu: Sinh viên áp dụng kỹ năng lập trình front-end cơ bản.
•	Nội dung:
o	Dùng Visual Studio Code viết một form login bằng HTML, CSS, JavaScript.
o	Yêu cầu: có input Username/Password, nút Login, Cancel, Remember me.
o	Thực hiện kiểm tra dữ liệu nhập cơ bản bằng JavaScript.
o	Đưa source code lên GitHub và chạy demo.
 
Lab 05 – Tích hợp, quản lý & báo cáo
•	Mục tiêu: Hoàn thiện quy trình phần mềm từ thiết kế đến triển khai.
•	Nội dung:
o	Gom tất cả các artifacts (Use Case, Sequence, Form Login code).
o	Tạo Project Report (Markdown hoặc PDF) mô tả quy trình làm việc.
o	Hướng dẫn push code, update readme, tạo tag version v1.0.
o	Nộp link repo GitHub để giáo viên review.
Lab 06 – Thiết kế chi tiết lớp & kiến trúc ATM
Mục tiêu: từ Use Case và Sequence, sinh viên thiết kế Class Diagram và Package Diagram cho ATM.
Công cụ: PlantUML/draw.io, VS Code.
Các bước
1.	Thư mục: /labs/lab06-atm-class/.
2.	Tạo class-atm.puml:
@startuml
class ATM {
  - atmId : int
  - location : String
  - cashLevel : double
  + authenticate(card:Card, pin:String) : boolean
  + withdraw(card:Card, amount:double) : Transaction
  + deposit(card:Card, amount:double) : Transaction
  + transfer(from:Account, to:Account, amount:double) : Transaction
}

class Card {
  - cardNo : String
  - pinHash : String
  - status : String
}

class Account {
  - accountNo : String
  - balance : double
  + debit(amount:double)
  + credit(amount:double)
}

class Transaction {
  - txId : int
  - type : String
  - amount : double
  - time : DateTime
  - status : String
}

ATM --> Card
ATM --> Transaction
Card --> Account
Account --> Transaction
@enduml
3.	Vẽ package diagram: UI, Controller, BankService, Hardware.
4.	Export PNG, ghi chú.
Phải nộp: class-atm.puml/png, package-diagram.puml/png, notes.md.
Rubric (10đ): đủ lớp & quan hệ (5), thuộc tính/phương thức đúng (3), tài liệu & repo (2).
 
Lab 07 – Phát triển Module Rút tiền (Prototype Java/Python)
Mục tiêu: viết module code mô phỏng Withdraw trong ATM.
Công cụ: Java hoặc Python + MySQL connector.
Các bước
1.	Thư mục: /labs/lab07-withdraw-module/.
2.	Code Python (ví dụ):
import mysql.connector, hashlib

def verify_pin(card_no, pin):
    conn = mysql.connector.connect(user="root", password="123456", database="atm_demo")
    cur = conn.cursor()
    cur.execute("SELECT pin_hash FROM cards WHERE card_no=%s", (card_no,))
    row = cur.fetchone()
    conn.close()
    return row and row[0] == hashlib.sha256(pin.encode()).hexdigest()

def withdraw(card_no, amount):
    conn = mysql.connector.connect(user="root", password="123456", database="atm_demo")
    cur = conn.cursor()
    try:
        conn.start_transaction()
        cur.execute("SELECT account_id, balance FROM accounts JOIN cards USING(account_id) WHERE card_no=%s FOR UPDATE",(card_no,))
        account_id,balance = cur.fetchone()
        if balance < amount:
            raise Exception("Insufficient funds")
        cur.execute("UPDATE accounts SET balance=balance-%s WHERE account_id=%s",(amount,account_id))
        cur.execute("INSERT INTO transactions(account_id,card_no,atm_id,tx_type,amount,balance_after) VALUES(%s,%s,1,'WITHDRAW',%s,%s)",(account_id,card_no,amount,balance-amount))
        conn.commit()
        print("Withdraw success")
    except Exception as e:
        conn.rollback()
        print("Error:", e)
    finally:
        conn.close()
3.	Test rút tiền với card_no demo.
Phải nộp: mã nguồn, ảnh màn hình chạy.
Rubric (10đ): kết nối DB đúng (3), xử lý giao dịch (3), kiểm tra số dư (2), log transaction (2).
 
Lab 08 – Kiểm thử ATM (Unit test & Integration test)
Mục tiêu: thực hành Unit Test và Integration Test module ATM.
Công cụ: Python (pytest) hoặc Java (JUnit), Selenium (cho form Login).
Các bước
1.	Thư mục: /labs/lab08-testing/.
2.	Viết unit test cho hàm verify_pin và withdraw.
o	Test case: PIN đúng/sai, đủ tiền/không đủ tiền.
3.	Viết integration test với Form Login (Lab 04) bằng Selenium.
o	Test case: login thành công, login sai, empty input.
4.	Lưu test_withdraw.py, selenium_test_login.py.
5.	Chạy test → export report.
Phải nộp: source test + ảnh pass/fail.
Rubric (10đ): unit test đủ case (4), integration test form login (4), báo cáo (2).
 
Lab 09 – Quản lý dự án ATM trên Jira (Agile)
Mục tiêu: mô phỏng quản lý phát triển ATM system bằng Scrum.
Công cụ: Jira/ClickUp/Trello.
Các bước
1.	Tạo project “ATM System”.
2.	Tạo Epic: “ATM Basic Functions”.
3.	Tạo User Stories:
o	US1: Là khách hàng, tôi muốn rút tiền.
o	US2: Là khách hàng, tôi muốn kiểm tra số dư.
o	US3: Là khách hàng, tôi muốn chuyển khoản.
o	US4: Là kỹ thuật viên, tôi muốn bảo trì.
4.	Phân rã thành Tasks/Subtasks (ví dụ: thiết kế UI, viết code, test).
5.	Lập Sprint 1 (2 tuần): Rút tiền + Xem số dư.
6.	Giao việc → chụp màn hình: Backlog, Board, Burndown.
Phải nộp: file report (.pdf hoặc .md) với ảnh chụp Jira.
Rubric (10đ): backlog đầy đủ (3), sprint board (3), báo cáo sprint (2), evidence hình ảnh (2).
 
Lab 10 – Báo cáo tổng hợp & Demo cuối kỳ
Mục tiêu: tổng hợp tất cả lab trước thành Mini Project ATM.
Công cụ: GitHub, PowerPoint/Markdown.
Các bước
1.	Thư mục: /labs/lab10-final-demo/.
2.	Gom toàn bộ artifacts:
o	Use Case (Lab 02)
o	Sequence (Lab 03)
o	Class Diagram (Lab 06)
o	ERD + DB (Lab 05)
o	Form Login (Lab 04)
o	Withdraw module (Lab 07)
o	Test (Lab 08)
o	Jira report (Lab 09)
3.	Viết báo cáo final-report.md:
o	Giới thiệu ATM mini-project
o	Mô hình UML
o	Database & code minh hoạ
o	Kết quả test & sprint report
o	Kết luận & định hướng mở rộng
4.	Demo trên lớp: chạy form login → withdraw demo kết nối DB → trình bày Jira board.
Phải nộp: final-report.md, slide PPT (nếu có), link repo GitHub.
Rubric (10đ): tích hợp đầy đủ (4), chạy demo được (3), báo cáo & trình bày (3).

# NMCNPM01
