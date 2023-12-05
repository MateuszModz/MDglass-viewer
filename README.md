# MDglass-viewer
MDglass viewer is a program for graphical analysis of molecular dynamics simulations data from the LAMMPS program.

Krótka instrukcja obsługi do testów programu (na razie po polsku)
1) Główne okno
   Program włączamy przez skompilowanie pliku Main.ipynb. W razie problemów z brakiem odpowiednich bibliotek proszę odkomentować linie kodu znajdujące się na górze pliku Main.ipynb i skompilować plik ponownie.
   Po uruchomieniu programu pokaże się nam główne okno. W obecnej wersji brakuje pewnych zabezpieczeń i obsługi błędów, co sprawia, że najpierw należy wczytać plik z termodynamiką typu log/out i dopiero po tym
   korzystać z innych funkcji programu. W obecnej wersji można pracować tylko na jednym pliku log/out na raz. Po wczytaniu danych przyciskiem "Load Log Files..." zapełnią się rozwijane listy wielkości, które
   można wyrysować na czterech wykresach. Znaczenie rozwijanych list podpisanych X i Y jest oczywiste, a N oznacza numer symulacji. Po wybraniu interesujących nas wielkości i numeru symulacji możemy wyrysować
   wykresy przyciskiem "Plot".
      
2) Okno do dopasowania liniowego
   W oknie głównym klikamy przycisk "Linear Fit". Pokaże nam się okienko, gdzie analogicznie chcemy wybrać X, Y i N i nacisnąć przycisk "Plot". Na wykresie pokaże nam się czerwony, pionowy kursor. Dwa kliknięcia 
   na wykresie definiują przedział dopasowania, na którym jest dopasowana prosta. Parametry dopasowanej prostej pokazują się w tabeli poniżej wykresu. Parametry zawierają kolor narysowanej prostej (na razie kod koloru),
   współczynnik kierunkowy a, punkt przecięcia z osią OY b oraz lim1 i lim2, które są granicami przedziału dopasowania. Kolejną funkcją jest znalezienie punktu przecięcia prostych, który będzie obliczony dla dwóch
   ostatnio wybranych prostych (wybranie oznacza kliknięcie na wiersz w tabeli!) po kliknięciu przycisku "Intersection point". Punkt przecięcia zostanie wyrysowany linią przerywaną (jeżeli proste przecinają się w
   granicach wykresu), a jego wartość zostanie wypisana pod ww. przyciskiem. Póki co nie można usuwać konkretnych prostych, ale można usunąć je wszystkie poprzez narysowanie na nowo wykresu przyciskiem "Plot".
   
4) Okno do oglądania funkcji rozkładu par
   W oknie głównym klikamy przycisk "RDF". W nowym okienku pokażą się znajome listy X, Y i N oraz przycisk "Plot". Po wyrysowaniu intersującego nas wykresu zobaczymy, że po prawej stronie znajduje się pusty wykres RDF.
   Dopiero po wczytaniu pliku rdf (brak zabezpieczeń, program może się wywalić w przypadku niewłaściwego formatu, nazwa i rozszerzenie nie mają znaczenia) pokaże nam się na lewym wykresie kursor, którym przez kliknięcie możemy wybrać punkt na wykresie.
   Program znajdzie najbliższy punkt X0 do miejsca kliknięcia, po czym znajdzie najbliższy punkt X1, który ma wczytaną funkcję RDF, do punktu X0. Każdy punkt na wykresie ma swój krok czasowy, tak samo funkcja rozkładu par jest liczona
   dla danego kroku czasowego, przy czym trzeba pamiętać, że funkcje rozkładu par mogą być liczone dowolnie rzadko w stosunku do termodynamiki symulacji. Punkt X1 zostanie narysowany na lewym wykresie, a na prawym pokaże się
   fukncja RDF dla kroku czasowego punktu X1. Co do samego wczytywania plików rdf, możliwe jest wczytywanie pojedynczego pliku, wielu plików naraz i nadpisywanie funkcji RDF dla konkretnych kroków czasowych poprzez wczytanie
   pliku. Przykładowo jeżeli najpierw wczytamy plik z funkcją RDF dla kroków czasowych 1-10, a następnie wczytamy plik z krokami 5-15 to kroki 5-10 zostaną nadpisane, a kroki 11-15 zostaną dopisane.

Co dalej?
Zmiana GUI w celu obsługi wielu plików log/out na raz. W głównym oknie będzie to zaimplementowane w postaci zakładek, dla których będzie widać cztery wykresy podglądowe. Każdy plik log/out (każda zakładka) będzie miała 
swoje jedno okienko do analizy z zakładkami "Linear FIt", "RDF" itd. zamiast odzielnych okienek dla każdej funkcjonalności.
Planowane są generalne poprawy przejrzystości i estetyki GUI.
Poprawa wygody funkcjonalności "Linear Fit", głównie z wybieraniem prostych do obliczania punktu przecięcia. Dodanie możliwości usuwania prostych z wykresu i tabeli.
W przypadku funkcjonalności "RDF" planowane jest dodanie przycisku do czyszczenia wczytanych danych rdf (obecnie możliwe jest zamknięcie i ponowane otworzenie okna). Możliwość odczytania współrzędnych wybranego punkt z wykresu RDF 
poprzez kliknięcie.
Ogólne uporządkowanie kodu, rozdzielenie go na więcej plików i napisanie komentarzy.

W przypadku uwag/sugestii/pomysłów proszę o kontakt z dr inż. Przemysławem Dzięgielewskim lub bezpośrednio ze mną (mateusz.modzelewski3.stud@pw.edu.pl).
   
