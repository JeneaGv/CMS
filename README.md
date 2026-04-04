# Lucrarea de laborator nr. 5. Securitatea WordPress

## Condiții

### Pasul 1. Pregătirea mediului

1. În instalarea locală WordPress, accesează panoul de administrare.

2. Asigură-te că ai acces de administrator.

<img width="1737" height="220" alt="image" src="https://github.com/user-attachments/assets/890fb6a4-31f4-406f-9dd2-5cd3344a6f2a" />

3. Activează modul de depanare în wp-config.php, adăugând define('WP_DEBUG', true);

<img width="262" height="40" alt="image" src="https://github.com/user-attachments/assets/e25d5d33-3976-40f6-b26b-fe7640212ac8" />

<img width="263" height="37" alt="image" src="https://github.com/user-attachments/assets/e561379d-2017-4538-aaa1-79d6d939a12b" />

### Pasul 2. Gestionarea rolurilor și parolelor

1. Creează un utilizator de test cu rolul Autor (pentru verificări ulterioare).

Intram in Users->All Users->Add User 

Completam toate campurile si cream utilizatorul

<img width="1465" height="56" alt="image" src="https://github.com/user-attachments/assets/716af227-1842-40d8-ae13-e0becb921380" />

2. Verifică dacă fiecare administrator are parole complexe activate (minimum 8 caractere, litere/cifre/simboluri).

<img width="594" height="82" alt="image" src="https://github.com/user-attachments/assets/608dc77e-f325-408d-9847-d2330745a21e" />

### Pasul 3. Actualizări ale nucleului, temelor și pluginurilor

1.Verifică existența actualizărilor pentru WordPress, teme și pluginuri.

Intram in Dashboard->Updates si vedem toate acutalizarile existente

2.Actualizează toate componentele la ultimele versiuni disponibile.

<img width="938" height="706" alt="image" src="https://github.com/user-attachments/assets/7b3423ae-c02f-43b4-aa93-6207d8f4a5f9" />

Observam ca nu avem componente ce necesita actualizare

3.Configurează actualizările automate pentru teme și pluginuri.

Pentru Pluginuri:

Intram Plugins->Installed Plugins->Bulk Actions(Enable auto update)

Pentru Teme:

Intram la Appearance -> Themes

Dam click pe imaginea de previzualizare a fiecărei teme instalate.

In fereastra care se deschide, sub numele temei și autor activam actualizările automat

<img width="228" height="134" alt="image" src="https://github.com/user-attachments/assets/e7b5b205-ae1d-4cb1-b68f-82a7a0ddf99b" />

4.Asigură-te că toate actualizările s-au aplicat cu succes și că site-ul funcționează corect.

<img width="190" height="37" alt="image" src="https://github.com/user-attachments/assets/974d7fe6-2728-4708-9a14-5dd2a4fcbca3" />

<img width="308" height="45" alt="image" src="https://github.com/user-attachments/assets/7a6d34be-fedb-4f91-9faf-d866392fdd93" />

<img width="1430" height="847" alt="image" src="https://github.com/user-attachments/assets/a8069f7d-3d11-4e96-bf0f-7f105317477a" />

### Pasul 4. Hardening de bază

1.Dezactivează editarea fișierelor din panoul de administrare, adăugând în wp-config.php:

<img width="363" height="44" alt="image" src="https://github.com/user-attachments/assets/c954fe96-13c9-4494-a066-eeb4e12f7a3d" />

3.Protejează fișierul wp-config.php, adăugând în .htaccess:

<img width="217" height="91" alt="image" src="https://github.com/user-attachments/assets/1898573e-ebaf-4dd2-9d3f-68aa91c188fb" />

### Pasul 5. Instalarea și configurarea inițială a All In One WP Security & Firewall (AIOS)

1.Instalează și activează pluginul All In One WP Security & Firewall.

Mergem la Plugins->Add Plugin

Cautam  All In One WP Security & Firewall. AIOS si instalam

Intram la Plugins->Installed Plugins si activam acesta

2.Accesează secțiunea pluginului din panoul de administrare.

Accesam sectiunea AIOS aparuta

3.Configurează următorii parametri:

User Login:

