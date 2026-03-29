# Lucrarea de laborator nr. 4. Dezvoltarea unui plugin pentru WordPress

## Condiții

Creează un plugin educațional numit USM Notes, care adaugă pe site o secțiune „Notițe” cu priorități și o dată de reamintire.

### Pasul 1. Pregătirea mediului

1. În instalarea locală WordPress, accesează folderul wp-content/plugins

<img width="249" height="37" alt="image" src="https://github.com/user-attachments/assets/361903e2-05b0-4188-9a3a-6a1be7ab4afa" />

2. Creează un director pentru tema ta, de exemplu usm-notes

<img width="221" height="25" alt="image" src="https://github.com/user-attachments/assets/d8313ec2-1545-4c98-966a-5f582069d4bc" />

3. Activează modul de depanare în wp-config.php, adăugând define('WP_DEBUG', true);

<img width="262" height="40" alt="image" src="https://github.com/user-attachments/assets/e25d5d33-3976-40f6-b26b-fe7640212ac8" />

<img width="263" height="37" alt="image" src="https://github.com/user-attachments/assets/e561379d-2017-4538-aaa1-79d6d939a12b" />

### Pasul 2. Crearea fișierului principal al pluginului

1. În folderul pluginului, creează fișierul usm-notes.php

2. Adaugă în acesta metadatele pluginului (nume, descriere, versiune, autor).

<img width="525" height="169" alt="image" src="https://github.com/user-attachments/assets/5e99880e-8340-4787-bf03-644dee5cbc49" />

3. Activează pluginul în panoul de administrare WordPress.

<img width="1712" height="72" alt="image" src="https://github.com/user-attachments/assets/de09b3c9-398b-40db-a3bf-70d1edcff4a5" />

4.Asigură-te că pluginul este activ și că nu sunt erori.

### Pasul 3. Înregistrarea Custom Post Type (CPT)

1.Adaugă o funcție pentru înregistrarea CPT „Notițe” (Notes) folosind register_post_type()

2.Setează parametrii CPT:

* public,
* suport pentru titlu, editor, autor, miniatură,
* pagină de arhivă,
* pictogramă în admin,
* etichete (labels) pentru utilizare facilă.

<img width="541" height="134" alt="image" src="https://github.com/user-attachments/assets/8ce60430-def5-4ddb-9fbd-fdefa6d99b12" />

3. Înregistrează CPT-ul la inițializarea WordPress folosind hook-ul init

<img width="375" height="22" alt="image" src="https://github.com/user-attachments/assets/200aa181-4f18-462d-ada5-92769ceb66f8" />

### Pasul 4. Înregistrarea taxonomiei personalizate

1.Adaugă o funcție pentru înregistrarea taxonomiei „Prioritate” (Priority) folosind register_taxonomy().

2.Leagă taxonomia de CPT-ul „Notițe”.

3.Setează parametrii taxonomiei:

* ierarhică (precum categoriile),
* publică,
* etichete (labels) pentru utilizare facilă.

4.Înregistrează taxonomia la inițializarea WordPress folosind hook-ul init

<img width="661" height="182" alt="image" src="https://github.com/user-attachments/assets/fde96ad9-a6d4-40e4-ae73-b8ce2ec41159" />

### Pasul 5. Adăugarea unui metabox pentru data de reamintire

1.Creează o funcție pentru adăugarea unui metabox în editorul CPT „Notițe” folosind add_meta_box().

2.În metabox, adaugă un câmp pentru selectarea datei de reamintire (utilizează HTML5 input type="date").

3.Creează o funcție pentru salvarea valorii datei la salvarea postării folosind hook-ul save_post.

4.Asigură-te că data este salvată corect și că este afișată la editarea postării.

5.Adaugă verificarea nonce pentru securitate la salvarea metadatelor.

6.Fă câmpul pentru dată obligatoriu.

7.Adaugă validare pentru dată (de exemplu, data nu poate fi în trecut). În caz de eroare la salvare, afișează un mesaj corespunzător.

8.Afișează data de reamintire în lista postărilor CPT „Notițe” din admin.

