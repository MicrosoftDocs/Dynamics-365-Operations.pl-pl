---
title: "Struktury podziału pracy"
description: "Struktura podziału pracy (SPP) to opis pracy, która zostanie wykonana w ramach projektu. Jest to hierarchia zadań ustalona przez zespół na podstawie koniecznej pracy, zakresu, kosztu i czasu trwania każdego ze składników lub zadań."
author: KimANelson
manager: AnnBe
ms.date: 06/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWorkBreakdownStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23861
ms.assetid: 241a0464-0056-4a69-b468-0afbe2d5f3ae
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fc2fa16a44b6421d56e9cb662cfaa26da5b1c5d1
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="work-breakdown-structures"></a>Struktury podziału pracy

[!include[banner](../includes/banner.md)]

Struktura podziału pracy (SPP) to opis pracy, która zostanie wykonana w ramach projektu. Jest to hierarchia zadań ustalona przez zespół na podstawie koniecznej pracy, zakresu, kosztu i czasu trwania każdego ze składników lub zadań. SPP pełni trzy główne funkcje:

-   Opis podziału lub kompozycji pracy w zadaniach.
-   Planowanie pracy w ramach projektu.
-   Szacowanie kosztów każdego zadania.

Stopień szczegółowości w SPP zależy od poziomu dokładności, jaki jest wymagany w szacunkach i poziomu śledzenia, który jest wymagany dla tych oszacowań. Projekty o bardzo małej tolerancji na opóźnienia harmonogramu czy wahania kosztów zazwyczaj wymagają bardziej szczegółowych SPP i dokładnego monitorowania postępów pracy i kosztów względem SPP. Ten typ projektu jest często stosowany w branżach budowlanych i inżynieryjnych. 

Dla odmiany, projekty w branżach, takich jak media i reklama, IT są zazwyczaj jednego typu a wydajność zależy od doświadczenia i kompetencji osób wykonujących zadania. Z tego względu w takich branżach wykorzystuje się SPP do określenia przybliżonej wielkości projektu, a nie do szczegółowego monitorowania jego postępów. 

Tworzenie SPP to intensywny proces, który zazwyczaj trwa długo i wymaga współpracy oraz przekazywania informacji między dużą grupą osób. W tym temacie opisujemy, jak można wykorzystać udoskonalenia wprowadzone do funkcji SPP w programie Microsoft Dynamics 365 for Finance and Operations, aby ułatwić sobie szacowanie i monitorowanie w projekcie.

## <a name="prerequisites-for-creating-a-wbs"></a>Wymagania wstępne dotyczące tworzenia SPP
Aby utworzyć SPP, konieczne jest utworzenie harmonogramu pracy i oszacowanie jej kosztów.

### <a name="prerequisites-for-creating-a-work-schedule"></a>Wymagania wstępne dotyczące tworzenia harmonogramu pracy

Aby korzystać w pełni możliwości planowania w funkcjach SPP, należy wprowadzić następujące ustawienia:

1.  Ustaw domyślny kalendarz i kalendarz projektu:
    1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie projektami i ich księgowanie** &gt; **Planowanie**. W polu **Domyślny kalendarz pracy** określ domyślny kalendarz. Będzie to domyślny kalendarz pracy dla każdego nowo tworzonego projektu.
    2.  Można zmienić kalendarz domyślny dla określonego projektu. Kliknij stronę szczegółów projektu, a następnie na skróconej karcie **Zespół projektu i planowanie** zaktualizuj pole **Kalendarz planowania**, wybierając inny kalendarz.

2.  Ustaw standardowe dni robocze i godziny pracy. Kalendarz, który zostanie ustawiony jako roboczy dla projektu, będzie używany w SPP do określenia następujących informacji:

-   Dni robocze i dni wolne od pracy
-   Liczba godzin pracy w dniu

Aby ustawić dni i godziny pracy w kalendarzu lub utworzyć nowy kalendarz, kliknij kolejno opcje **Administrowanie organizacją** &gt; **Wspólne** &gt; **Kalendarze**.

### <a name="prerequisites-for-estimating-the-cost-of-work"></a>Wymagania wstępne dotyczące oszacowania kosztów pracy

