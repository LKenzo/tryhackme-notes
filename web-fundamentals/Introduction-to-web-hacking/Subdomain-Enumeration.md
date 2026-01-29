# Subdomain Enumeration

## Task 1: 
Subdomain enumeration adalah sebuah proses untuk menemukan subdomain valid untuks sebuah domain. Bertujuan untuk memperbesar area penyerangan yang dapat dilakukan (attack surface). Beberapa subdomain enumeration methods: Brute Force, OSINT, dan Virtual Host.

1. Brute Force
2. OSINT
3. Virtual Host

## Task 2: (OSINT)
SSL/TLS yang dibuat oleh CA untuk sebuah domain akan mengambil bagian dari CT logs. CT logs ini dapat dimanfaatkan untuk mencari subdomain yang dimiliki oleh sebuah domain. Site https://crt.sh memberikan layanan searchable database of certificates. 
1. 	store.tryhackme.com

## Task 3:
Kita bisa memanfaatkan advanced search methods untuk mencari subdomain yang dimiliki oleh domain. Gunakan `site:*.tryhackme.com -site:www.tryhackme.com`, bagian site pertama untuk tujuan pencarian kita simbol `*` sebagai wild card bagian depan dan `.tryhackme.com` sebagai follow up wajibnya.
1. store.tryhackme.com

## Task 4: (Bruteforce)
Bruteforce DNS enumeration adalah metode yang mencari puluhan hingga jutaan posbilitas subdomains yang berbeda. Menggunakan tool yang dapat mengautomasinkan ini dapat sangat mempercepat pekerjaan. Task ini menggunakan tool dnsrecon `dnsrecon -t brt -d acmeitsupport.thm`.
1. api.acmeitsupport.thm

## Task 5: (OSINT)
Guankan tool seperti Sublist3r untuk mempercepat OSINT subdomain discovery. `./sublist3r.py -d acmeitsupport.thm`
1. web55.acmeitsupport.thm

## Task 6: 
Subdomains tidak selalu dihost di public accessible DNS results, bisa saja disimpan dalam private DNS Server yang dimana tidak akan muncul pada DNS results biasa. Kita dapat mengganti host header dan memonitor response yang dikirim oleh server untuk melihat website yang baru ditemukan. Mirip dengan DNS Bruteforce, kita dapat mengguankan wordliss untuk menemukan commonly used subdomains. 
`ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.48.181.114 -fs {size}`

-fs berfungsi untuk mengfilter output berdasarkan  size result, dapat dicari berdasarkan size value yang paling sering muncul berdasarkan hasil value
`ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.48.181.114`
