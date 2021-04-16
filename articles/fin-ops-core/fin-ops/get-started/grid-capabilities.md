---
title: Możliwości siatki
description: W tym temacie opisano kilka zaawansowanych funkcji formantu siatki. Musisz włączyć nową funkcje siatki, aby można było uzyskać dostęp do tych możliwości.
author: jasongre
ms.date: 01/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c8f417b3ba427104d6d0e57ac595ab7b453f48fa
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749572"
---
# <a name="grid-capabilities"></a>Możliwości siatki

[!include [banner](../includes/banner.md)]


Nowa kontrolka siatki zapewnia kilka przydatnych i zaawansowanych funkcji, które mogą być używane w celu zwiększenia wydajności użytkowników, tworzenia bardziej interesujących widoków danych oraz uzyskiwania informacji o szczegółowych danych. Ten artykuł będzie obejmował następujące możliwości: 

-  Obliczanie sum
-  Pisanie przed systemem
-  Ocenianie wyrażeń matematycznych 
-  Grupowanie danych tabelarycznych (włączone oddzielnie za pomocą funkcji **Grupowania w module siatki (wersja zapoznawcza)**)
-  Zamrażanie kolumn

## <a name="calculating-totals"></a>Obliczanie sum
W aplikacjach grupy Finance and Operations użytkownicy mają możliwość wyświetlania sum na dole kolumn liczbowych w siatkach. Sumy te są wyświetlane w sekcji stopki u dołu siatki. 

### <a name="showing-the-grid-footer"></a>Pokazywanie stopki siatki
W dolnej części każdej siatki tabelarycznej w aplikacjach Finance and Operations znajduje się obszar stopki. Stopka może zawierać cenne informacje związane z danymi wyświetlanymi w siatce. Oto kilka przykładów takich informacji:

- Liczba zaznaczonych wierszy w tabeli (gdy zaznaczysz więcej niż jeden rekord)
- Sumy końcowe u dołu skonfigurowanych kolumn liczbowych
- Liczby kolumn w zestawie danych 

Ta stopka jest domyślnie ukryta, ale możesz ją włączyć. Aby wyświetlić stopkę siatki, kliknij prawym przyciskiem myszy nagłówek kolumny w siatce i wybierz opcję **Pokazuj stopkę**. Po włączeniu stopki dla określonej siatki to ustawienie będzie przypominane do czasu, aż użytkownik zdecyduje się ukrywać stopkę. Aby ukryć stopkę, kliknij prawym przyciskiem myszy nagłówek kolumny i wybierz polecenie **Ukryj stopkę**.  (Położenie akcji **Pokazuj stopkę/Ukryj stopkę** może zmienić się na nową lokalizację w przyszłej aktualizacji). 

### <a name="specifying-columns-with-totals"></a>Określanie kolumn z sumami
Obecnie domyślnie żadne kolumny nie zawierają sum. Zamiast tego jest to uważane za jednorazowe działanie konfiguracji, podobne do korygowania szerokości kolumn w siatkach. Po określeniu, że dla kolumny mają być wyświetlone sumy, to ustawienie zostanie zapamiętane przy następnej wizycie na tej stronie.  

Istnieją dwa sposoby skonfigurowania kolumny do wyświetlania sumy: 

- Kliknij prawym przyciskiem myszy kolumnę, dla której chcesz zobaczyć sumę, a następnie wybierz **Suma dla tej kolumny**. Ta akcja powoduje wystąpienie trzech zdarzeń:

    1. Stopka staje się widoczna. 
    2. Twoje preferencje dotyczące wyświetlania sumy dla tej kolumny zostaną zapisane. 
    3. Obliczanie sum jest inicjowane dla tej kolumny i wszystkich innych kolumn, dla których skonfigurowano uprzednio wyświetlanie sum. Czas wymagany do wyświetlenia sumy zależy od rozmiaru zestawu danych do sumowania.

- Po wyświetleniu stopki wybierz opcję **Pokaż sumę** w obszarze stopki u dołu kolumny, dla której ma zostać wyświetlona suma. Jeśli nie ma skonfigurowanych kolumn, przycisk **Pokazuj sumę** będzie dostępny dla wszystkich kolumn liczbowych. 

    Po skonfigurowaniu co najmniej jednej kolumny dla sum, przyciski **Pokaż sumę** będą dostępne tylko przy najechaniu na nie kursorem lub skoncentrowaniu się na nich. Akcja wybranie opcji **Pokaż sumę** powoduje zapisanie preferencji w tej kolumnie, dzięki czemu preferencja będzie stosowana podczas przyszłych odwiedzin na stronie. W stopce ten stan jest wskazywany przez kreskę wyświetlaną w kolumnie. (Jeśli zestaw danych jest wystarczająco mały, suma jest natychmiast pokazywana.)

