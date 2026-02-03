# IDOR

## TASK 1
IDOR (Insecure Direct Object Reference) adalah sebuah access control vulnerability. Vulnerability ini terjadi saat web menerima sebuah user-supplied input untung mengambil sebuah object (file, data, document).
1. Insecure Direct Object Reference

## Task 2
Salah satu contoh IDOR pada website adalah saat kita mengganti value pada url dan dapat melihat data yang bukan milik kita.
ex.
(http://online-service.thm/profile?user_id=1035) -> (http://online-service.thm/profile?user_id=1000)
1. THM{IDOR-VULN-FOUND}

## Task 3
Encoding membuat pengiriman/pengambilan data seperti post data, cookies, query string lebih aman. Salah satu encoding type paling common dan paling mudah ditebak adalah base64
<img width="1314" height="103" alt="image" src="https://github.com/user-attachments/assets/6089f535-1d32-4e22-b31d-44406bfb1d04" />
1. Base64

## Task 4
Hashed ID adalah salah satu tipe ID yang disimpan dalam bentuk hashed. Dimana kita bisa menggunakan tools seperti hash cracker online yang sesuai atau JohnTheRipper.
1. MD5

## Task 5
1. 2

## Task 6
IDOR tidak selalu berada pada address bar. Aplikasi modern sering menyimpan object references di dalam API, AJAX Request atau Javascript file reference.

## Task 7
Pada task ini, kita diberikan salah satu contoh IDOR yang berada di dalam API request. Kita dapat mengganti parameter user_id=? pada GET request yang di mana request ini akan meminta ke server data-data user lain sesuai user_idnya.
1. adam84
2. j@fakemail.com

