# Proiect-Cloud-computing

Formular Înscriere Voluntari USASE

Stancu Diana

Grupa 1147

https://youtu.be/7byryWNfLlY

1. Introducere                                                                                                                                                                                                       Aplicația
Aplicația „Înscriere Voluntari” este o soluție web integrată, menită să automatizeze procesul de recrutare pentru asociația studențească USASE. Utilizatorul completează un formular simplu, iar datele sunt procesate și stocate automat în cloud, declanșând simultan o notificare de confirmare prin intermediul adresei de gmail instituțională.

2. Descriere problemă
Gestionarea manuală a formularelor de înscriere ale voluntarilor poate conduce la pierderea informațiilor, erori de organizare și întârzieri în procesul de comunicare. 
Aplicația propusă rezolvă aceste probleme prin:
- centralizarea automată a datelor într-un sistem accesibil echipei de recrutare;
- automatizarea confirmării înscrierii prin email;
- reducerea timpului necesar procesării aplicațiilor.

3. Descriere API
Aplicația utilizează două servicii cloud distincte prin intermediul unor API-uri REST:
Google Sheets API este utilizat pentru stocarea datelor. Acesta permite adăugarea de rânduri noi într-un fișier tip Spreadsheet.
IFTTT Maker Webhooks API: Utilizat ca serviciu de automatizare (iPaaS) pentru trimiterea notificărilor pe email. Acesta expune un endpoint HTTP care, la primirea unei cereri POST, declanșează un flux de lucru predefinit (Gmail service).

4. Flux de date
Fluxul de date începe de la client (browser) și se ramifică către cele două servicii cloud.

Metode HTTP:
POST către Google Sheets API pentru adăugarea datelor.
POST către IFTTT Webhook pentru declanșarea email-ului.

Autentificare și Autorizare:
Google Sheets utilizează protocolului OAuth 2.0. Aplicația folosește Google Identity Services pentru a obține un access_token de scurtă durată, oferind acces securizat doar la fișierul specificat.

În cadrul IFTTT, autentificare prin API Key este inclusă direct în URL-ul endpoint-ului pentru simplitate și viteză de execuție.

<img width="596" height="919" alt="image" src="https://github.com/user-attachments/assets/538159de-fef2-4480-8f98-55621c5242f8" />


<img width="483" height="912" alt="image" src="https://github.com/user-attachments/assets/4d34a8d9-f277-48a1-b74c-54552225a95a" />


<img width="944" height="493" alt="image" src="https://github.com/user-attachments/assets/ad4c98b0-abd2-4f80-b44d-0dae510009cf" />


<img width="746" height="455" alt="image" src="https://github.com/user-attachments/assets/1d19dccc-8274-45bc-90d7-9746db04b829" />


6. Referințe
Google Sheets API Documentation: https://developers.google.com/sheets/ap
IFTTT Webhook Documentation: https://ifttt.com/maker_webhooks