Jeśli popełnisz błąd i nie chcesz już wyświetlać sumy w określonej kolumnie, kliknij prawym przyciskiem myszy kolumnę i wybierz polecenie **Ukryj sumę** lub wybierz przycisk **Ukryj sumę** w stopce w tej kolumnie. Ta preferencja zostanie również zapisana dla przyszłych odwiedzin na stronie. 

### <a name="calculating-totals"></a>Obliczanie sum
Jeśli zostanie wyświetlona strona z widoczną stopką i kolumny już skonfigurowane dla sum, sumy mogą lub nie być widoczne w stopce. Zachowanie zależy od rozmiaru zestawu danych na stronie. Jeśli zestaw danych jest wystarczająco mały, sumy będą pokazywane automatycznie wraz z liczbą wierszy w zestawie danych. Jeśli w stopce w kolumnach skonfigurowanych dla sum znajdują się kreski, wówczas zestaw danych jest za duży, aby system natychmiastowo pokazywał sumy, a do obliczania sum jest wymagana jawna akcja. W tym celu należy kliknąć przycisk **Oblicz** w stopce lub kliknąć prawym przyciskiem myszy kolumnę, dla której ma zostać obliczona suma, a następnie wybrać opcję **Suma dla tej kolumny**.  

Jeśli obliczanie trwa zbyt długo, można anulować operację, wybierając przycisk **Anuluj**. Czasami jednak ten zestaw danych będzie zbyt duży do obliczania sum (limit narzucony przez Twoją organizację) i zamiast tego użytkownik zostanie powiadomiony o konieczności przefiltrowania danych.

Sumy zostaną automatycznie zaktualizowane podczas aktualizowania, usuwania lub tworzenia wierszy w zestawie danych.  

## <a name="typing-ahead-of-the-system"></a>Pisanie przed systemem
W wielu scenariuszach biznesowych możliwość szybkiego wprowadzania danych do systemu jest bardzo ważna. Zanim zostanie wprowadzony nowy formant siatki, użytkownicy będą mogli zmieniać dane tylko w bieżącym wierszu. Aby utworzyć nowy wiersz lub przełączyć się do innego wiersza, należy zaczekać, aż system pomyślne sprawdzi poprawności zmian. W celu poprawienia czasu, w którym użytkownicy oczekują na ukończenie tych weryfikacji i zwiększenia wydajności użytkownika, nowa siatka koryguje te operacje, tak aby były one asynchroniczne. Dzięki temu użytkownik może przechodzić do innych wierszy w celu wprowadzenia zmian, podczas gdy oczekiwania na poprzednie sprawdzanie poprawności wierszy. 

Aby można było obsłużyć to nowe zachowanie, nowa kolumna dla stanu wiersza została dodana po prawej stronie kolumny wyboru wiersza, gdy siatka jest w trybie edycji. W tej kolumnie jest wskazywany jeden z następujących stanów:

- **Pusty** — Brak obrazu stanu wskazuje, że wiersz został pomyślnie zapisany przez system.
- **Przetwarzanie w toku** — Ten stan wskazuje, że zmiany w wierszu nie zostały jeszcze zapisane przez serwer, ale znajdują się w kolejce zmian, które muszą zostać przetworzone. Przed wykonaniem akcji poza siatką należy poczekać na przetworzenie wszystkich oczekujących zmian. Ponadto tekst w tych wierszach jest pisany kursywą w celu wskazania niezapisanego stanu wierszy. 
- **Nieprawidłowy stan** — Ten stan wskazuje, że podczas przetwarzania wiersza zostało wyzwolone pewne ostrzeżenie lub komunikat, co mogło uniemożliwić systemowi zapisanie zmian w tym wierszu. W starej siatce, jeśli operacja zapisu nie powiodła się, zostaniesz przeniesiony z powrotem do wiersza, aby natychmiast rozwiązać problem. Jednak w nowej siatce zostanie wyświetlone powiadomienie, że napotkano problem z weryfikacją, ale można zdecydować, kiedy mają być naprawione wszystkie problemy występujące w danym wierszu. Gdy wszystko będzie gotowe do rozwiązania problemu, można ręcznie przenieść uwagę z powrotem na wiersz. Alternatywnie można wybrać akcję **Napraw ten problem**. Ta akcja powoduje natychmiastowe przeniesienie uwagi z powrotem do wiersza, którego dotyczy ten błąd, oraz umożliwia wprowadzanie zmian w siatce lub poza nią. Należy zauważyć, że przetwarzanie kolejnych wierszy oczekujących zostało zatrzymane do czasu rozwiązania tego ostrzeżenia o sprawdzeniu poprawności. 
- **Wstrzymano** — Ten stan wskazuje, że przetwarzanie przez serwer zostało wstrzymane, ponieważ weryfikacja wiersza wyzwoliła wyskakujące okno dialogowe, które wymaga wprowadzenia danych przez użytkownika. Ponieważ użytkownik może wprowadzać dane w innym wierszu, wyskakujące okno dialogowe nie jest natychmiast prezentowane użytkownikowi. Zamiast tego zostanie on przedstawiony, gdy użytkownik wybierze opcję wznowienia przetwarzania. Do tego stanu dołączane jest powiadomienie, które informuje użytkownika o sytuacji. Powiadomienie zawiera akcję **Wznawiania przetwarzania**, która będzie wyzwalać wyskakujące okno dialogowe.  
    