Aby korzystać z pełnej funkcjonalności szacowania kosztów SPP, należy ustawić koszty i płace pracowników, kategorie pracy, wydatki, opłaty i towary.

-   Aby ustawić koszt i cenę robocizny, wydatki i kategorie opłat, kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Ceny**.
-   Aby skonfigurować koszt i ceny sprzedaży towarów, przejdź na stronę **umów handlowych** stronę dla każdego elementu na stronie listy **zwolnionych produktów** w module Zarządzanie informacjami o produktach.

## <a name="creating-a-wbs"></a>Tworzenie SPP
Tworzenie SPP składa się z trzech czynności:

1.  **Rozkład pracy** — dzielenie pracy na możliwe do zarządzania fragmenty lub zadania.
2.  **Plan roboczy** — oszacuj czas potrzebny na wykonanie zadania, ustaw wzajemne relacje między zadaniami i wybierz daty rozpoczęcia i zakończenia zadań.
3.  **Szacowanie kosztów** — oszacuj koszty dla każdego zadania.

W następujących sekcjach omówiono, w jaki sposób możliwości SPP pomagają w każdym z tych działań.

### <a name="work-decomposition"></a>Dekompozycja pracy

Tworzenie podziału lub dekompozycji pracy jest zwykle pierwszym krokiem w procesie tworzenia SPP. Funkcja SPP obsługuje następujące podstawowe elementy podziału pracy: 

**Główne zadanie projektu** — zadanie najwyższego poziomu podsumowania w projekcie. Wszystkie inne zadania projektu są tworzone na niższych poziomach. Nazwa zadania głównego jest zawsze nazwą projektu. Nakład pracy, daty i czas trwania węzła głównego to suma wartości zadań podrzędnych względem głównego zadania. Nie można zmodyfikować właściwości węzła głównego ani go usunąć.

**Zadania podsumowania lub kontenera** zadanie podsumowania to zadanie, które składa się z zadań niższego poziomu lub ma elementy składowe. Zadanie podsumowania samo w sobie nie ma przypisanej żadnej pracy ani kosztów. Zamiast tego nakład pracy i koszt zadania podsumowania są sumą nakładów pracy i kosztów zadań wchodzących w jego skład. Najwcześniejsza data rozpoczęcia zadania składowego jest datą rozpoczęcia zadania podsumowania, a najpóźniejsza data zadania składowego to data zakończenia zadania podsumowania. Nazwę zadania podsumowania można zmienić, ale nie można zmienić jego właściwości harmonogramu dla nakładów pracy, dat i czasu trwania. Usunięcie zadania podsumowania powoduje usunięcie wszystkich jego zadań składowych. 

**Zadania węzła liścia** określa najbardziej szczegółowy pakiet prac w projekcie. Węzeł liścia ma szacowany nakład pracy, planowaną liczbę zasobów, planowane daty rozpoczęcia i zakończenia oraz czas trwania. 

Można wykonać następujące operacje hierarchii w celu umożliwienia tworzenia hierarchii pracy lub dekompozycji projektu. 

**Nowe zadanie** nowo tworzone zadanie zostanie automatycznie dodane do węzła głównego, a numer SPP zostanie automatycznie przypisany do zadania. Numer SPP odzwierciedla poziom zadania w hierarchii. W przypadku zadań pierwszego poziomu pod zadaniem głównym w projekcie używa się schematu 1, 2, 3 itd. W przypadku zadań pod pierwszym poziomem używa się schematu 1.1, 1.2, 1.3 itd. Dla każdego poziomu, który zostanie dodany w obszarze poprzedniego poziomu, dodawana jest nowa seria z podpunktami. 

Obecnie nie można dostosowywać numerowania SPP. 

**Wcinanie zadania** kiedy wcinasz zadanie, staje się ono zadaniem podrzędnym w stosunku do zadania, które je poprzedza. Numer nowego zadania podrzędnego SPP jest automatycznie ponownie wyliczany na podstawie numeru SPP jego nowego zadania nadrzędnego. Zadanie nadrzędne jest teraz zadaniem podsumowania lub kontenera i dlatego staje się zadaniem zbiorczym dla zadań wchodzących w jego skład. 

> [!NOTE] 
> Jeśli wcinasz zadanie pod zadaniem, które wcześniej było węzłem liścia, nowo utworzone zadanie podsumowania traci własne daty, nakład pracy i liczbę zasobów. Używa teraz podsumowania wartości nowych zadań składowych. 

