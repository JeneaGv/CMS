# Lucrarea de laborator nr. 3. Dezvoltarea unei teme WordPress simple

## Preconditii 

De elaborat Laboratorul nr. 2

## Condiții

### Pasul 1. Pregătirea mediului

1. În instalarea locală WordPress, accesează folderul wp-content/themes

<img width="467" height="152" alt="image" src="https://github.com/user-attachments/assets/c594867f-8738-4c72-a3fe-63f750c65cd8" />


2. Creează un director pentru tema ta, de exemplu usm-theme

<img width="478" height="166" alt="image" src="https://github.com/user-attachments/assets/6ad71b10-e7ea-4e6e-903e-0d58d9555481" />

3. Activează modul de depanare în wp-config.php, adăugând define('WP_DEBUG', true);

<img width="262" height="40" alt="image" src="https://github.com/user-attachments/assets/e25d5d33-3976-40f6-b26b-fe7640212ac8" />

<img width="263" height="37" alt="image" src="https://github.com/user-attachments/assets/e561379d-2017-4538-aaa1-79d6d939a12b" />

### Pasul 2. Crearea fișierelor obligatorii ale temei

1. În folderul temei, creează fișierul style.css cu metadatele temei.

2. După metadate, poți adăuga reguli CSS de bază.

<img width="719" height="470" alt="image" src="https://github.com/user-attachments/assets/56fa3f24-471f-4729-ae05-d1fb745fd656" />

3. Creează fișierul index.php – șablonul principal al temei. Pentru început, adaugă o structură HTML de bază.

<img width="1217" height="738" alt="image" src="https://github.com/user-attachments/assets/d7f48b3d-2d57-42a7-8c58-bac81366083b" />

### Pasul 3. Componente comune ale șabloanelor

1. Creează fișierul header.php și mută acolo codul antetului site-ului (până la începutul conținutului principal).

<img width="692" height="407" alt="image" src="https://github.com/user-attachments/assets/b09e24d5-96cf-4974-887c-2c8a43fa40d5" />

2.Creează fișierul footer.php și mută acolo codul subsolului site-ului (după conținutul principal).


<img width="581" height="171" alt="image" src="https://github.com/user-attachments/assets/e644d05b-5a3e-4cb6-9b2b-59213a541349" />

3. În index.php, include header.php și footer.php folosind funcțiile get_header() și get_footer().

<img width="774" height="289" alt="image" src="https://github.com/user-attachments/assets/71e15b27-87e3-49bb-a591-406e522a8615" />

4.Pe pagina principală, afișează o listă cu ultimele 5 postări folosind bucla WordPress.

<img width="773" height="701" alt="image" src="https://github.com/user-attachments/assets/dec34149-f2cc-46eb-b5f9-18f344d239f6" />

### Pasul 4. Fișierul de funcții

1.Creează fișierul functions.php în directorul temei.

2.În functions.php, adaugă o funcție pentru încărcarea stilurilor temei folosind wp_enqueue_style().

<img width="622" height="201" alt="image" src="https://github.com/user-attachments/assets/5d42e52f-e5b0-49fb-97af-e9037f43d1ef" />

### Pasul 5. Șabloane suplimentare

1. Creează fișierul single.php pentru afișarea unei postări individuale.

Inlocuim the_excerpt() cu the_content() pentru a vedea tot textul postării.

<img width="235" height="36" alt="image" src="https://github.com/user-attachments/assets/eeaf8b22-71e0-4caf-8481-f565f485c095" />

2. Creează fișierul page.php pentru afișarea paginilor.

<img width="878" height="651" alt="image" src="https://github.com/user-attachments/assets/4a0969ee-f236-407f-b4c7-b416801ed475" />

Diferența față de single.php sunt ca eliminat metadatele precum the_author() și the_category(), 

deoarece paginile sunt considerate conținut static, nu cronologic

3. Creează fișierul sidebar.php pentru bara laterală și include-l în șabloanele relevante cu get_sidebar()

<img width="443" height="136" alt="image" src="https://github.com/user-attachments/assets/c0b20a60-9ca6-4c6b-8088-69fc8dbfb7ba" />

<img width="511" height="80" alt="image" src="https://github.com/user-attachments/assets/7c3f892a-aeea-4a74-be66-69be467c790b" />

4. Creează fișierul comments.php pentru afișarea comentariilor și include-l în single.php și page.php.

<img width="1160" height="853" alt="image" src="https://github.com/user-attachments/assets/63f7509a-f485-4de5-81d1-f6cbf11dafb2" />

<img width="385" height="86" alt="image" src="https://github.com/user-attachments/assets/8da5dddf-3d40-4b22-a046-184bdcf6e373" />

<img width="448" height="88" alt="image" src="https://github.com/user-attachments/assets/c51f9bf7-8a45-4193-87f9-5045438e780a" />

5.Creează fișierul archive.php pentru afișarea arhivelor postărilor.

<img width="907" height="748" alt="image" src="https://github.com/user-attachments/assets/a0f8c764-2cbd-4f69-a324-953e90d456cf" />

### Pasul 6. Stilizarea temei

Adaugă stiluri pentru elementele principale ale temei (antet, subsol, conținut, bara laterală).

<img width="659" height="709" alt="image" src="https://github.com/user-attachments/assets/c26fe9cb-3b73-42d6-a64c-c450fdeef326" />

<img width="862" height="839" alt="image" src="https://github.com/user-attachments/assets/d22577f7-647c-4804-9574-731015859494" />

<img width="458" height="200" alt="image" src="https://github.com/user-attachments/assets/1dc491f7-6297-4737-8863-5df0e451e029" />

### Pasul 7. Captura de ecran a temei

Adaugă în folderul temei fișierul screenshot.png – o imagine de previzualizare a temei (dimensiune 1200x900px).

<img width="1449" height="806" alt="image" src="https://github.com/user-attachments/assets/b0a9f5f6-8866-48cd-ad6a-f1e00a343a02" />

### Pasul 8. Activarea temei

1.În panoul de administrare WordPress, accesează secțiunea Appearance → Themes.

2.Găsește tema ta și activeaz-o.

<img width="422" height="364" alt="image" src="https://github.com/user-attachments/assets/214ca059-3655-4140-a3c9-473a29eb8ee7" />

3.Verifică modul în care site-ul este afișat cu tema ta

<img width="1554" height="761" alt="image" src="https://github.com/user-attachments/assets/3bdb61d3-9ee3-4449-a912-67557de46236" />

## Întrebări de control

1.Care sunt cele două fișiere obligatorii pentru orice temă WordPress?

O temă WordPress nu poate funcționa fără următoarele două fișiere style.css si index.php

2.Cum se includ părțile comune ale șabloanelor (header, footer, sidebar)?

WordPress folosește funcții dedicate pentru a apela secțiunile repetitive ale site-ului: get_header(),get_footer(),get_sidebar()

3.Care este diferența dintre index.php, single.php și page.php?

index.php afișează lista generală cu ultimele noutăți, în timp ce single.php deschide un singur articol complet, 

iar page.php încarcă paginile statice precum "Despre" sau "Contact".

4.Care este rolul fișierului functions.php într-o temă?

functions.php este "creierul" temei, fiind locul unde încarci stilurile prin wp_enqueue_style() și activezi opțiuni.
