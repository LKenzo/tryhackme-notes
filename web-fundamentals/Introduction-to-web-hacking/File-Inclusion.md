<img width="854" height="302" alt="image" src="https://github.com/user-attachments/assets/e1ba4b17-44cf-4d16-8b4e-9fe798f2821b" /># File Inclusion

## Task 1
Get Requests mengirimkan user input ke dalam search enginennya. https://www.google.com/search?q=TryHackMe. File inclusion ini terjadi saat PHP ditulis dan diimplementasikan seacara tidak benar. Inti dari masalahnya adalah _Input Validation_. Dari file inclusion ini, attacker dapat mengambil data, seperti code, credentials, atau bahkan RCE (Gain Remote Command Execution) apabila attacker sampai dapat menulis file.

## Task 3 (Path Traversal)
Directory traversal membuat attacker dapat membaca operating system resources. Path traversel vulnerabilities terjadi saat input user dikirim ke fungsi seperti file_get_contents dalam php [read more on that](https://www.php.net/manual/en/function.file-get-contents.php). 
<img width="1596" height="684" alt="image" src="https://github.com/user-attachments/assets/d9249058-917a-4817-82be-87652d243f90" />

Kita bisa mencoba megnecheck suatu URL paramater by adding payloads. Path traversal attack atau dot-dot-slash attack, mempergunakan fungsi jalan ke directory selanjutnya dengan menggunakan `../`, input ex. `http://webapp.thm/get.php?file=../../../../etc/passwd`

Common OS files to use while testing
<img width="892" height="799" alt="image" src="https://github.com/user-attachments/assets/69a80177-80f6-46f9-a579-413ac6b4db0b" />

## Task 4 (Local File Inclusion - LFI)
LFI attacks adalah penyerangan yang terjadi akibat kurangnya kewaspadaan developer terhadap keamanan. function php seperti **include, require, include_once dan require_once** sering berkontribusi ke vulneribilitas pada web. 
#1. Kiranya diberikan 2 opsi pilihan, EN dan AR
<img width="850" height="164" alt="image" src="https://github.com/user-attachments/assets/4a8fff01-f5ff-4660-a24a-84e60989719e" />
menggunakan GET requets via url param lang. Call ini dapat dilakukan dengan HTTP request seperti ini, `http://webapp.thm/index.php?lang=EN.php`, EN.php adalah file yang ada di directory.
Kita bisa gunakan request ini untuk mengambil file penting seperti /etc/passwd. `http://webapp.thm/get.php?file=/etc/passwd`.

#2. Directory spesifik dalam fungsinya.
<img width="840" height="131" alt="image" src="https://github.com/user-attachments/assets/e56a7ebb-72cc-403d-aaf9-e4550e173791" />
Kita bisa coba mencari file-file sensitive seperti /etc/passwd dengan cara mirip seperti path traversal. `http://webapp.thm/index.php?lang=../../../../etc/passwd`

1. /lab1.php?file=/etc/passwd
2. includes

## Task 5 (Lanjutan LFI)
#3. Kita bisa mendapatkan banyak hint dari error message misalnya seperti ini 
`Warning: include(languages/THM.php): failed to open stream: No such file or directory in /var/www/html/THM-4/index.php on line 12`
dari entry point ini :
`http://webapp.thm/index.php?lang=EN`
Kita bisa mendapatkan include function dan juga full web application directorynya `/var/www/html/THM-4/`. Untuk melakukan eksploitasinya, kita bisa melakukan directory traversing dengan `../`. `var/www/html/THM-4/` berfungsi sebagai tingkatan directory, karena kita mau mengambil file yang berada pada root folder maka kita bisa gunakan `../` sebanyak 4x `http://webapp.thm/index.php?lang=../../../../etc/passwd`. 

Tetapi mungkin saja masih gagal, dan mendapat error lagi
`Warning: include(languages/../../../../../etc/passwd.php): failed to open stream: No such file or directory in /var/www/html/THM-4/index.php on line 12`
Mengartikan developer secara default menaruh file type ke fungsinya (passwd.php). Kita dapat membypassnya dengan menggunakan NULL BYTE `%00`.
`include("languages/../../../../../etc/passwd%00").".php");` = `include("languages/../../../../../etc/passwd");`

#4. Developer melakukan filter keywords untuk mencegah kebocoran data sensitif. Terdapat 2 metode untuk membypass filternya. Pertama gunakan NullByte `%00` atau gunakan `/..` pada akhir dari current directory. 
`http//webapp.thm/index.php?lang=/etc/passwd/` atau `http://webapp.thm/index.php?lang=/etc/passwd%00`

`cd ..` akan membawa kita kembali ke  directory sebelumnya tetapi `cd .` akan berhenti di current directory.

#5. Developer menggunakan input validation dengan mengfilter beberapa keywords. `http://webapp.thm/index.php?lang=/etc/passwd%00` menghasilkan error 
`Warning: include(languages/etc/passwd): failed to open stream: No such file or directory in /var/www/html/THM-5/index.php on line 15`
Web app mengganti `../` menjadi sebuah empty string menghasilkan `languages/etc/passwd/`

Salah satu teknik untuk mengbypassnya adalah dengan menggunakan `....//` bukan `../`, jadinya `....//....//....//....//....//etc/passwd`. Bekerja dikarenakan php akan hany mengfilter yang sesuai saja.
<img width="854" height="302" alt="image" src="https://github.com/user-attachments/assets/08937012-dddd-4fb5-b798-01b7c769a30e" />

#6. Web application meminta untuk supply input yang harus mengirim directory seperti `http://webapp.thm/index.php?lang=languages/EN.php` maka, payloadnya menjadi seperti ini:
`?lang=languages/../../../../../etc/passwd`

1. /lab3.php?file=../../../../etc/passwd/ atau /lab3.php?file=../../../../etc/passwd%00
2. file_get_contents
3. THM-profile
4. 12.04 `THM-profile/../../../../etc/os-release`

BONUS (Lab #5):
Use `....//` so the payload will be `lab5.php?file=....//....//....//....//etc/passwd`

## Task 6 (Remote File Inclusion - RFI)