**Wycinanie zadania** po wycięciu zadania przestaje ono być częścią składową swojego zadania nadrzędnego. Numer SPP tego zadania jest automatycznie ponownie wyliczany, tak aby odzwierciedlał nowy poziom zadania w hierarchii. Nakład pracy, koszt i daty zadania nadrzędnego wobec wyciętego są ponownie przeliczane z wykluczeniem tego zadania. 

**Przenieś w górę i Przenieś w dół** klikając polecenia **Przenieś w górę** i **Przenieś w dół**, można zmienić położenie zadania w ramach jego elementu nadrzędnego hierarchii. Położenie zadania nie wpływa na nakład pracy, koszt, daty lub czasu trwania zadania. Ale numer SPP tego zadania jest automatycznie ponownie wyliczany, tak aby odzwierciedlał jego nowe położenie.

### <a name="schedule-estimation"></a>Szacowanie harmonogramu

Szacowanie harmonogramu zazwyczaj jest to drugi etap w tworzeniu SPP. Zaleca się wykonywanie tego kroku po utworzeniu zadań. Strona **Struktury podziału pracy** w programie Finance and Operations składa się z dwóch części. Górne okienko jest przeznaczone do szacowania harmonogramu, a dolne zawiera kartę **szacowane koszty i dochody**, której można użyć do szacowania kosztów. 
**Zależności zadania** w SPP można utworzyć relację z zadaniem poprzedzającym. Po przypisaniu zadania poprzedzającego do zadania, zadanie to można uruchomić tylko po ukończeniu wszystkich zadań poprzedzających. Planowana data rozpoczęcia zadania jest ustawiana automatycznie jako najpóźniejsza data zakończenia wszystkich jego zadań poprzedzających. 

**Planowanie zadań w programie Microsoft Dynamics 365 for Finance and Operations** Następujące czynniki określają planowanie zadań węzła liścia:

-   Poprzedniki
-   Nakład pracy
-   Liczba zasobów
-   Daty rozpoczęcia i zakończenia

Data rozpoczęcia zadania węzła liścia, które nie zawiera zadań poprzedzających, jest automatycznie ustawiane jako data rozpoczęcia w harmonogramie projektu. Czas trwania zadania węzła liścia jest zawsze obliczany jako liczba dni roboczych pomiędzy jego datami rozpoczęcia i zakończenia. 

****Reguły planowania**** Po włączeniu asysty automatycznego planowania stosowane są następujące reguły planowania zadań dla zadań węzła liścia:

-   Daty rozpoczęcia i zakończenia zadania muszą być dniami roboczymi, zgodnie z kalendarzem harmonogramu projektu.
-   Planowana data rozpoczęcia zadania, które ma zadania poprzedzające, jest ustawiana automatycznie jako najpóźniejsza data zakończenia wszystkich jego zadań poprzedzających.
-   Nakład pracy dla zadania jest automatycznie obliczana w następujący sposób:

Liczba osób x czas trwania x liczba godzin w standardowym dniu roboczym w kalendarzu projektu 

W niektórych przypadkach może zaistnieć potrzeba odchylenia od tych reguł. Można wyłączyć automatyczne planowanie, aby uniemożliwić programowi Finance and Operations automatyczne ustawianie lub poprawianie właściwości zadania węzła liścia. Po wprowadzeniu informacji dla zadania, która powoduje naruszenie reguły planowania, w zadaniu jest wyświetlana ikona błędu harmonogramu. Jeśli nie chcesz, żeby błędy harmonogramu były wyświetlane, kliknij przycisk **Błędy planowania są wyświetlane**, aby wyłączyć tę funkcję. 

> [!NOTE] 
> Wartości dla zadania podsumowania lub kontenera nadal będą liczone jako suma wartości zadań składowych, niezależnie od tego, czy asysta automatycznego planowania jest włączona, czy nie. 

**Naprawianie błędów planowania** po włączeniu asysty automatycznego planowania błędy planowania nie będą wyświetlane. Jeśli wyłączysz asystę automatycznego planowania, a potem znowu ją włączysz, mogą znowu pojawiać się błędy planowania w SPP. 

