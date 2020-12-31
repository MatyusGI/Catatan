# Delete row

      delete from [nama tabel] where [nama coloumn] = [value];

# Drop / Delete Table

      drop table [nama tabel];
      
# Drop / Delete Database

      drop database [nama database];
      
# Melihat isi tabel

      select * from [nama tabel]; --> untuk melihat keseluruhan isi tabel
      select [nama coloumn] = [value] from [nama tabel]; --> untuk melihat isi tabel secara spesifik
      
# Melihat list tabel pada database

      show tables;
      
# Melihat deskripsi tabel

      describe [nama tabel];
      
# Memasuki / Menggunakan database

      use [nama database]
      
# Menambah database

      create database [nama database];
      
# Melihat list database

      show databases;
      
# Menambah / Mengisi data pada tabel

      insert into [nama tabel] ([nama coloumn], [nama coloumn]) values ([value pada coloumn], [value pada coloumn]);
      
# Mengubah isi data pada tabel

      update [nama tabel] set [nama coloumn] = '[value yang diganti]' where [nama coloumn] = '[value]';
      
# Membuat tabel pada database

      create table [nama tabel] ([deskipsi tabel seperti : id int primary key auto_increment ,  nama varchar(100), nrp varchar(10), email varchar(100), jurusan varchar(100), gambar varchar(100) ]);
      
# 
