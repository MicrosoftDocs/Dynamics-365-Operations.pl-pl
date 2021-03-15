---
title: Poprawa wydajności aparatu planowania
description: Ten temat zawiera informacje o aparacie planowania oraz o sposobach zwiększania wydajności.
author: ChristianRytt
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2c39a72d22c01faec3856e7f47cb6b3811447cab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983448"
---
# <a name="improve-scheduling-engine-performance"></a>Poprawa wydajności aparatu planowania

[!include [banner](../includes/banner.md)]

Aparat planowania zasobów jest używany podczas planowania marszrut dla planowanych i zwolnionych zleceń produkcyjnych. Aparat został pierwotnie wydany w ramach systemu Dynamics AX 2012, a od tego momentu wprowadzono kilka udoskonaleń.

[Problem z planowaniem pracy w module produkcyjnym](https://en.wikipedia.org/wiki/Job_shop_scheduling) jest niezwykle skomplikowanym problemem kombinatorycznym, w którym czas rozwiązania wzrasta w sposób wykładniczy wraz z liczbą zmiennych decyzji. Często odbiorcy konfigurują marszruty produkcji i powiązane dane w sposób, który powoduje problem z planowaniem, którego nie można rozwiązać w rozsądnym czasie, nawet w przypadku najbardziej nowoczesnego sprzętu. Ten temat ułatwi zrozumienie aparatu planowania oraz sposobu, w jaki określone ustawienia mogą mieć wpływ na wydajność.

Jeśli chodzi o poprawę wydajności planowania, ogólne wskazówki zalecają zmniejszenie złożoności problemu, który musi zostać rozwiązany przez aparat. Poniżej przedstawiono niektóre z głównych czynników, które mogą mieć wpływ na wydajność:

- Marszruty z wieloma operacjami
- Marszruty z równoległymi operacjami
- Operacje zawierające więcej niż jeden zasób
- Operacje z wieloma odpowiednimi zasobami
- Używanie łączy stałych
- Używanie ograniczonych zdolności produkcyjnych
- Liczba różnych używanych kalendarzy
- Liczba przedziałów czasu pracy dziennie w kalendarzu
- Łączny czas trwania marszruty
- Uruchamianie wielu aparatów planowania równolegle

## <a name="overview-of-basic-scheduling-flow"></a>Przegląd podstawowego przepływu planowania

Aby zrozumieć, w jaki sposób dana konfiguracja może mieć wpływ na wydajność, ważne jest zrozumienie, w jaki sposób przebiega proces przepływu, zarówno wewnątrz aparatu, jak i w otaczającym go kodzie X++.

Podstawowy proces planowania zamówienia składa się z trzech głównych kroków:

- **Ładowanie danych** — w tym miejscu modele danych X++ są przekształcane w wewnętrzny model danych aparatu w postaci zadań i ograniczeń.
- **Planowanie** — jest to główne źródło planowania, które przetwarza dany model i ograniczenia, a następnie generuje wynik. W trakcie tego procesu aparat będzie żądał informacji o czasie pracy i istniejących rezerwacjach zdolności produkcyjnych z X++, jeśli jest to konieczne.
- **Zapisywanie danych** — wynik aparatu w postaci gniazd rezerwacji zdolności produkcyjnych jest przetwarzany przez kodu X++ w celu zapisania rezerwacji zdolności produkcyjnych i zaktualizowania godzin rozpoczęcia i zakończenia zadań/operacji/zlecenia.

## <a name="load-data-into-the-engine"></a>Ładowanie danych do aparatu

Aparat planowania ma bardziej abstrakcyjny model danych niż baza danych Supply Chain Management, ponieważ został on zbudowany jako aparat ogólny, który może obsługiwać różne źródła danych. Pojęcia dotyczące marszruty, operacji dodatkowych i czasu działania muszą zostać „przetłumaczone” na zadanie ogólne i model ograniczeń, które udostępnia dany aparat. Logika tworzenia modelu ma istotną część logiki biznesowej i jest różna w zależności od danych źródłowych. Odpowiedzialna klasa X++ to `WrkCtrScheduler` i ma klasy pochodne dla planowanych zleceń produkcyjnych, zwolnionych zleceń produkcyjnych i prognoz projektów.

Rozważmy na przykład trasę podaną w poniższej tabeli i obrazie, która wygląda stosunkowo prosto.

| Nr Nr | Priorytet | Czas przezbrajania | Czas procesu | Czas oczekiwania po | Ilość zasobów | Następny |
| --- | --- | --- | --- | --- | --- | --- |
| 10 | Główne | 1.00 | 2.00 | | 1 | 20 |
| 10 | Podrzędna&nbsp;1 | | | | 1 | 20 |
| 20 | Główne | | 3.00 | 1.00 | 3 | 0 |

![Przykładowy diagram marszruty](media/scheduling-engine-route.png "Przykładowy diagram marszruty")

Po wysłaniu tego obrazu do aparatu jest on dzielony na osiem zadań, tak jak to pokazano na poniższej ilustracji (należy wybrać obraz, aby go powiększyć).

[![Planowanie zadań aparatu](media/scheduling-engine-jobs.png "Zadania aparatu planowania")](media/scheduling-engine-jobs-large.png)

Standardowe łącze między dwoma zadaniami to `FinishStart` oznaczające, że godzina zakończenia jednego zadania musi być wcześniejsza niż godzina rozpoczęcia innego zadania. Ponieważ konfiguracja musi zostać wykonana przez ten sam zasób, który będzie później wykonywać proces, istnieją między nimi ograniczenia `OnSameResource`. Między zadaniami podstawowymi i drugorzędnymi dla 10, istnieją łącza `StartStart` i `FinishFinish`, co oznacza, że zadania jednocześnie muszą się rozpoczynać i kończyć w tym samym czasie, i istnieją ograniczenia `NotOnSameResource`, które uniemożliwiają zastosowanie tego samego zasobu jako podstawowego i pomocniczego.

W przypadku operacji 20, gdzie ilość zasobów została ustawiona na 3, zadanie procesu zostało podzielone na trzy odrębne zadania, w których wszystkie zadania muszą być wykonywane dokładnie w tym samym czasie.
W takim przypadku grupa marszruty została skonfigurowana tak, aby nie rezerwowała zdolności produkcyjnych dla kolejki po godzinach, dlatego że kolejka ma tylko jedno zadanie.

Aparat planowania rozumie tylko pojęcia dotyczące zadań i nie ma informacji o operacjach. Oznacza to, że podczas planowania operacje są także dzielone na zadania, mimo że nie zostaną utrwalone w bazie danych.

Dla każdego zadania zdefiniujemy także wymagania dotyczące zdolności produkcyjnych zadania (wymaganą liczbę sekund). W zależności od sposobu zdefiniowania wymagań dotyczących zasobów możemy również wysłać do każdego zadania listę wszystkich potencjalnych zasobów, na których to zadanie może być uruchomione, oraz zapotrzebowanie na zdolności produkcyjne dla określonego zasobu. Mimo że podczas konstruowania modelu jest wysyłana lista odpowiednich zasobów, aparat nadal musi sprawdzić, czy przypisanie zasobu jest prawidłowe dla całego czasu trwania zadania.

## <a name="scheduling-engine-internals"></a>Elementy wewnętrzne aparatu planowania

### <a name="scheduling-engine-interface"></a>Interfejs aparatu planowania

Aby zrozumieć, w jaki sposób aparat działa wewnętrznie, najlepiej jest przeanalizować zewnętrzne funkcje. W kodzie X++ głównym interfejsem jest `WrkCtrSchedulerEngineInterface`. Zawiera metody opisane w poniższych podsekcjach.

#### <a name="general-engine"></a>Aparat ogólny

| **Metoda** | **Cel** |
| --- | --- |
| `run` | Planuje wszystkie załadowane zadania i zwraca kod błędu. |
| `getJobSchedulingSequenceResult` | Pobiera wynik planowania i pierwsze zadanie błędu dla sekwencji oznaczonej określonym zadaniem. |
| `validateJobCapacityReservations` | Sprawdza poprawność rezerwacji zdolności produkcyjnych dla wszystkich zadań przechowywanych przez aparat. |
| `setReservationsTimeStamp` | Wysyła sygnaturę czasową do aparatu ustawionego we wszystkich nowych rezerwacjach zdolności produkcyjnych dla zaplanowanych zadań w pamięci podręcznej aparatu. |
| `addPropertyToGroupAggregation` | Dodaje prefiks właściwości do zbioru właściwości używanego podczas agregowania zdolności produkcyjnych. |
| `addResource` | Dodaje zasób do puli zasobów aparatu planowania. |
| `addResourceGroup` | Dodaje grupę zasobów do puli grup zasobów aparatu planowania. |
| `addResourceGroupMembership` | Dodaje zasób jako element do grupy zasobów. |
| `addOptimizationGoal` | Dodaje cel optymalizacji planowania (czas trwania lub priorytet). |

#### <a name="individual-jobs"></a>Poszczególne zadania

| **Metoda** | **Cel** |
| --- | --- |
| `addJobInfo` | Dodaje rekord informacji o zadaniu, który informuje aparat o zaplanowanym zadaniu. |
| `addConstraintJobEndsAt` | Dodaje ograniczenie, które zadanie ma zakończyć w określonym dniu i o określonej godzinie. |
| `addConstraintJobStartsAt` | Dodaje ograniczenie, które zadanie ma rozpocząć w określonym dniu i o określonej godzinie. |
| `addConstraintMaxJobDays` | Definiuje ograniczenie, które może obejmować zadanie w okresie dłuższym niż maksymalna liczba dni. |
| `addConstraintResourceRequirement` | Umożliwia dodanie ograniczenia, które określa, że zadanie musi zostać zaplanowane w określonym zasobie. |
| `addJobBindPriority` | Dodaje priorytet powiązania zadania dla pary (zadanie, poziom ograniczeń). Wyższa wartość priorytetu oznacza, że zmienne zadania zostaną powiązane wcześniej. Zadanie będzie przetwarzane przed zadaniami o niższej wartości priorytetu w tej samej kolejności. |
| `addJobCapacity` | Umożliwia dodanie informacji o ładowaniu zdolności produkcyjnych dla zadania (np. wymagane środowisko uruchomieniowe zadania) niezależnie od zasobu, na którym jest uruchamiane zadanie. |
| `addJobResourceCapacity` | Dodaje zasób do zbioru zasobów, które mogą być używane do wykonywania zadania i określa zdolności produkcyjne wymagane podczas uruchamiania w tym zasobie. |
| `addJobGoal` | Dodaje informacje dotyczące celu zadania dla określonego poziomu ograniczenia (najwcześniejsza godzina zakończenia lub najpóźniejsza godzina rozpoczęcia). |
| `addJobResourcePriority` | Dodaje priorytet, który ma być używany, gdy zadanie jest zaplanowane dla zasobu. |
| `addJobResourceRuntime` | Określa czas zadania zależny od zasobu, w którym zadanie zostanie zaplanowane. |
| `addJobRuntime` | Określa czas zadania niezależny od zasobu, w którym zadanie zostanie zaplanowane. |
| `scheduleJobOnResourceGroup` | Umożliwia oznaczenie zadania planowania na poziomie grupy zasobów. |
| `setJobResourcePreemptionAllowed` | Określa, czy dla zadania w zasobie jest dozwolone wywłaszczenie (Jeśli aparat może zaplanować zadanie w nieciągłych gniazdach wydajności). |
| `setRequiredNumberOfResources` | Umożliwia ustawienie liczby zasobów wymaganych do zaplanowania zadania (tylko w przypadku planowania operacji). |

#### <a name="constraints-between-jobs"></a>Ograniczenia między zadaniami

| **Metoda** | **Cel** |
| --- | --- |
| `addJobLink` | Dodaje łącze (np. zakończenie\>rozpoczęcie) między dwoma zadaniami. |
| `addConstraintEndsDelayed` | Definiuje ograniczenie, które określa, że nie zadanie nie może się zakończyć przed zakończeniem innego zadania i upłynięciem czasu opóźnienia. |
| `addConstraintJobListWorkingTimeIntersect` | Dodaje ograniczenie określające, że gniazda zdolności produkcyjnych zarezerwowane dla zadań przypadać w przecinających się godzinach pracy dla dwóch zasobów używanych przez zadania. |
| `addConstraintJobOverlap` | Dodaj ograniczenie określające, w jaki sposób zadania są ustawiane kolejno, gdy dana ilość towaru może zostać przeniesiona między dwoma zasobami, gdy przetwarzanie pierwszego zasobu jeszcze nie zostało zakończone, tak aby drugi zasób mógł rozpocząć przetwarzanie. |
| `addConstraintNotOnSameResource` | Umożliwia dodanie ograniczenia, które określa, że dwa zadania nie powinny być planowane na tym samym zasobie. |
| `addConstraintOnSameResource` | Umożliwia dodanie ograniczenia, które określa, że dwa zadania muszą używać tego samego zasobu. |
| `addJobSameReservations` | Dodaje ograniczenie, które określa, że zadanie musi na końcu mieć te same rezerwacje zdolności produkcyjnych dla tych samych przedziałów czasu, co zadanie główne. |
| `setPrimaryParallelJob` | Dodaje informacje o tym, jakie zadanie jest zadaniem głównym w zestawie zadań równoległych. |

### <a name="solver"></a>Zmienna

Sam aparat stanowi zasadniczo specjalistyczny solwer ograniczeń z dodanymi niestandardowymi heurystykami. Solver jest oparty na dwóch głównych elementach: zmiennych i ograniczeniach.

#### <a name="variable"></a>Zmienna

Zmienna oznacza domenę możliwych wartości. Aparat planowania ma dwa typy zmiennych:

- **Zmienna DateTime** — ma domenę wszystkich dat i godzin, a domena może być ograniczona przez zbliżenie dolnej i górnej granicy czasu zmiennej.
- **Zmienna zasobu** — ma domenę odpowiednich zasobów, a domena może podlegać ograniczeniom, eliminując zasoby z listy.

#### <a name="constraint"></a>Ograniczenie

Ograniczenie działa w odniesieniu do zmiennych przez ograniczenie ich domen, ale jest również zależne od zmiennych, dzięki czemu jest uaktywniane po zmianie zmiennych. Proces „propagacji ograniczeń” oznacza, że warunek ograniczający wykonuje główną funkcję i raportuje z powrotem do logiki głównej w przypadku powodzenia.

Zmienna jest uznawana za powiązaną, jeśli nie może być dalej ograniczona, co dla zmiennej DateTime oznacza, że górna i dolna granica są takie same, a zmienna zasobu ma tylko jeden odpowiedni zasób. Jeśli wszystkie zmienne są powiązane, zostanie znalezione rozwiązanie.

### <a name="constraint-levels"></a>Poziomy ograniczeń

Jeśli planowanie jest wykonywane jako część fazy planowania zapotrzebowania na materiały (MRP), zamówienia zostaną zaplanowane wstecz od daty zapotrzebowania. Jeśli jednak nie można odnaleźć harmonogramu rozpoczynającego się dzisiaj lub późniejszego i kończącego się przed datą zapotrzebowania, kierunek planowania zmieni się na biegnący od daty bieżącej.

Główna reguła biznesowa jest obsługiwana przez uporządkowanie ograniczeń na poziomach. Jeśli podczas używania ograniczeń na najwyższym poziomie nie zostanie znalezione rozwiązanie, ograniczenia na tym poziomie pozostaną usunięte i zostanie użyty poziom niższy. W praktyce oznacza, że w przypadku planowania wstecz model będzie zawierał poziom 1 z celami zadania o najpóźniejszym czasie rozpoczęcia, odpowiadającym maksymalnemu ograniczeniu czasu zakończenia (dacie zapotrzebowania) oraz poziomowi 0 z celami zadania o najwcześniejszym czasie zakończenia i mającym minimalne ograniczenie czasu rozpoczęcia w dniu dzisiejszym.

### <a name="algorithm"></a>Algorytm

Główne kroki algorytmu aparatu to:

1. Znalezienie sekwencji (łańcuchów zadań), które można rozwiązać osobno.
1. Spróbuj znaleźć początkowe rozwiązanie sekwencji dla najwyższego poziomu ograniczeń.
    1. Posortuj zadania w sekwencji na podstawie celu i priorytetów zadania, co pozwala na znalezienie zadania rozpoczęcia.
    1. Zapętl zadania w następującej kolejności:
        1. Znajdź wszystkie ograniczenia, które muszą zostać rozpropagowane i uruchom propagację.
        1. Jeśli wszystkie zmienne dla zadania zostały powiązane, znaleziono rozwiązanie tego zadania.
        1. Jeśli nie można powiązać jednej ze zmiennych bez naruszania ograniczeń, wycofaj powiązanie zmiennej, spróbuj użyć innej wartości w domenie (dla zmiennej zasobu) i ponownie uruchom propagację ograniczeń.
1. Jeśli nie znaleziono rozwiązania, wszystkie ograniczenia na bieżącym poziomie ograniczeń zostaną usunięte, a poziom ograniczenia obniżony (jeśli są dostępne niższe poziomy), a wyszukiwanie rozwiązania zostanie ponowione przy użyciu nowego zestawu ograniczeń.
1. Jeśli znaleziono wykonalne rozwiązanie, rozpocznie się faza optymalizacji, w której zostanie podjęta próba znalezienia lepszego rozwiązania do czasu osiągnięcia limitu czasu optymalizacji lub wyczerpania wszystkich kombinacji zasobów.

Solver ograniczeń nie ma informacji o charakterystyce algorytmu planowania. „Magia” dzieję się w definicji i kombinacji różnych ograniczeń.

### <a name="determining-working-times"></a>Określanie czasu pracy

Duża część ograniczeń (wewnętrznych) w aparacie steruje czasem pracy i zdolności produkcyjnych zasobu. W zasadzie zadaniem jest przechodzenie gniazd czasu pracy zasobu z określonego punktu w danym kierunku i znalezienie długiego interwału, w którym może zmieścić się wymagana wydajność (czas) zadań.

W tym celu aparat musi mieć informacje o czasie pracy zasobu. W przeciwieństwie do danych modelu głównego czas pracy jest *ładowany z opóźnieniem*, co oznacza, że jest ładowany do aparatu w razie potrzeby. Powodem tego podejścia jest to, że często istnieje w Supply Chain Management czas pracy dla kalendarza przez bardzo długi okres i zazwyczaj istnieje wiele kalendarzy, więc wstępnie ładowane dane mogą być dość duże.

Informacje w kalendarzu są wymagane przez aparat we fragmentach przez wywołanie metody klasy X++ `WrkCtrSchedulingInteropDataProvider.getWorkingTimes`. Żądanie dotyczy określonego identyfikatora kalendarza w określonym danym czasu. W zależności od stanu pamięci podręcznej serwera w Supply Chain Management każde z tych żądań może się zakończyć kilkoma wywołaniami bazy danych, co zabiera dużo czasu (w odniesieniu do czystego czasu obliczeniowego). Ponadto, jeśli kalendarz zawiera bardzo rozbudowane definicje czasu pracy z wieloma dziennymi przedziałami czasu pracy, zwiększa to czas trwania ładowania.

Gdy dane czasu pracy są ładowane do aparatu planowania, są zachowywane w wewnętrznej pamięci podręcznej dla określonego kalendarza, co oznacza, że jeśli inne zadania lub zasoby używają tego samego kalendarza, kolejne wyszukiwania mogą być wykonywane szybko z pamięci. Jedną z najczęstszych przyczyn nieprawidłowej wydajności jest użycie osobnego identyfikatora kalendarza dla każdego zasobu, ponieważ konieczne będzie żądanie danych dla każdego z kalendarzy, nawet jeśli zawartość kalendarzy może być taka sama.

### <a name="finite-capacity"></a>Ograniczone zdolności produkcyjne

Jeśli używane są ograniczone zdolności produkcyjne, przedziały czasu pracy z kalendarza są dzielone i zmniejszane na podstawie istniejących rezerwacji zdolności produkcyjnych. Te rezerwacje są również pobierane przy użyciu tej samej klasy `WrkCtrSchedulingInteropDataProvider` co kalendarze, ale używają metody `getCapacityReservations`. W przypadku planowania w trakcie planowania głównego są brane pod uwagę rezerwacje określonego planu głównego, a jeśli są włączone na stronie **Parametry planowania głównego**, uwzględniane są także rezerwacje z ustalonych zleceń produkcyjnych. Podobnie podczas planowania zlecenia produkcyjnego jest to również opcja, która uwzględnia rezerwacje z istniejących zamówień planowanych, chociaż nie jest to powszechne, tak jak w poprzednim przypadku.

Użycie ograniczonych zdolności produkcyjnych spowoduje, że planowanie będzie trwać dłużej z kilku powodów:

- Pobieranie informacji o zdolnościach produkcyjnej z bazy danych jest powolną operacją, a buforowanie informacji o zdolnościach produkcyjnych na serwerze zazwyczaj nie jest tak dobre jak w przypadku czasu pracy, ponieważ nie są współużytkowane w zasobach typowych dla kalendarzy.
- Liczba przedziałów czasu pracy do przejścia zwiększa się z powodu podziałów, a aby można było znaleźć rozwiązanie, zwykle należy przeanalizować przedziały dla dłuższego okresu.
- Po zakończeniu planowania konieczne jest sprawdzenie, czy istnieją rezerwacje powodujące konflikt (patrz część „Równoległe uruchamianie aparatów planowania”).

### <a name="examining-the-resource-combinations"></a>Sprawdzanie kombinacji zasobów

Jeśli sekwencja zadań zawiera tylko standardowe łącza `FinishStart`, co oznacza, że formularz jest prostym łańcuchem bez oddziałów, optymalny wynik (widoczny w jednym zamówieniu, nie między kolejnymi zamówieniami) można uzyskać przez znalezienie najlepszego rozwiązania dla pierwszego zadania, a następnie znalezienia najlepszego rozwiązania dla następnego zadania. Najlepszym rozwiązaniem zadania jest znalezienie zasobu, który może uzyskać datę początkową i końcową zadania najbardziej zbliżonego do celu zadania (w procesie planowania od dnia dzisiejszego oznacza to uzyskanie daty zakończenia zadania możliwie najwcześniej) przy zachowaniu tych ograniczeń.

Jeśli istnieją zadania równoległe, znalezienie rozwiązania może wymagać zbadania różnych kombinacji zasobów. Liczba możliwych kombinacji zasobów wynika z liczby zasobów odpowiednich dla połączonych zadań równoległych. Szczególnie w przypadku planowania zamówienia wstecz od daty zapotrzebowania potrzebny jest czas, aby logika mogła określić, że nie ma rozwiązania problemu, który spowoduje, że zadania równoległe nie zmieszczą się przed datą dzisiejszą, co będzie wymagało sprawdzenia wszystkich kombinacji, ponieważ mogą istnieć pewne zasoby o wyższej wydajności lub innym kalendarzu, który może dać wynik. Oznacza to, że jeśli limit czasu nie zostanie skonfigurowany, będzie on uruchomiony przez dłuższy czas przed zmianą kierunku na do przodu.

Ta logika kombinatoryczna oznacza, że dodanie większej liczby odpowiednich zasobów może spowodować wolniejsze uruchamianie aparatu. Jeśli występują problemy z wydajnością podczas wykonywania równoległych operacji i planowania z nieskończonymi zdolnościami produkcyjnymi, można je częściowo rozliczyć, konfigurując projektanta marszrut w celu podjęcia decyzji, który zasób powinien zostać użyty, a następnie bezpośredniego przypisywania zasobu do operacji (ponieważ aparat w większości przypadków zawsze zakończy pobieranie tego samego zasobu, więc wynik końcowy będzie taki sam).

### <a name="hard-links"></a>Łącza stałe

Ustawienie typu łącza między dwoma zadaniami na stałe gwarantuje, że nie ma przerwy w przedziale czasu między zakończeniem jednego zadania a początkiem kolejnego. Może to być bardzo przydatne w scenariuszach takich jak wtedy, gdy metal jest podgrzewany w jednym zadaniu, a następnie przetwarzany w następnym zadaniu, gdzie nie jest pożądane schładzane metalu między nimi.

W przypadku standardowych łączy miękkich i planowania do przodu, jeśli marszruta tworzy prosty łańcuch bez oddziałów, można uzyskać wynik, wyszukując rozwiązanie dla pierwszego zadania, które spełnia jego własne ograniczenia, a następnie przechodząc przez łańcuch propagacji czasu zakończenia z poprzedniego zadania do następnego zadania. Jeśli bieżące zadanie nie może znaleźć zdolności produkcyjnych, czas rozpoczęcia dla tego zadania zostanie przesunięty najpóźniej, bez żadnego związku z poprzednimi zadaniami, potencjalnie tworząc przerwy między zadaniami. Jednak w przypadku łączy stałych (szczególnie w związku z ograniczonymi zdolnościami produkcyjnymi) w tym samym scenariuszu fakt, że jedno zadanie późniejsze w łańcuchu zdolności produkcyjnych nie ma możliwości znalezienia zdolności produkcyjnych oznacza, że wszystkie poprzednie zaplanowane zadania muszą być „przeciągnięte” pojedynczo, a w konsekwencji ponownie zaplanowane wiele razy. W szczególności w scenariuszach z wysokim obciążeniem dla wielu zasobów stałe łącza mogą powodować reakcje łańcuchowe, w których zadania mają wpływ na siebie, a wiele iteracji będzie wymagało wykonania przed ustabilizowaniem wyników do wykonalnego harmonogramu.

## <a name="running-scheduling-engines-in-parallel"></a>Uruchamianie aparatów planowania równolegle

Podczas planowania w ramach procesu planowania głównego, w którym używani są pomocnicy, każdy wątek pomocniczy planowania głównego może również pobierać zadania planowania zlecenia produkcyjnego. Oznacza to, że wiele aparatów planowania może być uruchomionych w tym samym czasie. Choć wielowątkowość jest bardzo istotną zaletą wydajności, istnieją również pewne wady funkcjonalne dotyczące planowania.

W module MRP wszystkie zlecenia produkcyjne dla danego poziomu listy składowej (BOM) są planowane w sekwencjach dat zapotrzebowania, co oznacza, że zamówienia z najwcześniejszą datą zapotrzebowania powinny być zaplanowane jako pierwsze i w ten sposób mieć największą szansę na uzyskanie dostępnej zdolności produkcyjnej zasobu. Jednak w przypadku wielu aparatów pobierających z listy nieplanowanych zamówień sekwencja nie jest już zapewniana, ponieważ jeden może zakończyć pracę szybciej niż drugi.

Ponadto podczas planowania przy użyciu ograniczonych zdolności produkcyjnych i gdy wiele wystąpień aparatów próbuje zaplanować zamówienia, które mogą potencjalnie korzystać z tych samych zasobów w tym samym przedziale czasu, może wystąpić stan wyścigu. Liczba takich stanów wyścigu jest rejestrowana w polu **Konflikty planowania** na stronie historii planów głównych. Logika rozwiązywania konfliktów jest następująca:

- Zaplanuj zamówienie (bez blokady) i pobierz rezerwacje zdolności produkcyjnych.
- Użyj blokady.
- Sprawdź, czy istnieją nowsze rezerwacje zdolności produkcyjnych dla zaplanowanych zasobów w przedziale czasu.
  - Jeśli nie, zapisz zdolności produkcyjne i zwolnij blokadę.
  - Jeśli tak, zwolnij blokadę i ponownie zaplanuj zamówienie od początku.

Dlatego podczas planowania z wieloma wystąpieniami aparatu wynik nie jest całkowicie określony, ponieważ będzie zależny od dokładnego czasu trwania każdego z wątków.

## <a name="operation-scheduling-performance"></a>Wydajność planowania operacji

Chociaż planowanie operacji jest również nazywane wstępnym planowaniem zdolności produkcyjnych, z punktu widzenia aparatu, może to utrudnić rozwiązanie problemu, jeśli są używane ograniczone zdolności produkcyjne, ponieważ więcej danych jest potrzebnych do określenia wykonalności.

Zdolności produkcyjne grupy zasobów zależą od tego, jakie i ile zasobów należy do danej grupy zasobów. Grupa zasobów w sama w sobie nie ma żadnych zdolności produkcyjnych &mdash; tylko gdy zasoby są elementami grupy, będą mieć zdolności produkcyjne. Ponieważ członkostwo grupy zasobów może się różnić w miarę upływu czasu, zdolności produkcyjne muszą być oceniane codziennie.

W planowaniu operacji kalendarz grupy zasobów służy do ustalania godzin rozpoczęcia i zakończenia każdej operacji. Oznacza to, że kalendarz grupy zasobów określa limit czasu, w którym operacje są planowane dla jednej operacji w jednym dniu w jednej grupie zasobów. W przeciwieństwie do kalendarza dla określonych zasobów dane dotyczące wydajności kalendarza są ignorowane dla grupy zasobów, ponieważ oznaczają po prostu godziny otwarcia, a nie rzeczywiste zdolności produkcyjne.

Jeśli na przykład czas pracy dla grupy zasobów w określonym dniu wynosi od 8:00 do 16:00, jedna operacja nie może nałożyć większego obciążenia na grupę zasobów, niż może ona zawierać w ciągu 8 godzin, bez względu na ilość zdolności produkcyjnych, która w danym dniu była dostępna dla danej grupy zasobów. Dostępne zdolności produkcyjne mogą jednak dodatkowo ograniczyć obciążenie.

Obciążenie pracą z planowania zadań na wszystkich zasobach uwzględnionych w grupie zasobów jest brane pod uwagę w przypadku obliczania dostępnych zdolności produkcyjnych dla grupy zasobów w danym dniu. Dla każdej daty obliczenie jest następujące:

*Dostępna pojemność grupy zasobów = pojemność zasobów w grupie na podstawie ich kalendarza &ndash; Zaplanowane zadanie obciążenia zasobów w grupie &ndash; Zaplanowane operacje obciążenia zasobów w grupie &ndash; Zaplanowane obciążenie operacji w grupie zasobów*

Na karcie **Zapotrzebowanie na zasoby** w operacji marszruty zapotrzebowanie na zasoby można określać przy użyciu danego zasobu (w takim przypadku operacja będzie planowana na podstawie tego zasobu), dla grupy zasobów, dla typu zasobu lub dla jednego lub większej liczby możliwości, umiejętności, kursu lub certyfikatu. Użycie wszystkich tych opcji zapewnia dużą elastyczność w projektowaniu marszruty, a także komplikuje planowanie dla aparatu, ponieważ zdolności produkcyjne muszą być księgowane według „właściwości” (nazwy abstrakcyjnej używanej w aparacie w celu uzyskania możliwości, umiejętności itp.).

Wydajność grupy zasobów dla zdolności produkcyjnych to suma wydajności dla wszystkich zasobów w grupie zasobów o danej zdolności produkcyjnej. Jeśli zasób w grupie ma zdolności produkcyjne, będzie on uwzględniany niezależnie od tego, jaki poziom wydajności jest wymagany.

W planowaniu operacji dostępna wydajność dla danych zdolności produkcyjnych grupy zasobów zostanie zmniejszona po załadowaniu operacji wymagającej danych zdolności produkcyjnych. Jeśli operacja wymaga więcej niż jednej zdolności produkcyjnej, wydajność zostanie zmniejszona dla wszystkich wymaganych zdolności produkcyjnych.

Dla każdej daty wymagane obliczenie jest następujące:

*Dostępna pojemność dla zdolności = Pojemność dla zdolności &ndash; Zaplanowane obciążenie zasobów z określonymi możliwościami, które są zawarte w grupie zasobów &ndash; Zaplanowane obciążenie operacji na zasobach z określonymi możliwościami, które są zawarte w grupie zasobów &ndash; Zaplanowane ładowanie operacji w samej grupie zasobów, które wymagają określonej możliwości*

Oznacza to, że w przypadku obciążenia określonego zasobu, obciążenie jest brane pod uwagę przy obliczaniu dostępnej wydajności grupy zasobów na jedną zdolność, ponieważ obciążenie określonego zasobu zmniejsza jego udział w wydajności grupy zasobów w zależności od zdolności produkcyjnych, jeśli obciążenie określonego zasobu jest związane z daną zdolnościami produkcyjnymi. Jeśli na poziomie grupy zasobów znajduje się obciążenie, jest ono uwzględniane w obliczeniach dostępnej wydajności grupy zasobów na zdolności produkcyjne tylko wtedy, gdy obciążenie pochodzi z operacji wymagającej określonych zdolności produkcyjnych.

Powyższa logika jest skomplikowana, ponieważ jest taka sama dla każdego typu „właściwości”, więc korzystanie z funkcji planowania operacji o ograniczonych zdolnościach produkcyjnych wymaga załadowania znacznej ilości danych.

## <a name="viewing-scheduling-engine-input-and-output"></a>Wyświetlanie danych wejściowych i wyjściowych aparatu planowania

Aby uzyskać szczegółowe informacje dotyczące wejścia i wyjścia procesu planowania, należy włączyć rejestrowanie, przechodząc do **Administrowanie organizacją \> Ustawienia \> Planowanie \> Panel śledzenia planowania**.

Na tej stronie najpierw wybierz opcję **Włącz rejestrowanie** w okienku akcji. Następnie uruchom planowanie zlecenia produkcyjnego. Po zakończeniu wróć do strony **Panel śledzenia planowania** i wybierz opcję **Wyłącz rejestrowanie** w okienku akcji. Umożliwia odświeżenie strony i wyświetlenie nowego wiersza w tabeli. Wybierz nowy wiersz, a następnie opcję **Pobierz** w okienku akcji. Spowoduje to udostępnienie skompresowanego folderu. zip zawierającego następujące pliki:

- **Log. txt** — jest to plik dziennika opisujący kroki, jakie wykona aparat. Jest bardzo rozbudowany i może być nieco przytłaczający, ale jeśli jest używany jako część eksperymentowania z konfiguracją marszruty w celu rozwiązania problemów z wydajnością, pierwszym elementem analizy powinna być różnica w czasie między pierwszym a ostatnim wierszem, co pozwoli uzyskać dokładny czas trwania harmonogramu.
- **XmlModel.xml** — zawiera model zbudowany w języku X++ i, na którym działa aparat. `JobId` użyty w pliku odpowiada `RecId` z tabeli źródłowej zawierającej zadania (`ReqRouteJob` lub `ProdRouteJob`). Typowym elementem do sprawdzenia w tym pliku jest to, że daty podane w `ConstraintJobStartsAt` i `ConstraintJobEndsAt` są zgodne z oczekiwaniami, właściwość `JobGoal` jest poprawnie ustawiona i zadania są ze sobą wzajemnie powiązane przez ograniczenia `JobLink`.
- **XmlSlots.xml** — zawiera wszystkie rezerwacje czasów pracy i zdolności produkcyjnych, których wymaga dany aparat. Czas pracy w kalendarzu i rezerwacje będą wymagane tylko przez aparat dla okresów, w których próbuje on umieścić zadania (i dodatkowy bufor), więc jeśli plik zawiera terminy w dalekiej przyszłości, może to oznaczać problem z konfiguracją. W węzłach `ResourceProperty` będą pokazywane wszystkie zasoby, z którymi skojarzone są grupy zasobów i funkcje, dla których są powiązane okresy.
- **Result. XML** — zawiera wynik uruchomienia planowania.

Należy zauważyć, że funkcja śledzenia może dodawać znaczne obciążenie związane z wydajnością, dlatego służy tylko do badania planowania konkretnych zamówień w kontrolowany sposób. Jeśli ta opcja jest włączona podczas planowania głównego, system szybko osiągnie swój limit rozmiaru i zostanie zatrzymany.

## <a name="troubleshooting-performance"></a>Rozwiązywanie problemów z wydajnością

Zgodnie z informacjami we wszystkich poprzednich sekcjach, istnieją pewne pułapki związane z konfiguracją i użytkowaniem aparatu planowania, co może prowadzić do problemów z wydajnością. Do rozwiązywania takich problemów można użyć następującej listy kontrolnej. Ważne jest, aby przeanalizować wszystkie punkty, ponieważ najczęściej połączenie wielu czynników powoduje problemy.

### <a name="performing-scheduling-as-part-of-mrp-when-it-is-not-needed"></a>Wykonywanie planowania jako części MRP bez potrzeby

Chociaż marszruty są używane do celów kontroli produkcji, takich jak wycena i raportowanie, nie trzeba ich uwzględniać podczas MRP. W niektórych przypadkach, gdy dla danego towaru określenie standardowego czasu realizacji produkcji będzie wystarczające do planowania. Aby wyłączyć planowanie marszruty, należy ustawić wartość w polu horyzont czasowy zdolności produkcyjnych na zero. Jeśli planowanie powinno zostać wykonane, horyzont czasowy zdolności produkcyjnych musi zostać starannie ustawiony, ponieważ może nie być konieczne uwzględnienie marszrut w pełnym zakresie horyzontu czasowego zapotrzebowania na MRP.

Należy zauważyć, że jeśli zamówienie nie jest planowane w trakcie MRP, będzie konieczne zaplanowanie podczas ustalania zamówienia planowanego. Oznacza to, że proces ustalania może trwać dłużej, więc w zależności od liczby potwierdzonych sugerowanych planowanych zamówień zysk wydajności w czasie MRP może zostać utracony przy potwierdzaniu.

### <a name="route-with-unnecessary-operations"></a>Marszruta z niepotrzebnymi operacjami

Podczas projektowania marszruty kuszące jest wypróbowanie modelu rzeczywistego ze wszystkimi etapami produkcji. Chociaż może to być przydatne w niektórych przypadkach, nie jest dobrym rozwiązaniem, ponieważ model, na którym musi działać aparat, rośnie (zarówno pod względem zadań, jak i ograniczeń), a w celu wstawienia i zaktualizowania zadań i rezerwacji zdolności produkcyjnych więcej będzie wykonywanych instrukcji SQL. Ponadto istnieje efekt niższego rzędu powodujący konieczność raportowania postępu na zadaniach, który można ograniczyć przez automatyczne księgowania. Jeśli dane nie są używane do niczego, tworzy to niepotrzebne obciążenie.

Zalecane jest tworzenie tylko operacji, które są niezbędne do planowania (zazwyczaj są to zasoby powodujące powstanie wąskiego gardła) i/lub wyceny. Można również zgrupować wiele mniejszych operacji w jedną większą operację, która reprezentuje większą część procesu.

### <a name="many-applicable-resources-for-an-operation"></a>Wiele odpowiednich zasobów dla operacji

Liczba odpowiednich zasobów dla operacji jest określona przez zapotrzebowanie na zasoby określone w relacji operacji. Wymaganie może dotyczyć konkretnego (pojedynczego) zasobu lub może być oparte na członkostwie zasobu w grupie zasobów lub możliwości produkcyjnych.

Jeśli planowanie nie jest wykonywane przy użyciu ograniczonych zdolności produkcyjnych, a wszystkie odpowiednie zasoby mają ten sam kalendarz i efektywność, aparat planowania będzie zawsze kontynuować pobieranie tego zasobu dla operacji, ale tylko po próbie sprawdzenia, czy wszystkie odpowiednie zasoby nie są „lepsze” niż inne. W takim przypadku obciążenie planowania może być znacznie zmniejszone przez stałe przypisanie konkretnego zasobu do operacji w czasie projektowania marszruty.

### <a name="route-with-parallel-operations"></a>Marszruta z równoległymi operacjami

Chociaż operacje równoległe (podstawowe/pomocnicze) to zaawansowane narzędzie do modelowania scenariuszy, np. gdy maszyna i operator, są potrzebne do wykonania określonego zadania, to również źródło wielu problemów z wydajnością. Jeśli zapotrzebowanie dla konkretnego zasobu jest przypisane zarówno do operacji głównej, jak i pomocniczej, zwykle nie jest to problem. Jeśli jednak istnieje wiele możliwych zasobów dla każdej z tych operacji, zwiększa to znacznie złożoność obliczeń w planowaniu.

Alternatywą dla stosowania równoległych operacji jest modelowanie par jako zasobów „wirtualnych” (będą one oznaczać zespół, który zawsze będzie się łączyć z daną operacją) lub po prostu niemodelowanie jednej z operacji, jeśli nie powoduje powstania wąskiego gardła.

### <a name="route-with-quantity-of-resources-higher-than-1"></a>Marszruta zawierająca więcej niż 1 zasób

W przypadku ustawienia ilości zasobów potrzebnych do wykonania operacji na więcej niż jeden w praktyce jest to tak samo, co użycie operacji podstawowych/drugorzędnych, ponieważ do aparatu jest wysyłanych wiele zadań równoległych. Jednak w tym przypadku nie jest dostępna opcja stosowania konkretnych przydziałów zasobów, ponieważ ilość wyższa niż jeden wymaga, aby dla danej operacji był dostępny więcej niż jeden zasób.

### <a name="excessive-use-of-finite-capacity"></a>Nadmierne używanie ograniczonych zdolności produkcyjnych

Użycie ograniczonych zdolności produkcyjnych wymaga, aby aparat ładował informacje o zdolnościach produkcyjnych z bazy danych i miał narzut obliczeniowy, ponieważ znalezienie rozwiązania jest trudniejsze w środowiskach, w których zasoby są zarezerwowane blisko ich maksymalnych zdolności produkcyjnych. W związku z tym ważne jest dokładne oszacowanie, czy zasób naprawdę wymaga użycia ograniczonych zdolności produkcyjnych czy można go zarezerwować ponad swoje możliwości. Ponieważ istnieje różnica między zasobami z ograniczonymi zdolnościami produkcyjnymi dotyczące znaczenia ich nierezerwowania ponad możliwości, zaleca się użycie opcji wąskiego gardła dla zasobu w połączeniu z oddzielną wartością planu w sekcji „Horyzont czasowy zdolności produkcyjnych dla zasobów wąskich gardeł”. Użycie koncepcji wąskiego gardła może umożliwić skrócenie horyzontu czasowego ograniczonych zdolności produkcyjnych.

### <a name="setting-hard-links"></a>Ustawianie łączy stałych

Standardowy typ łącza marszruty jest *miękki*, co oznacza, że jest dozwolony odstęp czasowy między godziną zakończenia jednej operacji a początkiem następnej. Zezwolenie na ten proces może mieć negatywny efekt: jeśli materiały lub zdolności produkcyjne nie są dostępne dla jednej z operacji wykonywanych przez bardzo długi czas, produkcja może być w dłuższym czasie bezczynna, co oznacza możliwy wzrost ilości prac w toku. Nie będzie to miało miejsca w przypadku użycia łączy stałych, ponieważ zakończenie i rozpoczęcie muszą być dokładnie zsynchronizowane. Jednak ustawienie łączy stałych sprawia, że problem planowania jest trudniejszy, ponieważ przedziały czasu pracy i zdolności produkcyjnych muszą być obliczane dla dwóch zasobów operacji. Jeśli istnieją również operacje równoległe, powoduje to dodanie znacznego czasu obliczeniowego. Jeśli zasoby dwóch operacji mają różne kalendarze, które się wcale nie nakładają, problemu nie da się rozwiązać.

Zaleca się używanie łączy stałych tylko wtedy, gdy jest to absolutnie konieczne i należy dokładnie przeanalizować, czy jest to konieczne dla każdej operacji związanej z daną marszrutą.

Aby zmniejszyć ilość pracy w toku bez stosowania stałych łączy, należy zaplanować zlecenie dwa razy, zmieniając na przeciwny kierunek drugiego przebiegu. Jeśli pierwszy harmonogram został wykonany wstecz od daty dostawy, drugi powinien zostać wykonany do przodu od zaplanowanej daty rozpoczęcia. Dzięki temu zadania będą kompresowane w możliwie największym stopniu, aby praca w toku była zminimalizowana.

### <a name="separate-calendar-for-each-resource"></a>Osobny kalendarz dla każdego zasobu

Jednym z głównych źródeł danych dla aparatu planowania są informacje kalendarza, których ładowanie z bazy danych może być kosztowne. Ponieważ kalendarze są generowane na podstawie szablonów, kuszące jest generowanie kalendarza dla każdego zasobu, a następnie korygowanie informacji w tym kalendarzu, gdy zasób ma przestoje i inne problemy. Jednak ten sposób poważnie ogranicza zdolność aparatu do buforowania danych kalendarza, ponieważ wymaga to żądania nowych danych dla każdego zasobu i może być dużym źródłem problemów z wydajnością. Zamiast tego zaleca się ponowne użycie kalendarzy w możliwie największym stopniu między zasobami, a następnie kontrolowanie zmian czasu przestojów przez przypisanie do okresu innego identyfikatora kalendarza.

### <a name="high-number-of-working-time-slots-per-calendar-day"></a>Duża liczba przedziałów czasu pracy dziennie w kalendarzu

Ponieważ działanie aparatu polega na sprawdzeniu zdolności produkcyjnych poszczególnych przedziałów czasu, korzystne jest zminimalizowanie liczby gniazd czasu na dzień kalendarzowy. Można to zrobić na przykład analizując, czy w wynikowym harmonogramu jest ważna informacja, że co godzinę pracownicy mają 5-minutową przerwę.

### <a name="large-or-none-scheduling-timeouts"></a>Duże (lub brak) limity czasu planowania

Wydajność aparatu planowania można zoptymalizować przy użyciu parametrów znajdujących się na stronie **Parametry planowania**. Ustawienia **Limit czasu planowania włączony** i **Limit czasu optymalizacji włączony** muszą zawsze mieć wartość **Tak**. Jeśli jest ustawiona wartość **Nie**, planowanie może działać bez ograniczeń, jeśli utworzono niemożliwą do realizacji marszrutę z wieloma opcjami.

Wartość opcji **Maksymalny czas planowania na sekwencję** określa liczbę sekund, przez jaką można najdłużej próbować znaleźć rozwiązanie dla jednej sekwencji (w większości przypadków sekwencja odpowiada jednemu zamówieniu). Wartość, która ma być używana w tym miejscu, zależy od złożoności marszruty i ustawień, takich jak ograniczone zdolności produkcyjne, a maksymalnie 30 sekund jest dobrą wartością początkową.

Wartość **Limit czasu prób optymalizacji** umożliwia określenie liczby sekund, przez jaką można szukać lepszego rozwiązania niż pierwotnie znalezione. Ma to wpływ tylko na marszruty, które używają równoległych operacji, ponieważ są one niezbędne do testowania różnych kombinacji.

> [!NOTE]
> Wartości ustawione dla limitów czasu zostaną zastosowane zarówno do planowania zwolnionych zleceń produkcyjnych, jak i planowanych zamówień w ramach modułu MRP. Dlatego ustawienie bardzo wysokich wartości może znacząco zwiększyć czas działania procesu MRP w przypadku działania planu z wieloma zaplanowanymi zleceniami produkcyjnymi.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]