**Naprawianie błędów planowania według zadań** po dwukrotnym kliknięciu ikony błędu harmonogramu dla określonego zadania, zostanie wyświetlone okno dialogowe ze wszystkimi błędami planowania dla tego zadania. Można określić, które błędy planowania należy skorygować dla zadania. 

**Naprawianie wszystkich błędów planowania** jeśli chcesz, żeby program Finance and Operations naprawił wszystkie błędy w SPP, w okienku akcji kliknij **Korygowanie wszystkich rozbieżności planowania**. 

> [!NOTE] 
> Ta funkcja może spowodować wprowadzenie istotnych zmian w SPP. Błędy są naprawiane w następującej kolejności:

1.  Szacowany nakład pracy nad wszystkimi zadaniami jest zmieniany, tak aby był równy zdolnościom produkcyjnym zdefiniowanym w kalendarzu projektu.
2.  Data rozpoczęcia każdego zadania jest modyfikowana tak, aby dane zadanie było rozpoczynane po zakończeniu wszystkich jego zadań poprzedzających.
3.  Data rozpoczęcia każdego zadania jest zmieniana tak, aby usunąć luki w datach rozpoczęcia zadań poprzedzających.

### <a name="cost-estimation"></a>Szacowanie kosztów

Jak wspomniano wcześniej w tym dokumencie, oszacowanie kosztów wprowadza się dla każdego zadania węzła liścia przy użyciu karty **szacowane koszty i dochody** w dolnym okienku strony **struktury podziału pracy**. 

> [!NOTE] 
> Nie można zmodyfikować oszacowania kosztów dla zadania podsumowania lub kontenera. Szacowanie kosztów dla zadania podsumowania jest równe sumie oszacowań kosztów jego zadań węzła liścia. Szacowany całkowity koszt dla każdego zadania jest obliczany jako suma kwot szacowanych kosztów dla następujących typów transakcji:

-   Praca
-   Towarów lub materiałów
-   Koszty

Typ transakcji **opłaty** jest używany do szacowania przychodów na podstawie opłat. Ten typ transakcji nie ma składnika kosztów i dlatego nie jest brany pod uwagę podczas są szacowania kosztów. 

Typ transakcji **akonto** służy do rejestrowania wartości sprzedaży określonej w umowie w projekcie o stałej wartości. Ten typ transakcji też nie jest brany pod uwagę podczas szacowania kosztów. 

Podczas szacowania kosztów pracy, materiałów i wydatków dla każdego zadania trzeba przypisać kategorię projektu do szacowanego kosztu. 

**Oszacowania kosztów robocizny** dla każdego zadania węzła liścia należy przypisać robociznę w godzinach i domyślną kategorię. W związku z tym podczas konfigurowania harmonogramu zadania oszacowany koszt robocizny jest automatycznie dodawany do domyślnej kategorii dla robocizny. To oszacowanie kosztów jest wyświetlane na karcie **szacowane koszty i przychód** w siatce **szczegóły wiersza** dla tego zadania. Jeśli potrzebujesz więcej szacowanych kosztów pracy, możesz dodać je na tej karcie. Jeśli zwiększasz lub zmniejszasz godziny w oszacowaniu kosztów robocizny, harmonogram zadania jest przeliczany automatycznie. 

**Oszacowania wydatków i kosztów materiałów** Na karcie **Szacowane koszty i przychód** można także oszacować wydatki i koszty materiałów dla zadania. 

Koszt własny i cena sprzedaży dla każdego wiersza oszacowania robocizny lub wydatku opiera się na ustawieniach zdefiniowanych dla każdej kategorii w cennikach na stronie **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Ceny**. W przypadku towarów koszt i cena sprzedaży są dodawane domyślnie z umów dotyczących towarów lub handlowych na stronie listy **Zwolnione produkty** w module Zarządzanie informacjami o produktach.

## <a name="tracking-progress-on-the-wbs"></a>Monitorowanie postępu w SPP
W niektórych branżach śledzi się postęp projektu względem SPP na bardzo szczegółowym poziomie, a w innych na wyższych poziomach SPP. W tej sekcji opisano sposób korzystania ze śledzenia SPP dla wymagań projektu. 

W programie Finance and Operations są dostępne trzy widoki dla SPP projektu: widok planowania, widok śledzenia robocizny i widok śledzenia kosztów.

