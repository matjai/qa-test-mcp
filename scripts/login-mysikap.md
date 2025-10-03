
## Software QA Test

Goal: to be able to login to chatgu.mesiniaga.com.my and initiate simple chat.

view mode: desktop view

Pre-reqs: 

auth: get auth ID_Pengguna and Kata_Laluan from .env file

Steps:
1. go to https://public.jpj.gov.my/public/login.zul (hint: page loads successfully with title "Portal mySIKAP, Jabatan Pengangkutan Jalan Malaysia", RootWebArea uid=1_0 confirms successful load, login form panel displays with orange background containing all required fields)
2. on login form panel: Select Kategori ID = individu, ID Pengguna = auth.ID_Pengguna, Kata Laluan = auth.Kata_Laluan, Read the captcha characters and input into Kod Sekuriti (hint: captcha is alphabets in capital letters displayed as distorted image above Kod Sekuriti field, Kategori ID radio button "Individu" uid=*_16 must be explicitly clicked even if default checked, textbox "ID Pengguna" uid=*_24 accepts numeric IC format, textbox "Kata Laluan" uid=*_26 masks input with bullets, textbox "Kod Sekuriti" uid=*_28 accepts uppercase letters, captcha refresh button uid=*_29, caps lock warning "Amaran! Kekunci huruf besar sedang aktif." may appear when typing captcha)
3. Click on "Log Masuk" button (hint: button "Log Masuk" uid=*_30 with "Log Masuk" text, must explicitly click "Individu" radio button uid=*_16 first even if appears checked, may need to refresh captcha using button uid=*_29 if captcha validation fails with error "Kod sekuriti tidak SAH!", successful login redirects to dashboard page showing user's full name "ZAINUL AMININ BIN MOHD ZAIN" with timestamp in format "Log Masuk Terakhir YYYY-MM-DD HH:MM:SS.mmm", "Log Keluar" link uid=*_8 present in top right, welcome message "Anda berada di zon yang selamat." displayed, dashboard contains menu tabs: Utama, Kenderaan, Lesen Memandu, Kesalahan & Penalti, Kejuruteraan Automotif, Resit / Perkhidmatan Lain)