# ubuntu server 20.04 di oracle virtualbox 6.1.10
pertama klik new pada virtualbox untuk virtual machine
selanjutnya mengisi nama virtual machine dan memilih ubuntu 64 bit
lalu klik selesai
setelah itu klik kanan pada machine yang sudah dibuat, klik setting
system -> processor -> naikan menjadi 4 cores
strorage -> controller IDE -> empty -> logo CD -> choose file from disk
network -> bridge adapter
klik OK
start machine

## setting installation ubuntu server
pilih bahasa english
update to the new installer
keyboard configuration -> english (US) -> done
network -> done
proxy -> done
archive mirror -> done
storage configuration -> done -> continue
profile setup -> name -> server name (dibedakan dari name) -> ussername -> password
SSH setup -> ceklist (enter) -> done
featured server snap -> done
waiting installation -> reboot
login

## setting dasar ubuntu server
sudo apt update
sudo apt install net-tools 

Server kosong sudah jadi

## cloning server
klik kanan pada virtual machine -> clone -> generate new mac address -> ok