### <a name="planning-view"></a>Widok planowania

Widok planowania pokazuje planowane lub podstawowe oszacowanie harmonogramu i kosztów. Mimo że nie istnieją żadne funkcje śledzenia wersji i bazy SPP projektu, wartości w tym widoku odzwierciedlają wersję podstawową. Sekcje szacowania harmonogramu i kosztów sekcje w tym temacie opisują ten widok i pokazują, jak jest używany do tworzenia SPP.

### <a name="effort-tracking-view"></a>Widok śledzenia nakładu pracy

Śledzenie nakładu pracy pokazuje postęp zadań w SPP. Porównuje skumulowane rzeczywiste nakłady pracy w godzinach dla zadania z planowanym nakładem pracy. Poniższe formuły zawierają wartości w widoku śledzenia nakładu pracy:

-   Procent postępu = Rzeczywisty nakład pracy do dnia ÷ planowany nakład pracy dla zadania.
-   Pozostały nakład pracy (określany także jako oszacowania do zakończenia \[ETC\]) = Planowany nakład pracy — Rzeczywisty nakład pracy do dnia
-   Końcowy szacunek (EAC) = Rzeczywisty nakład pracy do dnia + Pozostały nakład pracy
-   Prognozowane odchylenie nakładu pracy = planowany nakład pracy — EAC

Widok śledzenia nakładu pracy pokazuje prognozę odchylenia nakładu pracy dla zadania na podstawie tego, czy EAC ma wartość większą lub mniejszą niż planowany nakład pracy:

-   Jeśli wartość EAC jest większa niż planowany nakład pracy, zadanie może trwać dłużej niż pierwotnie zaplanowane i jest opóźnione względem harmonogramu.
-   Jeśli wartość EAC jest mniejsza niż planowany nakład pracy, zadanie może trwać krócej niż pierwotnie zaplanowane i wyprzedza harmonogram.

**Ponowna projekcja menedżera projektu dotycząca nakładów pracy** od czasu do czasu menedżer projektu lub inna osoba śledząca postęp projektu, musi zmienić oryginalne oszacowania dla zadań. Wykonanie zadania może z różnych przyczyn przebiegać szybciej lub wolniej niż pierwotnie zakładano. Na przykład, gdy zakres zadania został ograniczony lub pracownicy mają mniej doświadczenia niż oryginalnie zaplanowano. Prognozy są punktem widzenia menedżera projektu na oszacowania na podstawie bieżącego stanu projektu. Ogólnie nie należy zmieniać podstawowych liczb, ponieważ podstawy projektu odzwierciedlają dane w opublikowanym dokumencie harmonogramu projektu i oszacowaniach kosztów, na które wyraziły zgodę wszystkie osoby zaangażowane w projekt. 

Istnieją dwa sposoby modyfikacji przez menedżerów projektu nakładów pracy w zadaniach:

-   Modyfikowanie pozostałego nakładu pracy, które jest ustawione pod kątem automatycznej aktualizacji pozostałej robocizny w zadaniu.
-   Modyfikowanie pozostałego nakładu pracy, które jest ustawione pod kątem automatycznej aktualizacji pozostałej robocizny w zadaniu.

Każda z tych metod powoduje ponowne obliczenie ETC, EAC, postępu procentowego i prognozowanej wariancji nakładu pracy dla zadania. EAC, ETC i procent postępu zadania podsumowania są także przeliczane, a ich prognozowane odchylenie nakładu pracy zostanie zaktualizowane. 

**Zmodyfikowany nakład pracy w zadaniu podsumowania** można zmodyfikować nakład pracy dla zadań podsumowania lub kontenera. Niezależnie od tego, czy zmieniasz te wartości za pomocą pozostałego nakładu pracy czy procenta postępu w zadaniach podsumowania, obliczenia są wykonywane automatycznie w następującej kolejności:

1.  Obliczane są EAC, ETC i procent postępu zadania.
2.  Nowa wartość EAC jest przekazywana do zadań podrzędnych w takiej samej proporcji jak pierwotna kwota EAC.
3.  Obliczana jest nowa wartość EAC w poszczególnych węzłach liścia zadania.
4.  Pozostały nakład pracy i procent postępu zostaną ponownie obliczone dla wszystkich zadań podrzędnych, których dotyczą, na podstawie nowej wartości EAC. Odchylenie nakładu pracy zadań jest również ponownie obliczane.
5.  Następuje również ponowne obliczenie EAC zadań podsumowania z węzłów liścia.