Activează Login Lockdown. Parametri recomandați pentru testare: Max Login Attempts: 5, Login Retry Time Period: 15 min, Lockout Time: 30 min.

<img width="1210" height="240" alt="image" src="https://github.com/user-attachments/assets/811faf3b-e17b-4ddc-8108-546c5b35ecf4" />

Activează Force Logout (de exemplu, 24h) pentru a limita sesiunile „eterne”.

<img width="920" height="285" alt="image" src="https://github.com/user-attachments/assets/f7ca32d9-27fc-48c3-a658-1e1137fe9699" />

Am lasat valoarea implicita de o ora

User Accounts:

Verifică dacă există un utilizator cu loginul admin. Dacă da — redenumește-l prin AIOS cu un nume de utilizator sigur.

Nu avem utilizatori de genu

User Registration:

Dezactivează auto-aprobarea sau activează aprobarea manuală a utilizatorilor noi dacă înregistrarea este activată.

<img width="1030" height="172" alt="image" src="https://github.com/user-attachments/assets/e4b39390-3a65-4562-a3c6-11a2730270e0" />

Filesystem Security:

Rulează verificarea File Permissions și aplică corecturile recomandate (nu seta permisiuni scriere globale).

<img width="187" height="52" alt="image" src="https://github.com/user-attachments/assets/ab271a77-8759-4ee6-acf5-d0b91e255bf2" />

<img width="834" height="123" alt="image" src="https://github.com/user-attachments/assets/70140a7f-c717-4fa8-8740-fc72f7dc1afa" />

Firewall:

Activează Basic Firewall (începe cu nivelul de bază).

<img width="658" height="153" alt="image" src="https://github.com/user-attachments/assets/73c3b1dd-40dd-4f86-b858-9e14d2a3e9f7" />

Activează protecția împotriva Bad Query Strings, XSS, directory browsing.

<img width="668" height="186" alt="image" src="https://github.com/user-attachments/assets/c78ba09e-2195-4c6b-a306-a544b1bf409d" />

<img width="691" height="170" alt="image" src="https://github.com/user-attachments/assets/1e7d3190-2767-44c1-851b-29e7ae0c112f" />

<img width="692" height="215" alt="image" src="https://github.com/user-attachments/assets/5c6d9080-c262-406e-85e5-0d452f4997c9" />

Brute Force:

Activează Rename Login Page (schimbă URL-ul de autentificare de la /wp-login.php la ceva unic, de ex. /login-<slug>).

<img width="1690" height="224" alt="image" src="https://github.com/user-attachments/assets/dcab3d04-c457-44fb-92b7-4374dbc4f927" />

Salvează noul URL într-un manager de parole!

Scanner / Malware:

Configurează file change detection (notificări pe email).

<img width="767" height="182" alt="image" src="https://github.com/user-attachments/assets/6fada56f-bccc-4681-a7c4-965eb4b2578b" />

Backup:

În secțiunea Database, creează o copie de rezervă a BD (stocheaz-o în afara rădăcinii web). Configurează un program de backup, dacă este disponibil.

<img width="712" height="206" alt="image" src="https://github.com/user-attachments/assets/5998f175-87b8-4d77-8aea-3c40c8a3db25" />

Apasam pe linkul de mai jos,trecem toti pasii si facem backup la baza de date

Setam ca acesta sa se execute odata pe saptamana 

<img width="754" height="66" alt="image" src="https://github.com/user-attachments/assets/39ceed04-d1ed-492d-910f-8b3f6f04199a" />

Notifications:

Activează notificări pe email pentru evenimente importante (de ex. blocare, cont nou de admin, modificări de fișiere).

Lockdown

<img width="1010" height="209" alt="image" src="https://github.com/user-attachments/assets/079b0099-c451-4e29-a1a0-af8da282c1f0" />

Scanner

<img width="851" height="227" alt="image" src="https://github.com/user-attachments/assets/74f22835-ae57-455e-89f6-853dcaea5c5e" />

backup

<img width="881" height="57" alt="image" src="https://github.com/user-attachments/assets/4ceacd5e-a652-4ba1-92c9-0f31faf47897" />

### Pasul 6. Testarea protecției brute-force (pe un utilizator de test)

