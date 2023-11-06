# TUGAS2-Kelompok10
## Hadoop Ecosystem
Ekosistem ini dibuat pada platform Cloudera yang dijalankan pada Virtual Box.
### Cara Kerja:
- Masuk ke SQL sebagai root
  ```
  mysql -u root -pcloudera
  ```
- Melihat dataase dan tabel yang ada di SQL
  ```
  show databases
  use retail_db
  show tables
  ```
- Melihat isi tabel
  ```
  select * from categories;
  ```
- Melakukan import tabel ke dalam Sqoop
  ```
  sqoop import --connect jdbc:mysql://localhost/retail_db --username=root --password=cloudera --table categories --target-dir /user/clodera/test_import -m 1
  ```
- Cek tabel berhasil di import
  ```
  hdfs dfs -ls -R /user/cloudera/test_import
  ```
- Import tabel ke Hive
  ```
  sqoop import --connect jdbc:mysql://localhost/retail_db --username=root --password=cloudera --table categories --hive-import --create-hive-table --hive-table mydb.newtable
  ```
- Masuk ke Hive
  ```
  Hive
  ```
- Cek data yang terdapat pada Hive
  ```
  show databases
  show tables
  ```