Kliknij **Rozwiń do poziomu** w widoku śledzenia nakładów pracy, aby ustawić poziom, na którym będzie śledzony i zachowany SPP. Struktura podziału pracy jest automatycznie dodawana do tego poziomu w widoku śledzenia nakładów pracy przy każdym jego otwarciu.

### <a name="cost-tracking-view"></a>Widok śledzenia kosztów

Widok śledzenia kosztów pokazuje zużycie kosztów w zadaniu. W tym widoku koszt rzeczywisty wydany na realizację zadania do dnia jest porównywany z planowanym kosztem zadania. Poniższe formuły zawierają wartości w widoku śledzenia kosztu:

-   Procent wykorzystania kosztu = koszt rzeczywisty do dnia / koszt planowany dla zadania.
-   Koszt ukończenia (CTC) = Planowany koszt – rzeczywisty koszt do dnia
-   Szacowany koszt końcowy (EAC) = CTC + rzeczywisty koszt do dnia
-   Prognozowane odchylenie kosztowe = Koszt planowany — EAC

Widok śledzenia kosztu pokazuje prognozę odchylenia kosztu dla zadania na podstawie tego, czy EAC ma wartość większą lub mniejszą niż planowany koszt:

-   Jeśli wartość EAC jest większa niż planowany koszt, zadanie może wymagać wydania większej sumy pieniędzy niż pierwotnie zaplanowano w budżecie.
-   Jeśli wartość EAC jest mniejsza niż planowany koszt, zadanie może wymagać wydania mniejszej sumy pieniędzy niż pierwotnie zaplanowano w budżecie.

**Ponowna projekcja menedżera projektu dotycząca kosztów** menedżer projektu musi użyć CTC do przejrzenia oszacowania pierwotnego kosztu zadania. Menedżer projektu może zmodyfikować wartość CTC do kosztu wymaganego do zakończenia zadania. W przypadku zmodyfikowania wartości CTC, jego CTC, EAC, procent wykorzystania kosztu i prognozowane odchylenie kosztów dla zadania, zostaną ponownie obliczone. EAC, ETC i procent wykorzystania kosztu zadania podsumowania są także przeliczane, a ich prognozowane odchylenie kosztu zostanie zaktualizowane. 

> [!NOTE] 
> Podczas korygowania nakładu pracy dla zadania SPP w widoku śledzenia nakładu pracy jego CTC, EAC, wartość procentowa kosztu, zużycie i prognozowane odchylenie kosztów są ponownie obliczane w widoku śledzenia kosztów. Jednak korekty kosztu nie wpływają na wartości w widoku śledzenia nakładu pracy, ponieważ nie jest skorygowany koszt według typu transakcji (robocizny, materiałów lub wydatków) lub kategorii projektu. 

**Korekta prognozy kosztów zadania podsumowania** można skorygować koszty na zadań podsumowania. Obliczenia będą wykonywane automatycznie w następującej kolejności:

1.  Przeliczane są EAC CTC, procent wykorzystanych kosztów w zadaniu.
2.  Nowa wartość EAC jest przekazywana do zadań podrzędnych w takiej samej proporcji jak pierwotna kwota EAC.
3.  System oblicza nową wartość EAC dla każdego zadania.
4.  CTS i procent wykorzystanego kosztu są ponownie obliczane dla odpowiednich zadań podrzędnych na podstawie wartości EAC. Odchylenie kosztu zadań jest również ponownie obliczane.
5.  EAC dla zadań podsumowania oblicza się na podstawie tej zmiany.

Kliknij **Rozwiń do poziomu** w widoku śledzenia kosztów, aby ustawić poziom, na którym będzie śledzony i zachowany SPP. Struktura podziału pracy jest automatycznie dodawana do tego poziomu w widoku śledzenia kosztów przy każdym jego otwarciu.

### <a name="earned-value-management"></a>Zarządzanie uzyskanymi wartościami