1.Deconectează-te din admin (sau folosește o fereastră privată).

<img width="681" height="463" alt="image" src="https://github.com/user-attachments/assets/7db16e62-1718-41da-be47-d64139fa0a11" />

2.Accesează noul URL de autentificare, încearcă să introduci o parolă greșită de 5–6 ori.

<img width="498" height="47" alt="image" src="https://github.com/user-attachments/assets/770be70b-3ae3-426a-933d-252ce638ee83" />

3.Asigură-te că Lockdown-ul s-a activat (blocare IP/utilizator).

<img width="851" height="149" alt="image" src="https://github.com/user-attachments/assets/ee6dd3b4-182b-409e-a6fb-2f78117679a3" />


4.Verifică înregistrarea blocării în WP Security → Dashboard / Logs și (dacă este necesar) deblochează IP-ul de test.

<img width="1657" height="646" alt="image" src="https://github.com/user-attachments/assets/e2a9a5a2-edbe-46b3-abd0-9c29c5597811" />

### Pasul 7. Restaurarea din backup

1.Șterge o postare de test și o imagine aleatorie.

<img width="940" height="807" alt="image" src="https://github.com/user-attachments/assets/924c6a8e-44ca-4f3e-8bc0-51fb2f035530" />

<img width="1740" height="330" alt="image" src="https://github.com/user-attachments/assets/ae9323d8-4854-4bc9-adf3-d7037756c3cf" />

<img width="1244" height="422" alt="image" src="https://github.com/user-attachments/assets/fc81099e-2f2d-4cd1-b284-343980857cc3" />

2.Restaurează baza de date din backup (import SQL sau prin plugin).

<img width="1674" height="87" alt="image" src="https://github.com/user-attachments/assets/7ca5be0f-fb55-4411-ae6c-e7643e9b0ee2" />

<img width="870" height="350" alt="image" src="https://github.com/user-attachments/assets/543d8ad8-0d61-4b58-b954-20bc3e2a9140" />

3.Verifică integritatea datelor (au fost restaurate imaginea și postarea șterse?).

<img width="1000" height="373" alt="image" src="https://github.com/user-attachments/assets/0ffa8462-295a-4304-a621-eef4fc78dcc9" />

Imaginea sa restaurat dar nu pana la capat

<img width="1714" height="235" alt="image" src="https://github.com/user-attachments/assets/b8a94eab-c2d5-4603-87f7-7897ee6b70b5" />

## Întrebări de control

1.De ce DISALLOW_FILE_EDIT și permisiunile corecte pe wp-config.php reduc semnificativ riscul post-exploit?

Am învățat că acestea blochează un atacator care a spart deja parola de admin. DISALLOW_FILE_EDIT îi interzice să scrie cod periculos direct în teme din browser, 

iar permisiunile pe wp-config.php îi ascund "cheile" bazei de date, limitând daunele după acces.

2.Ce setări ai ales pentru Login Lockdown/Firewall și de ce (explică echilibrul între securitate și experiența utilizatorului)?

Am pus 5 încercări în 15 minute cu blocare de 30 de minute.

E un echilibru bun: oprește roboții care bagă mii de parole, dar nu blochează imediat un coleg de laborator care a uitat parola sau a lăsat Caps Lock pornit.

3.Cu ce se deosebesc măsurile de protecție la nivel WordPress (plugin/WAF) față de cele la nivelul serverului web și al sistemului de operare?

Măsurile WordPress (plugin) filtrează utilizatorii și spam-ul, cele de Server (.htaccess) opresc atacul la "intrare" înainte să atingă site-ul, 

iar cele de OS (permisiuni 755/644) sunt ultima barieră care protejează fișierele fizice de pe disc împotriva modificării. (in Windows acestea nu sunt permise)

4.Ce trebuie inclus neapărat într-un backup „complet” WordPress și cum verifici dacă restaurarea funcționează cu adevărat?

E obligatoriu să ai baza de date SQL (pentru texte/setări) și folderul wp-content (pentru poze/teme). 

Ca să fiu sigur că restaurarea a mers, am verificat manual dacă pozele apar în galerie și dacă paginile se deschid fără erori 404.
