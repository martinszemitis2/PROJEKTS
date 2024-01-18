# **PROGRAMMA VALŪTU MONITORINGAM** <br />

## **Veidotājs: Martins Zemītis (1.kurss, 231RDB174)** 

## **PIRMS VĒRTĪBU IZMAIŅU APRĒĶINIEM IR NEPIECIEŠAMS IEGŪT DATUS (MIN. 2, lai spētu aprēķināt starpību)** 


## **APSKATĪT KOMENTĀRUS PROGRAMMAS KODĀ!** <br />

## Programmas uzdevums <br />
### **1. Apskatīt kriptovalūtu cenas** <br />
### **2. Spēt tās nolasīt kā vērtības** <br />
### **3. Ievietot tās vērtības EXCEL faila un aprēķināt cenas izmaiņas kopš pirmās un pēdējās reizes** <br />

### **4. Programmai ir nepieciešams tikt automātiski palaistai ik reizi, kad tiek ieslēgts dators (shell:startup) NAV OBLIGĀTS** <br />

## Programmai izmantotās bibliotēkas <br />
### **1. Selenium - Nepieciešama mājaslapas automātiskai atveršanai un valūtu cenu apskatei.** <br />
### **2. Openpyxl - Excel automatizēšanai.** <br />
### **3. Time - Nepieciešams, lai varētu nodrošināt programmas pakāpenisku izpildīšanu.** <br />