Można używać metody wartości wypracowanej (EVM) do śledzenia postępu projektu. Mierniki uzyskanej wartości można zobaczyć w widoku głównym menedżera projektu. Wykres uzyskanej wartości przedstawia wartości okresowe wartości planowanych i rzeczywistych kosztów. Uzyskana wartość dla bieżącego dnia jest wskazana jako punkt. Uzyskana wartość danych okresowych nie jest obecnie dostępna. 

Faza czasu na wykresie uzyskanej wartości jest wyświetlana według tygodnia lub miesiąca. W tej sekcji opisano trzy kolumny EVM: wartość uzyskana, planowana i rzeczywisty koszt. 

**Wartość planowana** EVM teoretycznie wskazuje, że planowana wartość reprezentuje kurs, według którego zespół projektu planuje uzyskane wartości w projekcie. 

Finance and Operations używa reguły zarabiania 0:100 podczas planowania wartości. Zgodnie z tą regułą wartość zadania jest księgowana w zadaniu w dniu zakończenia zadania. Wartości nie są księgowane przed całkowitym zakończeniem zadania. 

W module Zarządzanie projektami i ich księgowanie wprowadza się datę końcową węzłów liścia i planowany koszt dla tej daty. Po wyświetleniu wykres planowanej wartości wg tygodnia jest ona podsumowywana wg tygodnia dla wszystkich zadań węzłów liści w czasie trwania projektu. 

**Wartość uzyskana** według teorii EVM planowana wartość uzyskana jest stawką, według której zespół projektu uzyskuje realną wartość w projekcie. 

Finance and Operations używa reguły zarabiania 0:100 podczas rysowania wykresu wartości wypracowanej. Zgodnie z tą regułą wartość zadania jest księgowana w zadaniu w dniu zakończenia zadania. Wartości nie są księgowane przed całkowitym zakończeniem zadania. 

W obliczaniu wartości uzyskanej jest uwzględniany procent postępu każdego zadania. Zgodnie z regułą zarabiania 0:100 tylko zadania ukończone w danym okresie są uwzględniane w obliczeniach wartości uzyskanej na koniec okresu. Wartość uzyskana w projekcie jest obliczana dla wszystkich zadań, które zostały wypełnione podczas tworzenia wykresu. 

> [!NOTE] 
> Obecnie system śledzenia SPP nie ma struktur danych do przechowywania archiwalnych wartości procentowych postępu w każdym zadaniu. W związku z tym uzyskana wartość może być zgłaszana tylko dla czasu przetwarzania modułu. Przetwarzaj moduł regularnie, aby zaktualizować dane uzyskanej wartości, która jest wyświetlana w widoku głównym użytkownika. 

**Koszt rzeczywisty** według teorii EVM planowanie kosztu rzeczywistego odzwierciedla stawkę, przy której wydawane są pieniądze w projekcie. 

Transakcje, które zostały zaksięgowane do projektu służą do planowania wiersza kosztu rzeczywistego. Koszty są zestawione według daty. Te dane są następnie używane do tworzenia wykresów kosztu rzeczywistego wg tygodnia lub miesiąca na wykresie uzyskanej wartości.

### <a name="how-to-use-the-concepts-of-planned-value-earned-value-and-actual-cost"></a>Jak używać koncepcji wartości planowanej, uzyskanej i kosztu rzeczywistego

**Odchylenie od harmonogramu** podczas planowania tworzone są prognozy dla pracy na osi czasu. W związku z tym planowana wartość jest stawką, wg której planiści projektu zakładali ukończenie pracy w projekcie. Po rozpoczęciu projektu, praca jest wykonywana, a projekt uzyskuje wartość. Porównanie wartości planowanych do uzyskanych umożliwia wyświetlenie postępów prac nad projektem. Wynik porównania jest nazywany odchyleniem od harmonogramu. 

Jeśli planowana wartość dla okresu jest wyższa niż wartość uzyskana, ilość pracy wykonanej w projekcie jest mniejsza niż zaplanowana. W związku z tym projekt jest opóźniony. Ponieważ wartość planowana i uzyskana są wyrażone w jednostkach pieniężnych, czas zwłoki w projekcie jest również podany jako wartość pieniężna. 

