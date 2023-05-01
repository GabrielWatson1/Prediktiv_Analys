Sammanfattning på arbetesprocessen samt de findings som vi har gjort

Import Data / Explore Data

Denna delen är väldigt strightforward, impoterade datan tog reda på vad csv filen innehöll
och sedan gjorde några histrogram samt scatterplots 'target' vilket gav mig en anning om
hur datan i 'target' va fördelad. 
Sen tog jag reda på mängden NAN variablar som fanns i hela datasettet med missing_values
Sen med hjälp av percetage_nan så kan man se att de följade:
feature11    93.369788%
feature12    80.587833%
feature15    48.598770%
Därför beslot jag mig att ta bort dessa columner då de innehåll antigen >50% na värden eller 
en större del av NAN värden i helhet. 

Drop NA Values and Create Dummy Variables
(mitt tänkesätt under denna delen va att eftersom jag inte vet rollen och betydelsen
som all denna datan har så är de mitt jobb som en Data Scientist att behålla så mycket
av datan som de bara går. Det är därför jag tog de valen som jag tog)

Vi tog reda på de columner som hade majoriteten av NAN värden i Explore Data, och valde att 
ta bort dessa kolumner med col_to_remove. Sedan för att arbeta med resterande data så behövde
jag hantera de kolumner som hade NAN värden kvar. Alla dessa kolumner hade 1 NAN värde variablar
så istället för att ta bort NAN värdet så tog jag the mean på respektive kolumner och fyllde
NAN värdet med mean värdet. 
Sen hade vi kolumner med Kategorisk data (kolumner 13, 16), dessa kolumner skapade vi dummy Variables
till. Jag lämmnade ut ett "värde" i både kolumner 13,16 för att undvika multicollonearity (k-1)

Linear Regression

När det kom till stegen i Linear Regression så följade jag de stegen som stog i pdf filen för
inlämmningsuppgiften samt olika lectures.. Det va en lång process av trail och error, angående vilka
features som jag skulle inkludera i feature_names (x). I början hade jag bara ett par, features då jag va osäker
kring hur de skulle påverka modellen. Det blev tillslut i princip nästa alla features som fanns i datasettet

Använde mig av Root Mean Square Error som en metric för att utvädera modellen samt R2 för att
få en anning om "variance between the real and predicted value". I fallet av R2 så fick jag värdet av
0.8334414 vilket motsvarar 83% accuracy. Änvände mig av R" för att det gav mig en indication att modellen 
närmade sig så mycket den kunde tll 1.0
RMSE värdet som jag fick va 31390, vilket givet de stora värden av datasettet känns inte helt fel.
För att RMSE värdet jämnför med "target value"
Jag känner att min sactterplot inte kan "predict" höga värden. Jag försökte att använda mig
av robust scalar för att förbättra modellen. Har med det i koden men gjorde ingen skillnad. Vet ej om jag har
gjorde rätt eller fel. 

Tack för ännu en utamandande men kul kurs att jobba med. Hoppas du har en bra helg :)