# Programmas detalizēts apraksts <br />
### **(line 1-8) Tiek importētas visas izmantojamās bibliotēkas, kas nepieciešamas programmas izgatavei.** <br />
<br />
### **(line 11-13) Tiek ievadīts:** <br />
"Service()" - Nepieciešams, lai startētu un apturētu Webdriver servisu. <br />
"webdriver.ChromeOptions()" - Ļauj mainīt iestatījumus "Chrome" pārlūka. <br />
"webdriver.Chrome(service=service, options=option)" - Iestata "Chrome" ar dotajām opcijām. <br />
<br />
### **(line 17-19):** <br />
"url = "https://www.binance.com/lv"" - Norāda mājaslapu, kura tiks izmantota. <br />
"driver.get(url)" - Atver mājaslapu "Chrome" pārlūkā. <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 23-25):** <br />
"cookies=driver.find_element(By.ID, "onetrust-reject-all-handler")" - Atrod dotajā mājaslapā pogu "Noraidīt". (uz sīkfailiem)
"cookies.click()" - Nospiež uz pogu "Noraidīt". <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 29-31):**  <br />
"crypto1=driver.find_elements(By.CLASS_NAME, "css-1ev4kiq")" - Atrod 1.valūtu <br />
"crypto1[0].click()" - Nospiež uz 1.valūtas <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 35-38):** <br />
"crypto1=driver.find_element(By.CLASS_NAME, "css-1bwgsh3")"  - Atrod 1.valūtas cenu. <br />
"valuta1=crypto1.text" - Iegūst 1.vērtību kā tekstu. (str) <br />
"print(valuta1)" - Izprintē 1.vērtību. (Gala rezultāta salīdzināšanai) <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 42-43):** <br />
"driver.get(url)" - Aiziet atpakaļ uz sākumu. <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 46-48):** <br />
"crypto2=driver.find_elements(By.CLASS_NAME, "css-1ev4kiq")" - Atrod 2.valūtu <br />
"crypto2[1].click()" - Nospiež uz 2.valūtas <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 51-54):** <br />
"crypto2=driver.find_element(By.CLASS_NAME, "css-1bwgsh3")"  - Atrod 2.valūtas cenu. <br />
"valuta2=crypto1.text" - Iegūst 2.vērtību kā tekstu. (str) <br />
"print(valuta2)" - Izprintē 2.vērtību. (Gala rezultāta salīdzināšanai) <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 57-58):** <br />
"driver.get(url)" - Aiziet atpakaļ uz sākumu. <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 61-63):** <br />
"crypto3=driver.find_elements(By.CLASS_NAME, "css-1ev4kiq")" - Atrod 3.valūtu <br />
"crypto3[2].click()" - Nospiež uz 3.valūtas <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 66-69):** <br />
"crypto3=driver.find_element(By.CLASS_NAME, "css-1bwgsh3")"  - Atrod 3.valūtas cenu. <br />
"valuta3=crypto1.text" - Iegūst 3.vērtību kā tekstu. (str) <br />
"print(valuta3)" - Izprintē 3.vērtību. (Gala rezultāta salīdzināšanai) <br />
"time.sleep(2)" - Aizmidzina programmu uz 2 sekundēm. (Atļauj mājaslapai ielādēties) <br />
<br />
### **(line 73-75):** <br />
"project=load_workbook('project.xlsx')" - Atver excel failu "project" <br />
"ws=project.active" - Nosaka kurā excel failā darbojas ("project") <br />
"max_row=ws.max_row" - Nodefinē excel failā pēdējo rindu <br />
<br />
### **(line 79-81):** <br />
"ws['A'+str(max_row+1)].value=valuta1" - Ievieto cenas excel failā kolonnā "A" <br />
"ws['B'+str(max_row+1)].value=valuta2" - Ievieto cenas excel failā kolonnā "B" <br />
"ws['C'+str(max_row+1)].value=valuta2" - Ievieto cenas excel failā kolonnā "C" <br />
<br />
<br />
## **Kods vērtību izmaiņu aprēķināšanai** <br />
### **(line 87-89):** <br />
"fvalue1=ws['A'+str(2)].value" - Nosaka 1.vērtību 1.valūtai <br />
"fvalue2=ws['B'+str(2)].value" - Nosaka 1.vērtību 2.valūtai <br />
"fvalue3=ws['C'+str(2)].value" - Nosaka 1.vērtību 3.valūtai <br />
<br />
### **(line 93-95):** <br />
"lvalue1=ws['A'+str(max_row+1)].value" - Nosaka pēdējo vērtību 1.valūtai <br />
"lvalue2=ws['B'+str(max_row+1)].value" - Nosaka pēdējo vērtību 2.valūtai <br />
"lvalue3=ws['C'+str(max_row+1)].value" - Nosaka pēdējo vērtību 3.valūtai <br />
<br />
### **(line 99-101):** <br />
"fvf1=float(fvalue1.replace('$','').replace(',',''))" - Pārveido pirmās vērtības no "string" uz "float" <br />
"fvf2=float(fvalue2.replace('$','').replace(',',''))" - Pārveido pirmās vērtības no "string" uz "float" <br />
"fvf3=float(fvalue3.replace('$','').replace(',',''))" - Pārveido pirmās vērtības no "string" uz "float" <br />
<br />
### **(line 105-107):** <br />
"lvf1=float(lvalue1.replace('$','').replace(',',''))" - Pārveido pēdējās vērtības no "string" uz ""float" <br />
"lvf2=float(lvalue2.replace('$','').replace(',',''))" - Pārveido pēdējās vērtības no "string" uz ""float" <br />
"lvf3=float(lvalue3.replace('$','').replace(',',''))" - Pārveido pēdējās vērtības no "string" uz ""float" <br />
<br />
### **(line 111-113):** <br />
"valc1=(lvf1-fvf1)" - Aprēķina vērtību izmaiņas 1. valūtai <br />
"valc2=(lvf2-fvf2)" - Aprēķina vērtību izmaiņas 2. valūtai <br />
"valc3=(lvf3-fvf3)" - Aprēķina vērtību izmaiņas 3. valūtai <br />
<br />
### **(line 117-119):** <br />
"ws['D'+str(2)].value=valc1" - Ievieto 1.vērtības izmaiņas excel failā <br />
"ws['E'+str(2)].value=valc2" - Ievieto 2.vērtības izmaiņas excel failā <br />
"ws['F'+str(2)].value=valc3" - Ievieto 3.vērtības izmaiņas excel failā <br />
<br />
### **(line 123-125):** <br />
"project.save('project.xlsx')" - Saglabā iegūtos datus excel failā "project" <br />
"project.close()" - Aizver excel failu <br />
"driver.quit()" - Aizver webdriver servisu <br />
<br />

## Programmatūru var izmantot: <br />
### **1. Lasot sarakstītos komentārus** <br />
### **2. Ieslēdzot programmu** <br />
<br />

## Iespējamie uzlabojumi <br />
### **1. Palielināt time.sleep() sekunžu laiku, ja programmu izmanto uz lēnākām iekārtām.** <br />
### **2. Palielināt monitorēto valūtu skaitu, ja nepieciešams.** <br />
### **3. Automatizēt programmas ieslēgšanos noteiktā laika intervālā. (Iespējams nepieciešamas citas bibliotēkas)** <br />
<br />

## Iespaidi par projektu! <br />
### **Man ļoti patika izgatavot šo projektu, jo varēja izpausties programmas kodā un nebija noteiktas prasības.** <br />
### **Cerams, ka nākotnē varēšu izveidot kaut ko ambiciozu. :)** <br />
<br />
### **Martins Zemītis (1.kurss, 231RDB174)**