Jeśli planowana wartość dla okresu jest niższa niż wartość uzyskana, ilość pracy wykonanej w projekcie jest większa niż zaplanowana. W związku z tym projekt jest realizowany szybciej niż planowano. Ten czas również ma wartość pieniężną.

**Odchylenie kosztów** ponieważ uzyskana wartość używa wartości kosztu własnego jako mnożnik, uzyskana wartość wskazuje koszt pracy przeprowadzanej w projekcie. W miarę postępów projektu dziennik transakcji pokazuje rekord pieniędzy faktycznie wydanych w projekcie. Przez porównanie wartości uzyskanej do kosztu rzeczywistego, można wyświetlić kwotę wydawaną względem uzyskiwanej. Wynik porównania jest nazywany odchyleniem kosztu. 

Jeśli koszt rzeczywisty w okresie jest większy od wartości uzyskanej, wydatki są wyższe niż zarobki. W związku z tym projekt przekracza budżet. 

Jeśli koszt rzeczywisty w okresie jest większy od wartości uzyskanej, wydatki są wyższe niż zarobki. W związku z tym projekt przekracza budżet.

## <a name="wbs-templates"></a>Szablony WBS
Funkcja szablonów SPP umożliwia tworzenie standardowych szablonów dla projektów. Jeśli projekt zakłada dużo powtarzającej się pracy, rozważ utworzenie szablonu SPP. 

Szablon SPP można utworzyć z SPP istniejącego projektu, dzięki czemu wiedza i sprawdzone metody zgromadzone podczas planowania projektu mogą być wykorzystane w przyszłości do podobnych projektów. Ale czasem nie ma sensu zapisywanie całego SPP jako szablonu. Dlatego też można utworzyć szablony z części SPP dla projektu.

### <a name="saving-a-projects-wbs-as-a-template"></a>Zapisywanie SPP projektu jako szablonu

Po utworzeniu szablonu można zaimportować go do nowego projektu SPP pod węzłem głównym lub w obszarze każdego zadania w SPP projektu.

### <a name="importing-a-wbs-template-into-a-projects-wbs"></a>Importowanie szablonu struktury podziału pracy do SPP projektu

Importowane zadania są porządkowane wg daty rozpoczęcia zadania, dla którego są importowane. Podczas importu do obliczania dat początkowych dla importowanych zadań używane są relacje istniejące wcześniej w zadaniach szablonu. Kalendarz pracy standardowej w projekcie docelowym jest stosowany do obliczania dat zakończenia importowanych zadań, tak aby dni robocze i standardowe godziny pracy określone w kalendarzu czasu pracy bieżącego projektu zostały zachowane. 

W wierszach oszacowania uwzględnia się ceny kosztu i sprzedaży, aby zapewnić, że ceny właściwe dla projektu lub umowy dotyczącej projektu mają prawidłowe daty.

### <a name="differences-between-a-projects-wbs-and-a-wbs-template"></a>Różnice między SPP projektu a szablonem SPP

-   Zadania w szablonach SPP nie mają dat rozpoczęcia i zakończenia.

Dni pracujące i niepracujące nie są ustawione w szablonach SPP.

-   Szablony SPP zawsze używają kalendarzy harmonogramu ustawionych jako domyślne dla wszystkich projektów.

Domyślny kalendarz harmonogramu jest używany tylko do zidentyfikowania godzin w standardowy dzień roboczy.

-   Poprzednie relacje nie są kopiowane do szablonu struktury podziału pracy.

Ponieważ szablon SPP nie ma dat, nie jest wymagana logika daty rozpoczęcia na podstawie wcześniejszych dat zakończenia.

-   Wiersz szacowania kosztów pracy jest tworzony automatycznie podczas tworzenia zadania w szablonie struktury podziału pracy. Cena sprzedaży i koszt są kopiowane z danych wybranego pracownika.

Wydatki i koszty towarów można tworzyć ręcznie, tak jak w SPP projektu.

-   Błędy planowania są wyświetlane, gdy istnieją odchylenia od następującej formuły:

Nakład pracy = liczba zasobów x czas trwania x liczba godzin w standardowym dniu roboczym 

Można poprawić wszystkie błędy planowania jednocześnie, klikając opcję **Popraw wszystkie błędy planowania**. 

Można też poprawiać je pojedynczo, klikając ikonę ostrzeżenia dla każdego zadania.