<img width="902" height="312" alt="image" src="https://github.com/user-attachments/assets/449b31f3-79fb-41c2-a89c-ad08fa57a7cd" />

### Pasul 6. Crearea unui shortcode pentru afișarea notițelor

1.Creează o funcție pentru procesarea shortcode-ului [usm_notes priority="X" before_date="YYYY-MM-DD"], unde priority este filtrul după prioritate, iar before_date – filtrul după data de reamintire.

2.În funcție, obține și afișează lista notițelor care corespund filtrelor.

3.Înregistrează shortcode-ul folosind add_shortcode().

4.Adaugă stiluri pentru afișarea listei de notițe.

5.Gestionează cazurile în care nu există notițe pentru filtrele respective și afișează mesajul: „Nu există notițe cu parametrii specificați”.

6.Dacă priority sau before_date nu sunt specificate, shortcode-ul trebuie să afișeze toate notițele.

<img width="1026" height="482" alt="image" src="https://github.com/user-attachments/assets/9d3b521b-42a1-429e-a103-b2dfcc8d3491" />


### Pasul 7. Testarea pluginului

1.Adaugă 5–6 notițe cu priorități și date de reamintire diferite.

<img width="224" height="73" alt="image" src="https://github.com/user-attachments/assets/29e5059d-d7a9-41de-9f95-584497f098c4" />

<img width="1732" height="704" alt="image" src="https://github.com/user-attachments/assets/6dd4cd9a-63ba-4cbd-9197-f2007dea46a5" />

La fel facem inca 4 notite

<img width="1714" height="341" alt="image" src="https://github.com/user-attachments/assets/d5aa5c6f-d230-4a8f-8790-d4e5e7df122d" />

2.Atribuie fiecăreia o prioritate (High/Medium/Low) și completează câmpul „Due Date”.

<img width="155" height="329" alt="image" src="https://github.com/user-attachments/assets/9d0ca620-1707-4baf-9722-e7d76e930f04" />

3.Creează pagina „All Notes” și inserează următoarele shortcode-uri:

* [usm_notes] – pentru afișarea tuturor notițelor.

<img width="880" height="791" alt="image" src="https://github.com/user-attachments/assets/3cab1aa7-99f4-4a8b-9281-235d25a13836" />

  
* [usm_notes priority="high"] – pentru notițele cu prioritate mare.

<img width="848" height="558" alt="image" src="https://github.com/user-attachments/assets/eb96ee25-c7fb-4b19-83e4-082311add788" />

* [usm_notes before_date="2026-03-30"] – pentru notițele cu dată de reamintire anterioară zilei de 30 martie 2026.

<img width="816" height="810" alt="image" src="https://github.com/user-attachments/assets/d3603ec9-d10e-4f98-b63d-0fd780380bb6" />

## Întrebări de control

1.Care este diferența esențială dintre o taxonomie personalizată și un metacâmp? Oferă un exemplu când este mai potrivit să folosești taxonomie și când metadate.

Taxonomia grupează postările (ex: toate notițele "Urgente"), în timp ce Metacâmpul stochează detalii unice (ex: o dată specifică). 

Folosești taxonomia pentru categorii și metadatele pentru proprietăți individuale care nu necesită pagini de arhivă.

2.De ce este necesar nonce la salvarea metacâmpurilor și ce se întâmplă dacă nu este verificat?

Nonce-ul este un token de securitate care confirmă că salvarea datelor vine din formularul tău legitim. 

Fără el, site-ul este expus atacurilor de tip CSRF, permițând hackerilor să modifice baza de date prin acțiuni mascate executate în numele unui admin logat.

3.Care sunt cei mai importanți parametri ai register_post_type() și register_taxonomy() pentru frontend și UX (numește cel puțin trei și explică de ce)?

Pentru succesul unui plugin, public asigură vizibilitatea în site, has_archive creează automat o pagină cu lista tuturor postărilor, 

iar hierarchical (pentru taxonomii) permite utilizatorului să aleagă priorități prin bife simple, îmbunătățind considerabil experiența de editare.
