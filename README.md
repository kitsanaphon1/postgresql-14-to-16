คู่มือการติดตั้งและอัปเกรด PostgreSQL
1. การติดตั้ง PostgreSQL 14
1.1. อัปเดตแพ็กเกจ


sudo apt update
1.2. ติดตั้ง PostgreSQL 14


sudo apt install postgresql-14
1.3. ตรวจสอบการติดตั้ง


psql --version
1.4. เริ่มบริการ PostgreSQL


sudo systemctl start postgresql
1.5. ตั้งค่าให้เริ่มอัตโนมัติ


sudo systemctl enable postgresql
2. การสร้าง Database
2.1. เข้าสู่ PostgreSQL

bash

sudo -i -u postgres
psql
2.2. สร้าง Database

sql

CREATE DATABASE your_database_name;
2.3. ตรวจสอบ Database

sql

\l
2.4. เชื่อมต่อกับ Database

sql

\c your_database_name;
3. การอัปเกรดเป็น PostgreSQL 16
3.1. หยุดบริการ PostgreSQL


sudo systemctl stop postgresql
3.2. เพิ่ม Repository สำหรับ PostgreSQL 16


sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
3.3. อัปเดตแพ็กเกจ


sudo apt update
3.4. ติดตั้ง PostgreSQL 16


sudo apt install postgresql-16
3.5. ลบ Cluster 16 ถ้าจำเป็น


sudo pg_dropcluster 16 main
3.6. อัปเกรด Cluster 14


sudo -u postgres pg_upgradecluster 14 main
3.7. เริ่มบริการ PostgreSQL 16


sudo systemctl start postgresql
3.8. ตรวจสอบ Cluster


pg_lsclusters
สรุป
ตอนนี้คุณได้ติดตั้งและอัปเกรด PostgreSQL เป็นเวอร์ชัน 16 เรียบร้อยแล้ว! หากมีคำถามหรือปัญหาเพิ่มเติม สามารถสอบถามได้เลย!