Gdy użytkownicy wprowadzają dane przed miejscem przetwarzania serwera, mogą oczekiwać na wprowadzenie kilku degradacji w środowisku wprowadzania danych, takich jak brak wyszukiwań, sprawdzanie poprawności na poziomie kontroli i wprowadzanie wartości domyślnych. Użytkownicy, którzy potrzebują listy rozwijanej do znalezienia wartości, są zachęcani do czekania, aż serwer dogoni bieżący wiersz. Sprawdzanie poprawności na poziomie kontroli i wprowadzanie wartości domyślnych będą również występować, gdy serwer przetwarza ten wiersz.   

### <a name="pasting-from-excel"></a>Wklejanie z programu Excel
Użytkownicy zawsze mogli eksportować dane z siatek w aplikacjach Finance and Operations do programu Excel za pomocą mechanizmu **Eksport do programu Excel**. Jednak możliwość wprowadzania danych przed systemem umożliwia nowej siatce obsługę kopiowania tabel z programu Excel i wklejanie ich bezpośrednio do siatek w aplikacjach Finance and Operations. Komórka siatki, z której jest inicjowana operacja wklejenia określa miejsce, w którym rozpocznie się wklejanie skopiowanej tabeli. Zawartość siatki jest zastępowana zawartością skopiowanej tabeli, z wyjątkiem dwóch przypadków:

- Jeśli liczba kolumn w kopiowanej tabeli przekracza liczbę kolumn pozostających w siatce, rozpoczynając od lokalizacji wklejania, użytkownik zostanie poinformowany, że dodatkowe kolumny zostały zignorowane. 
- Jeśli liczba wierszy w kopiowanej tabeli przekracza liczbę wierszy w siatce, począwszy od lokalizacji wklejania, istniejące komórki zostaną zastąpione przez wklejoną zawartość, a wszystkie dodatkowe wiersze ze skopiowanej tabeli zostaną wstawione jako nowe wiersze u dołu siatki. 

## <a name="evaluating-math-expressions"></a>Ocenianie wyrażeń matematycznych
Jako środek zwiększający produktywność, użytkownicy mogą wprowadzać formuły matematyczne w komórkach liczbowych w siatce. Nie muszą one przeliczać w aplikacji poza systemem. Jeśli na przykład wprowadzisz wartość **=15\*4**, a następnie naciśnij klawisz **Tab**, aby przenieść się z pola, system oszacuje wyrażenie i zapisze wartość **60** dla tego pola.

