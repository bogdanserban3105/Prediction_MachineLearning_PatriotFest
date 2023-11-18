# În ce constă caracterul de inovare al proiectului? Prin ce diferă față de alte abordări potențial existente pe piață?
Caracterul inovator al proiectului constă în utilizarea rețelelor neuronale artificiale pentru a realiza predicții asupra valorilor de debit ale unui aparat și, ulterior, pentru a calcula costul total al energiei consumate. Această abordare se deosebește prin faptul că:

## 1.Utilizarea Rețelelor Neuronale Artificiale (RNA):

- Rețelele neuronale artificiale permit modelarea relațiilor complexe între variabile, putând învăța reprezentări de înaltă calitate din date brute. Acest aspect este deosebit de util în situații în care relațiile dintre variabile sunt dificil de exprimat printr-un set de reguli sau instrucțiuni.
- Capacitatea RNA de a face predicții și generalizări în baza experienței anterioare le face potrivite pentru problemele de predicție, cum este și cazul proiectului.

## 2.Folosirea Configurației Ușor de Personalizat:

- Proiectul include un fișier de configurare (machine_learning.config) pentru a oferi utilizatorilor posibilitatea de a introduce datele dorite fără a fi necesară o cunoștință avansată a codului. - Aceasta face aplicația mai flexibilă și ușor de utilizat pentru diferite scenarii de predicție.

## 3.Transparența și Managementul Datelor:

- Output-ul procesului de antrenare al modelului este afișat atât în consolă, cât și într-un fișier de logging (logfile.log). Acest lucru adaugă transparență în procesul de dezvoltare și permite utilizatorilor să urmărească și să înțeleagă evoluția modelului.

## 4.Flexibilitate în Rularea Modelului:

- După ce modelul a fost antrenat, acesta este salvat în format .onnx, permitând rularea independentă a modelului cu ajutorul programului Main.py. Acest aspect oferă utilizatorilor flexibilitate în implementarea și utilizarea modelului în diverse medii sau contexte.

## 5.Integrarea cu Alte Platforme:

- Datele prezise de algoritmul de machine learning sunt destinate să fie preluate de Node Red și ulterior încărcate într-o bază de date din Cloud. Aceasta deschide posibilități de integrare cu alte platforme și sisteme, extinzând funcționalitățile proiectului și permitând utilizatorilor să beneficieze de datele prezise în contextul lor specific.
- Aceste caracteristici împreună contribuie la inovația proiectului, oferind o soluție eficientă și personalizabilă pentru realizarea de predicții cu privire la valorile de debit ale unui aparat și calcularea costului total al energiei consumate.

# Descrieți conceptele, tehnologiile, standardele pe care le-ați utilizat și/sau generat în realizarea proiectului.


În realizarea proiectului, au fost utilizate și integrate diverse concepte, tehnologii și standarde pentru a asigura funcționalitatea și eficiența acestuia. Mai jos sunt detaliile relevante:

## 1.Concepte de Machine Learning:

- Rețele Neuronale Artificiale (RNA): Utilizarea rețelelor neuronale pentru a modela relațiile complexe dintre variabile și pentru a face predicții asupra datelor de debit.
- Antrenare și Testare a Modelului: Conceptele de împărțire a datelor în seturi de antrenament și evaluare, calcularea erorii, și evaluarea performanței modelului.

## 2.Tehnologii și Module Python:

- TensorFlow și Keras: Biblioteci open-source pentru machine learning și construirea rețelelor neuronale artificiale.
- Pandas și NumPy: Module pentru manipularea eficientă a datelor, inclusiv citirea datelor din fișierele de tip CSV și lucrul cu aranjamente multidimensionale de date.
- JSON: Utilizat pentru lucrul cu date în format JSON, în special pentru parsarea fișierului de configurare.

## 3.Gestionarea și Validarea Datelor:

- Fișier de Configurație (machine_learning.config): Permite utilizatorilor să configureze ușor datele fără a fi necesară o cunoștință detaliată a codului.
- Enum: Utilizat pentru a defini tipuri de enumerare și a crea un set restricționat și predefinit de valori constante.

## 4.Logging și Documentare:

- Modulul Logging: Folosit pentru înregistrarea mesajelor și informațiilor utile în timpul rulării programelor, asigurând transparența și ușurând depurarea.
- README.md: Documentația a fost generată sub formă de fișier README.md, inclus în repository-ul de pe GitHub, pentru a oferi informații detaliate despre proiect și cum să îl utilizeze.

## 5.Gestionarea Argumentelor în Linia de Comandă:

- Argparse: Utilizat pentru analiza argumentelor din linia de comandă atunci când se rulează scripturile, oferind utilizatorilor o modalitate flexibilă de a interacționa cu aplicația.

## 6.Manipularea și Analiza Datelor cu Pandas:

- Pandas: Folosit pentru a manipula și analiza datele din fișierele CSV într-un mod eficient și flexibil.

## 7.Biblioteca Standard Python și Module:

- OS și Pickle: Folosite pentru interacțiunea cu sistemul de operare, verificarea existenței fișierelor și serializarea/deserializarea obiectelor Python.
- JSON: Utilizat pentru lucrul cu date în format JSON, în special pentru parsarea datelor din fișierul de configurare.

## 8.Standardul ONNX (Open Neural Network Exchange):

- tf2onnx: Utilizat pentru conversia modelelor TensorFlow în formatul ONNX, asigurând interoperabilitatea între diferite framework-uri de deep learning și biblioteci.

## 9.Eficiența și Performanța Modelului:

- Onnxruntime: Bibliotecă dezvoltată de Microsoft pentru rularea modelelor AI create în formatul ONNX cu performanță înaltă și eficientă.

## 10.Gestionarea Versiunilor și Colaborare:

- GitHub: Platformă de gestionare a codului sursă, folosită pentru versionare, colaborare și documentare a proiectului.
  
Prin integrarea acestor concepte, tehnologii și standarde, proiectul a fost dezvoltat într-un mod inovator și eficient, furnizând o soluție flexibilă pentru realizarea de predicții asupra datelor de debit în contextul specific al consumului de energie.