Aby system rozpoznawał wartość jako wyrażenie, należy uruchomić wartość ze znakiem równości (**=**). Więcej informacji na temat obsługiwanych operatorów i składni zawiera sekcja [obsługiwane symbole matematyczne](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Grupowanie danych tabelarycznych
Użytkownicy biznesowi często muszą przeprowadzać analizę danych ad hoc. Chociaż można to zrobić przez wyeksportowanie danych do Microsoft Excel i za pomocą tabel przestawnych, funkcja **Grupowanie w siatkach**, zasadniczo dostępna w wersji 10.0.16/aktualizacji platformy 40 i zależna od nowej funkcji kontroli siatki, umożliwia użytkownikom organizowanie swoich danych tabelarycznych w interesujący sposób w aplikacjach Finance and Operations. Ponieważ ta funkcja rozszerza funkcję **Sum**, **Grupowanie** umożliwia również uzyskanie istotnych informacji na temat danych przez zapewnienie sum częściowych na poziomie grupy.

Aby skorzystać z tej funkcji, kliknij prawym przyciskiem myszy kolumnę, według której chcesz grupować, a następnie wybierz polecenie **Grupuj według tej kolumny**. Ta akcja spowoduje posortowanie danych według wybranej kolumny, dodanie nowej kolumny **Grupy według** do początku do siatki, a następnie wstawienie „wierszy nagłówka” na początku każdej grupy. Te wiersze nagłówka zawierają następujące informacje o każdej grupie: 
-  Wartość danych dla grupy 
-  Nazwa kolumny (te informacje są szczególnie przydatne, gdy istnieje wiele poziomów grupowania)  
-  Liczba wierszy danych w tej grupie
-  Sumy cząstkowe dla dowolnej kolumny skonfigurowanej do wyświetlania sum

Przy włączonym [Zapisanym widoku](saved-views.md), grupowanie może zostać zapisane przez personalizację jako część widoku, aby uzyskać szybki dostęp przy następnym odwiedzaniu strony.  

### <a name="multiple-levels-of-grouping"></a>Wiele poziomów grupowania
Po zgrupowaniu danych według jednej kolumny można je pogrupować według innej kolumny, zaznaczając w żądanej kolumnie opcję **Grupuj według tej kolumny**. Ten proces można powtarzać aż do uzyskania 5 zagnieżdżonych poziomów grupowania, co jest maksymalną obsługiwaną głębokością. W tym momencie nie będzie już można grupować według dodatkowych kolumn.  

W dowolnym momencie można usunąć grupowanie według dowolnej kolumny, klikając prawym przyciskiem myszy tę kolumnę i wybierając polecenie **Rozgrupuj**. Można również usunąć grupowanie ze wszystkich kolumn, wybierając kolejno polecenia **Opcje siatki** i **Rozgrupuj wszystko**.   

Uwaga: przed wersją 10.0.16/aktualizacją platformy 40 jest obsługiwany tylko jeden poziom grupowania. W tych wersjach jeśli dane są pogrupowane i wybierzesz opcję **Grupuj według tej kolumny** dla innej kolumny, pierwotne grupowanie zostanie zastąpione.  


### <a name="expanding-and-collapsing-groups"></a>Rozwijanie i zwijanie grup
Początkowe grupowanie danych będzie miało rozwinięte wszystkie grupy. Podsumowane widoki danych można tworzyć, zwijając poszczególne grupy, a także rozwijając grupę i zwijając ją, aby ułatwić nawigację między danymi. Aby rozwinąć lub zwinąć grupę, wybierz przycisk pagonu (>) w odpowiednim wierszu nagłówka grupy. Należy pamiętać, że stan rozwijania/zwijania poszczególnych grup **nie jest** zapisywany w obszarze Personalizacja.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Zaznaczanie i odznaczanie wierszy na poziomie grupy
W taki sam sposób, w jaki można wybrać (lub usunąć zaznaczenie) wszystkie wiersze w siatce — zaznaczając pole wyboru u góry pierwszej kolumny w siatce — można również szybko zaznaczyć (lub usunąć zaznaczenie) wszystkich wierszy w grupie, zaznaczając pole wyboru w odpowiednim wierszu nagłówka grupy. Pole wyboru w wierszu nagłówka grupy zawsze odzwierciedla bieżący stan zaznaczenia wierszy w tej grupie, niezależnie od tego, czy zaznaczono wszystkie wierszy, nie zaznaczono wierszy lub wybrano tylko niektóre wiersze.

### <a name="hiding-column-names"></a>Ukrywanie nazw kolumn
Podczas grupowania danych domyślnym zachowaniem jest wyświetlenie nazwy kolumny w wierszu nagłówka grupy. Począwszy od wersji 10.0.14 z aktualizacją platformy 38 można wybrać opcję wyłączania nazwy kolumny w wierszach nagłówka grupy, wybierając **Opcje siatki** > **Ukryj nazwę kolumny grupy**.

## <a name="freezing-columns"></a>Zamrażanie kolumn
Niektóre kolumny w siatce mogą być na tyle ważne dla kontekstu, że nie powinny być przewijane w widoku. W zamian chcesz, aby wartości w tych kolumnach zawsze były widoczne. W wersji 10.0.17 funkcja **Zamroź kolumny w siatce** zapewnia użytkownikom tę elastyczność. 

Aby zamrozić kolumnę, kliknij prawym przyciskiem myszy nagłówek kolumny, a następnie wybierz polecenie **Zamroź kolumnę**. Gdy ten krok zostanie ukończony po raz pierwszy, wybrana kolumna stanie się pierwszą kolumną i nie będzie już przewijana w widoku. Każda kolejna zamrożona kolumna zostanie dodana po prawej stronie ostatniej zamrożonej kolumny. W celu zmiany kolejności zamrożonych kolumn można użyć standardowych funkcji przenoszenia. Jednak zamrożonych kolumn nie można przenieść, aby były widoczne wśród zestawu odmrożonych kolumn. Podobnie odmrożonych kolumn nie można przenieść, aby były widoczne wśród zestawu zamrożonych kolumn.

Aby odmrozić kolumnę, kliknij prawym przyciskiem myszy nagłówek zamrożonej kolumny, a następnie wybierz polecenie **Odmroź kolumnę**. 

Należy zauważyć, że wybór wierszy i kolumny stanu wiersza w nowej siatce są zawsze zamrożone jako pierwsze dwie kolumny. Dlatego kiedy te kolumny są zawarte w siatce, zawsze będą widoczne dla użytkowników, niezależnie od pozycji przewijania w poziomie w siatce. Nie można zmienić kolejności tych dwóch kolumn.

## <a name="frequently-asked-questions"></a>Często zadawane pytania
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Jak włączyć formant nowej siatki w środowisku? 

**10.0.9 / Aktualizacja Platform update 33 i nowsze**

Funkcja **Kontrolka nowej siatki** jest dostępna bezpośrednio w module Zarządzanie funkcjami w dowolnym środowisku. Podobnie jak inne funkcje prapremiery publicznej, włączenie tej funkcji w produkcji podlega [uzupełniającemu warunkowi stosowania umowy](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/Aktualizacja platformy 32 i 10.0.7/Aktualizacja platformy 31**

Funkcja **Kontrolka nowej siatki** można włączyć w środowiskach warstwy 1 (Dev/Test) i warstwa 2 (piaskownicy) w celu zapewnienia dodatkowych zmian w testowaniu i projekcie, wykonując poniższe kroki.

1.  **Włącz funkcję testową**: wykonaj następującą instrukcję SQL: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Zresetuj usługi IIS**, aby opróżnić statyczną dystrybucję testową pamięci podręcznej. 

3.  **Znajdź funkcję**: przejdź do obszaru roboczego **Zarządzanie funkcjami**. Jeśli **Formant nowej siatki** nie jest wyświetlana na liście wszystkich funkcji, wybierz opcję **Sprawdź aktualizacje**.   

4.  **Włącz funkcję**: Znajdź funkcję **Formant nowej siatki** na liście funkcji i wybierz przycisk **Włącz teraz** w okienku szczegółów. Zauważ, że jest wymagane odświeżenie przeglądarki. 

Wszystkie kolejne sesje użytkownika będą uruchamiane z włączonymi formantami nowej siatki.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Deweloper] Rezygnacja z używania nowej siatki dla poszczególnych stron 
Jeśli Twoja organizacja odkryje stronę, na której występują pewne problemy z wykorzystaniem nowej siatki, począwszy od wersji 10.0.13/Aktualizacji platformy 37 dostępny jest interfejs API, który umożliwia indywidualnemu formularzowi korzystanie ze starszej kontroli sieci, jednocześnie zezwalając reszcie systemu na korzystanie z nowej kontroli sieci. Aby wycofać pojedynczą stronę z nowej siatki, należy dodać następujący wpis wywołania `super()` w metodzie `run()` dla formularza.

 ```this.forceLegacyGrid();```

Ten interfejs API będzie uznawany do wydania w październiku 2021, gdy nowa kontrolka siatki stanie się wymagana. Jeśli jakiekolwiek problemy wymagają użycia tego interfejsu API, należy zgłosić je do rozwiązania Microsoft.

## <a name="developer-size-to-available-width-columns"></a>[Deweloper] Kolumny od rozmiaru do dostępnej szerokości
Jeśli projektant ustawi właściwość **WidthMode** na **SizeToAvailable** dla kolumn w nowej siatce, te kolumny mają początkowo taką samą szerokość, jaką miałyby w przypadku ustawienia właściwości na **SizeToContent**. Jednak rozciągają się one na użycie dowolnej dodatkowej szerokości w siatce. Jeśli właściwość jest ustawiona jako **SizeToAvailable** dla wielu kolumn, wszystkie te kolumny mają dowolną dodatkową szerokość w siatce. Jeśli jednak użytkownik ręcznie zmieni rozmiar jednej z tych kolumn, kolumna stanie się statyczna. Pozostanie on o tej samej szerokości i nie będzie już rozciągany, aby uzyskać dodatkową szerokość siatki.  

## <a name="known-issues"></a>Znane problemy
Ta sekcja zawiera listę znanych problemów związanych z nową kontrolą siatki.  

### <a name="open-issues"></a>Otwarte problemy
-  Po włączeniu funkcji **Kontrolka nowej siatki** niektóre strony będą nadal korzystać z istniejącej kontrolki siatki. Ma to miejsce w następujących sytuacjach:  
    -  Na stronie, która jest renderowana w wielu kolumnach, istnieje lista kart.
    -  Na stronie istnieje lista zgrupowanych kart.
    -  Kolumna siatkowa z niereagującą, rozszerzalną kontrolą.

    Gdy użytkownik po raz pierwszy napotka jedną z tych sytuacji, zostanie wyświetlony komunikat o odświeżeniu strony. Po wyświetleniu tego komunikatu strona będzie nadal wykorzystywać istniejącą siatkę dla wszystkich użytkowników, aż do następnej aktualizacji wersji produktu. Lepsza obsługa tych scenariuszy, dzięki czemu może być wykorzystywana nowa siatka, będzie brana pod uwagę podczas przyszłej aktualizacji.    
    
-  [KB 4582758] Rekordy są zamazane po zmianie powiększenia ze 100 na dowolną inną wartość procentową
-  [KB 4592012] Nieoczekiwany błąd klienta w programie IE11 podczas wklejania wielu wierszy z programu Excel
    -  Microsoft nie przygotowuje poprawki dla tego problemu

### <a name="fixed-as-part-of-10016"></a>Naprawiono w ramach 10.0.16

-  [KB 4598335] Kontrolki ciągu wielowierszowego nie są zgodne z ich wartościami DisplayHeights na listach/kartach 
-  [KB 4591891] Wiersze propozycji faktury znikają podczas cofania zaznaczenia wierszy
-  [KB 4592104] Nie można edytować rekordów po kliknięciu przycisku „Rozwiąż problem” i przeniesieniu do innego wiersza bez rozwiązania problemu z weryfikacją
-  [KB 4594449] W selektorze dat brakuje przycisków „Nigdy” i „Wyczyść” 
-  [KB 4594448] Czas wprowadzania w nowej siatce jest traktowany inaczej
-  [kb 4600059] Nieoczekiwany błąd klienta z ograniczeniem poczty e-mail
-  [KB 4574584] Podgląd załącznika wydatku jest niedostępny po umieszczeniu kursora na ikonie paragonu

### <a name="fixed-as-part-of-10015"></a>Naprawiono w ramach 10.0.15    

-  (Aktualizacja dotycząca jakości) [KB 4594444] Nieoczekiwany błąd klienta z podglądem dla kontrolki wpisów segmentowanych
-  [KB 4582723] Opcje wyświetlania nie są pokazywane przy próbie ich wybrania na dalszym etapie cyklu życia formularza
-  [KB 4591988] Problemy z klawiaturą podczas wybierania wartości z wyszukiwania ReferenceGroup
-  [KB 4588958] Test Regression Suite Automation Tool (RSAT) zakończył sie z błędem: TypeError: nNie można odczytać właściwości „text” elementów niezdefiniowanych
-  [KB 4591970] Nieoczekiwany błąd klienta, jeśli wklejanie danych z programu Excel zostało wykonane natychmiast po kliknięciu siatki
-  [KB 4591904] Zmiany danych nie są zapisywane, jeśli po edycji kontrolki użytkownik natychmiast kliknął i otworzył wyszukiwanie innej kontrolki
-  [KB 4584752] Nieoczekiwany błąd klienta po otwarciu strony Propozycje faktur projektu
-  [KB 4584540] Nie można wyjść z siatki po wklejeniu jednego wiersza w wierszu arkusza
-  [KB 4591908] Podczas tworzenia nowego wiersza uwaga jest koncentrowana na kolumnie, w której znajdował się użytkownik

### <a name="fixed-as-part-of-10014"></a>Naprawiono w ramach 10.0.14

-  (Aktualizacja jakości) [KB 4584752] Nieoczekiwany błąd na urządzeniu klienckim po otwarciu strony Propozycje faktur projektu
-  [KB 4583880] Testy w narzędziu Regression Suite Automation Tool (RSAT) kończą się niepowodzeniem na akcji OpenLookup, czemu towarzyszy komunikat „Nie można odczytać niezdefiniowanej właściwości RowIndex”
-  [KB 4583847] Nieoczekiwany błąd klienta podczas nawigowania po odnośnikach

### <a name="fixed-as-part-of-10013"></a>Naprawiono w ramach 10.0.13

-  (Aktualizacja jakości) [KB 4584752] Nieoczekiwany błąd na urządzeniu klienckim po otwarciu strony Propozycje faktur projektu
-  (Aktualizacja jakości) [KB 4583880] Testy w narzędziu Regression Suite Automation Tool (RSAT) kończą się niepowodzeniem na akcji OpenLookup, czemu towarzyszy komunikat „Nie można odczytać niezdefiniowanej właściwości RowIndex”
-  (Aktualizacja jakości) [KB 4583847] Nieoczekiwany błąd na urządzeniu klienckim podczas nawigowania po odnośnikach 
-  (Aktualizacja jakości) [Usterka 471777] Nie można wybrać pól w siatce do edytowania lub utworzenia aplikacji mobilnej
-  [KB 4582727] Siatka jest zamrażana po tym, jak użytkownik otworzy okno dialogowe dla pozycji z wieloma ilościami
-  [Usterka 474851] Hiperłącza w kontrolkach grup odwołań nie działają 
-  [Usterka 474848] Rozszerzone podglądy z siatkami nie są wyświetlane
-  [KB 4582726] Właściwość RotateSign nie jest respektowana  
-  [Usterka 470173] Pola wyboru w nieaktywnych wierszach przełączają się, gdy zostanie kliknięty odstęp w komórce
-  [Usterka 474848] Rozszerzone podglądy z siatkami nie są wyświetlane
-  [Usterka 474851] Hiperłącza w kontrolkach grup odwołań nie działają 
-  [Usterka 471777] Nie można wybrać pól w siatce do edytowania lub utworzenia aplikacji mobilnej
-  [KB 4569441] Problemy z renderowaniem wielokolumnowych list kart, etykiet narzędzi na obrazach oraz opcji wyświetlania w niektórych polach
-  [KB 4575279] Nie wszystkie oznaczone wiersze są usuwane z arkusza finansowego
-  [KB 4575233] Opcje wyświetlania nie są przywracane po przeniesieniu do innego wiersza
-  [Usterka 477884] Wyszukiwania zwracają nieprawidłową wartość/rekord, jeśli uaktywniono nową kontrolkę siatki
-  [KB 4571095] Księgowanie przyjęcia produktu następuje po przypadkowym naciśnięciu klawisza Enter (poprawna obsługa domyślnej akcji strony)
-  [KB 4575437] Wyszukiwania z edytowalnymi kontrolkami są nieoczekiwanie zamykane
-  [KB 4569418] Zduplikowany wiersz utworzony w formularzu harmonogramu dostaw
-  [KB 4575435] Rozszerzony podgląd czasem utrzymuje się nawet wtedy, gdy wskaźnik myszy nie znajduje się w pobliżu pola
-  [KB 4575434] Wyszukiwanie nie jest filtrowane, jeśli pole zostało zmodyfikowane
-  [KB 4575430] Wartości w polach haseł nie są maskowane w siatce
-  [KB 4569438] „Przetwarzanie zostało zatrzymane z powodu problemów z weryfikacją” powoduje wyświetlenie po zaznaczeniu wierszy podczas rozliczania transakcji dostawców
-  [KB 4569434] Odświeżenie formularza firmy powoduje zmniejszenie liczby rekordów
-  [KB 4575297] Podczas edycji i przełączania fokusu do okienka Rejestratora zadań jest zachowywane przejście na siatkę
-  [KB 4566773] Informacje o transakcjach korekty, które nie są wyświetlane jako ujemne w zapytaniu transakcji dotyczących załącznika 
-  [KB 4575288] Fokus jest ustawiany na aktywny wiersz podczas wybierania obramowania między wierszami na prostej liście
-  [KB 4575287] Fokus nie jest powracany do pierwszej kolumny przy użyciu klawisza strzałka w dół w celu utworzenia nowego wiersza w arkuszach
-  [KB 4564819] Nie można usunąć wierszy z faktury niezależnej (ponieważ źródło danych właściwość ChangeGroupMode=ImplicitInnerOuter)
-  [KB 4563317] Podpowiedzi/ulepszone podglądy nie są wyświetlane w przypadku obrazów

### <a name="fixed-as-part-of-10012"></a>Naprawiono w ramach 10.0.12

- [KB 4558545] Kontrolki tabeli nie aktualizują zawartości wyświetlanych pozycji.
- [KB 4558570] Po usunięciu rekordu towary są nadal wyświetlane na stronie.
- [KB 4558572] Style skojarzone z Panelem listy **ExtendedStyle** nie są stosowane.
- [KB 4558573] Nie można ustalić błędów sprawdzania poprawności, jeśli wymagana zmiana znajduje się poza siatką.
- [KB 4558584] Liczby ujemne są niepoprawnie renderowane.
- [KB 4560726] Wystąpił komunikat „nieoczekiwany błąd klienta”, gdy wymiana list odbywa się za pomocą kontrolki Widoku listy.
- [KB 4562141] Indeksy siatki są wyłączone po dodaniu nowego rekordu.
- [KB 4562151] Opcje Rejestratora zadań **Sprawdź** i **Kopiuj** nie są dostępne dla kontrolek daty/numeru. 
- [KB 4562153] Pola wielokrotnego wyboru nie są widoczne w przypadku siatek list/kart.
- [KB 4562646] Sporadycznie nie można kliknąć poza siatką po wybraniu wielu wierszy w siatce.
- [KB 4562647] Po dodaniu nowego wiersza do siatki ról zabezpieczeń fokus jest resetowany do pierwszej kontrolki w oknie dialogowym **Publikuj**.
- [KB 4563310] Rozszerzony podgląd nie jest zamykany po zmianie wiersza.
- [KB 4563313] W przypadku wybrania wartości w wyszukiwaniu w Internet Explorer występuje błąd „nieoczekiwany klient”.
- [KB 4564557] Listy wyszukiwania i rozwijane menu nie są otwierane w Internet Explorer
- [KB 4563324] Nawigacja nie działa po otwarciu obszaru roboczego **Zarządzanie personelem**.

### <a name="fixed-as-part-of-10011"></a>Naprawiono w ramach 10.0.11

- [Rozchód 432458] Puste lub zduplikowane wiersze są wyświetlane na początku niektórych zbiorów podrzędnych.
- [KB 4549711] Nie można poprawnie usunąć wierszy z propozycji płatności po włączeniu nowej kontrolki siatki.
- [KB 4558374] Nie można utworzyć rekordów wymagających okna dialogowego wyboru polimorficznego.
- [KB 4558375] Tekst pomocowy nie jest pokazywany w kolumnach w nowej siatce.
- [KB 4558376] Siatki Panelu list nie są renderowane na poprawnej wysokości w Internet Explorer.
- [KB 4558377] Kolumny pola kombi o szerokości **SizeToAvailable** nie są renderowane na niektórych stronach.
- [KB 4558378] Funkcja drążenia wskroś czasami powoduje otwarcie niewłaściwego rekordu.
- [KB 4558379] Wystąpił błąd podczas otwierania wyszukiwań, gdzie **ReplaceOnLookup**=**No**.
- [KB 4558380] Dostępne miejsce w siatce nie jest wypełniane natychmiast po zwinięciu części strony.
- [KB 4558381] Liczby ujemne nie są renderowane prawidłowo/użytkownicy mogą być wyrzucani po napotkaniu problemów z weryfikacją.
- [KB 4558382] Wystąpił nieoczekiwany błąd klienta.
- [KB 4558383] Kontrolki poza siatką nie są aktualizowane po usunięciu ostatniego rekordu.
- [KB 4558587] Grupy odwołań z polami kombi przeznaczonymi do zamiany nie są wyświetlane wartości.
- [KB 4562143] Pola nie są aktualizowane, gdy przetwarzanie zmian w wierszu/siatce zostanie zablokowane po usunięciu wiersza.
- [KB 4562645] Wyjątek występuje podczas otwierania wyszukiwania podczas wykonywania testów w narzędziu Regression Suite Automation Tool (RSAT).

### <a name="fixed-as-part-of-10010"></a>Naprawiono w ramach 10.0.10

- [Problem 414301] Niektóre dane z poprzednich wierszy znikają podczas tworzenia nowych wierszy.
- [Usterka 417044] Brak pustych komunikatów siatki dla siatek w stylu listy.
- [KB 4539058] Czasami niektóre siatki (zwykle na kartach skróconych) nie są renderowane (ale będą renderowane w przypadku pomniejszenia).
- [KB 4549734] Aktywne wiersze nie są traktowane jako zaznaczone, jeśli kolumna oznaczania jest ukryta.
- [KB 4549796] Nie można edytować wartości w siatce, gdy jest ona w trybie widoku.
- [KB 4558367] Po zmianie wierszy wybór tekstu jest niespójny.
- [KB 4558368] Wielokrotne wybieranie za pośrednictwem klawiatury jest dozwolone w scenariuszach pojedynczego wyboru.
- [KB 4558369] W siatce hierarchicznej znikają obrazy stanu.
- [KB 4558370] Nowy wiersz nie jest przewijany do widoku.
- [KB 4558372] Nowa siatka zostanie zablokowana w trybie przetwarzania, jeśli liczba kolumn w wklejanej zawartości przekracza liczbę pozostałych kolumn w siatce.
- [KB 4562631] Wartości czasu nie są poprawnie sformatowane.

### <a name="quality-update-for-1009platform-update-33"></a>Aktualizacja jakości dla 10.0.9/aktualizacja Platform update 33

- [KB 4550367] Wartości czasu nie są poprawnie sformatowane.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
