---
title: Nowości i zmiany w systemie Dynamics AX 7.0 (luty 2016)
description: W tym artykule opisano nowe oraz zmienione funkcje dostępne w systemie Microsoft Dynamics AX 7.0. Ta wersja zawiera funkcje zarówno platformy, jak i aplikacji. Została wydana w lutym 2016 r.
author: sericks007
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 91243
ms.assetid: 515bc6e7-a85d-4995-95c6-6cab6c8aa0f9
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e69fddf1acd9a9388f62da63e0ca6a19c7a95f55
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287089"
---
# <a name="whats-new-or-changed-in-dynamics-ax-70-february-2016"></a>Nowości i zmiany w systemie Dynamics AX 7.0 (luty 2016)

[!include [banner](../includes/banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w systemie Microsoft Dynamics AX 7.0. Ta wersja zawiera funkcje zarówno platformy, jak i aplikacji. Została wydana w lutym 2016 r.

## <a name="cost-management"></a>Zarządzanie kosztami

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Szybki podgląd salda zapasów, salda zapasów pracy w toku (PWT) oraz dopływu/rozchodu zapasów w wybranym roku obrachunkowym.</td>
<td>Nie dotyczy</td>
<td>Obszar roboczy <strong>Administrowanie kosztami</strong> zawiera sekcję, w której jest prezentowane zestawienie zapasów lub zapasów PWT dla wybranego okresu obrachunkowego. Zestawienie to jest oparte na pamięci podręcznej zestawu danych, która domyślnie jest aktualizowana co 24 godziny. Pamięć podręczną zestawu danych można skonfigurować tak, aby użytkownicy mogli ją aktualizować ręcznie na potrzeby sprawozdawczości w czasie rzeczywistym. Karta <strong>Stan odświeżania danych</strong> w obszarze roboczym <strong>Administrowanie kosztami</strong> pokazuje, kiedy ostatnio aktualizowano pamięć podręczną.</td>
<td>Kontrolerzy kosztów chcą wiedzieć, czy saldo zapasów lub zapasów PWT zwiększa się czy zmniejsza w czasie. Klasyfikując zdarzenia operacyjne w zestawieniu, kontroler kosztów może uzyskać przegląd przepływu zapasów. Zapasy lub zapasy PWT są oceniane według kosztów standardowych. Widać także łączne zarejestrowane odchylenie.</td>
</tr>
<tr>
<td>Używanie modułu <strong>Zarządzanie kosztami</strong>.</td>
<td>Nie dotyczy</td>
<td>Zarządzanie kosztami jest obszarem głównym. Konfiguracja związana z kosztami i informacje były rozproszone w modułach Zarządzanie zapasami, Kontrola produkcji i Rozrachunki z dostawcami.</td>
<td>Ponieważ wszystkie zadania, które są powiązane z zarządzaniem kosztami, zostały zebrane w jednym module, kontrolerzy kosztów mogą łatwiej obsługiwać system.</td>
</tr>
<tr>
<td>Typy księgowania, które odnoszą się do księgowania zapasów i księgowania produkcji zostały zaktualizowane.</td>
<td>Formularze <strong>Księgowanie zapasów</strong>, <strong>Zasoby</strong>, <strong>Grupa zasobów</strong> i <strong>Grupa produkcji</strong> nie zawsze są dopasowane do używanych etykiet <strong>Typ księgowania w księdze</strong>. Nie jest łatwo zrozumieć terminologię używaną w tych etykietach.</td>
<td>Etykiety zostały zaktualizowane, tak aby etykiety na stronach <strong>Księgowanie zapasów</strong>, <strong>Zasoby</strong>, <strong>Grupa zasobów</strong> i <strong>Grupa produkcji</strong> pasowały do rzeczywiście używanych etykiet <strong>Typ księgowania w księdze</strong>. Zostały także zmienione nazwy wszystkich etykiet, tak aby pasowały do zdarzeń operacyjnych. Należy zwrócić uwagę, że logika rzeczywistego księgowania nie został zmodyfikowana.</td>
<td>Teraz można łatwiej skonfigurować system, ponieważ nowe etykiety są powiązane z zdarzeniami operacyjnymi, korzystającymi z tego typu księgowania.</td>
</tr>
<tr>
<td>Importowanie/eksportowanie ceny zakupu, koszty, ceny sprzedaży z programu Microsoft Excel do lub z wersji wyceny.</td>
<td>Nie można poprawnie importować cen lub kosztów do wersji wyceny, ponieważ model danych wymaga identyfikatora tabeli InventDim.</td>
<td>Wprowadzenie jednostki danych umożliwia wdrożenie funkcji importu/eksportu. Ta funkcja umożliwia użytkownikom import/eksportu ceny lub koszty do wersji wyceny.
<ul>
<li>Można zaimportować pełną listę cen zakupu w następnym roku uzyskaną z działu zakupów.</li>
<li>Można także przesunąć koszty i standardowe ceny sprzedaży z centrali do jednej lub kilku firm zajmujących się sprzedażą w ramach jednej operacji.</li>
</ul></td>
<td>Kontrolerzy kosztów mogą oszczędzić mnóstwo czasu wykorzystywanego na obsługę systemu, zwłaszcza kiedy muszą obsługiwać wstępnie określone koszty na kolejny rok obrachunkowy.</td>
</tr>
<tr>
<td>Można uzyskać szybki przegląd salda magazynowego i średni koszt jednostkowy obiektu kosztów.</td>
<td>Użytkownik musi otworzyć podręczny formularz i wybrać wymiary magazynowe, które odzwierciedlają obiekt kosztów. W związku z tym użytkownik musi wiedzieć, jakie wymiary magazynowe zostały oznaczone dla magazynu finansowego dla określonego produktu.</td>
<td>Została wprowadzona nowa strona <strong>Obiekt kosztów</strong>. Domyślnie na tej stronie są pokazane wszystkie obiekty kosztów związanych z produktem. Strona pokazuje bieżący stan zapasów, wartości i średni koszt jednostkowy na obiekt kosztów.</td>
<td>Niektóre złożone aspekty zostały usunięte i ułatwiono pracę kontrolerom kosztów.</td>
</tr>
<tr>
<td>Używanie nowej strony <strong>Wpisy kosztów</strong> stronę podczas kontroli zapasów.</td>
<td>Kontrolowanie zapasów w przypadku zarejestrowanych transakcji magazynowych i pokrewnych rozliczeń może być trudne, bo te same transakcje mogą być fizyczne lub finansowe.</td>
<td>Strona <strong>Wpisy kosztów</strong> oferuje nowy sposób wyświetlania transakcji magazynowych.
<ul>
<li>Transakcje są pokazywane w porządku chronologicznym.</li>
<li>Uwzględniane są tylko transakcje, które składają się na koszty.</li>
<li>Nie ma informacji o kosztach fizycznych lub finansowych.</li>
<li>Nie ma informacji o ilości fizycznej lub ilości finansowej.</li>
<li>Koszty są dodawane stopniowo.</li>
</ul></td>
<td>Kontrolerzy kosztów mogą oszczędzić znaczną ilość czasu podczas kontrolowania zapasów na poziomie transakcji.</td>
</tr>
<tr>
<td>Używanie nowego okna dialogowego <strong>Zestawienie PWT produkcji</strong> do obejrzenia sumarycznego widok skumulowanych kosztów dla określonego produktu.</td>
<td>Nie dotyczy</td>
<td>Zestawienie PWT pokazuje sumaryczne Saldo PWT określonego zlecenia produkcyjnego, pogrupowane na odpowiednie klasyfikacje kosztów. Wykres przedstawia w porządku chronologicznym, jaki jest wpływ księgowania operacyjnego na saldo PWT.</td>
<td>Kontrolerzy kosztów mogą zaoszczędzić mnóstwo czasu, kiedy muszą się dowiedzieć, jakie jest bieżące saldo PWT określonego zlecenia produkcyjnego lub ile materiału zużyto w ramach zamówienia.</td>
</tr>
<tr>
<td>Można skorzystać z funkcji Wyświetl porównanie kosztów wprowadzonej w module zleceń produkcyjnych. Ta funkcja ułatwia porównanie kosztów związanych ze zleceniem produkcyjnym.</td>
<td>Użytkownik może porównywać tylko koszty szacowane i zrealizowane. Porównanie może odbywać się na najniższym poziomie.</td>
<td>Funkcja porównanie kosztów umożliwia porównywanie następujących danych:
<ul>
<li>Aktywny koszt w stosunku do kosztów szacowanych = Odchylenie planowania</li>
<li>Koszty szacowane w stosunku do kosztów zrealizowanych = Odchylenie produkcji</li>
<li>Odchylenie planowania + Odchylenie produkcji = Łączne odchylenie</li>
</ul>
Ta funkcja działa niezależnie od metod wyceny, które są przypisane do produkowanego towaru. Domyślnie wykres pokazuje porównanie kosztów według typu grupy kosztów. Wykres pozwala przejść do bardziej szczegółowych poziomów.</td>
<td>Umożliwia kontrolerom kosztów i menedżerom produkcji określenie źródeł odchyleń produkcji i ich przyczyn.</td>
</tr>
</tbody>
</table>

## <a name="developer"></a>Deweloper

| Co można zrobić? | Dynamics AX 2012 | Dynamics AX 7.0 | Dlaczego to jest ważne? |
|------------------|------------------|-----------------|------------------------|
| Można tworzyć rozwiązania oparte na sieci web w chmurze, które są dostępne w wielu urządzeń. | Niedostępna | Bieżąca wersja systemu Dynamics AX została zbudowana na kliencie sieci web i strukturze klienckiej. | Umożliwia to zapewnienie użytkownikom końcowym najnowocześniejszych rozwiązań. |
| Program Microsoft Visual Studio umożliwia opracowywanie rozwiązań. | Microsoft MorphX jest głównym środowiskiem programowania, ale niektóre elementy można wykonać w programie Visual Studio. | Program Visual Studio jest jedynym środowiskiem programowania. | Zachowuje koncepcje znane z wersji Dynamics AX 2012 i bezproblemowo adaptuje je w strukturze i paradygmatach oprogramowania Visual Studio. Umożliwia standardowe współdziałanie z innymi językami i projektami języków .NET. |
| Umożliwia kompilację wspólnego języka pośredniego (CIL) dla wszystkich języków. | X ++ skompilowano do pseudokodu. | Całkowicie nowy kompilator X ++ generuje CIL dla wszystkich funkcji. CIL jest tym samym pośrednim językiem, który jest używany przez inne języki .NET. | CIL jest szybszy, może efektywnie odwoływać się do klas w zarządzanych bibliotek dołączanych dynamicznie (DDL) i może działać na dużej bazie narzędzi funkcji .NET. |
| Umożliwia osadzenie raportów BI i wizualizacji w kliencie systemu Microsoft Dynamics AX. | Niedostępna | Tworzenie bardzo intuicyjnych i płynnych wizualizacji. | Zawiera on wgląd w podejmowanie decyzji w oparciu o analizę biznesową. |
| Integracja z programem Microsoft Office. | Niedostępna | Nowe funkcje obejmują aplikację Excel Data Connector, stronę **Projektant skoroszytów**, interfejs API eksportowania oraz Zarządzanie dokumentami. | Można tworzyć rozwiązania poprawiające wydajność dla użytkowników końcowych. |
| Automatyczne kompilowanie, testowanie i wdrażanie. | Dostępne częściowo | Do wdrażania topologii dla deweloperów służą wirtualne maszyny do programowania i kompilacji. Automatyczne konfigurowanie wirtualnej maszyny kompilacji do wykrywania, tworzenia modułów z programu Visual Studio Online (VSO) i testowania. Obsługiwane są kompilacje modułów języków C\# i X++ oraz odwołania. | Zwiększa to wydajność pracy deweloperów poprzez zmniejszenie kosztów i nakładów pracy do testowania i weryfikacji. |
| Dostosowywanie z nakładaniem i rozszerzaniem. | Rozszerzenia nie są dostępne. | Bieżąca wersja systemu Dynamics AX zawiera nowy model personalizacji. | Można dostosować kod źródłowy i metadane elementów modelu, które zostały wysłane przez firmę Microsoft lub partnerów zewnętrznych firmy Microsoft. |
| Tworzenie nowych formantów i elementów interfejsu użytkownika za pomocą kodu X ++ i struktury nowoczesnej sieci web. | Formanty niestandardowe opierają się na zewnętrznych struktur, takich jak Microsoft ActiveX i Windows Presentation Foundation (WPF). | W bieżącej wersji łatwiej jest budować formanty. Struktura X++ może być używana do obsługi zachowania aplikacji i logiki biznesowej, a klient oparty na HTML/JavaScript umożliwia nowoczesne wizualizacje. | Formanty użytkownika mogą wyglądać i zachowywać się jak gotowe (out-of-box — OOB) formanty systemu Dynamics AX. |
| Nowe narzędzia do oceny i regulacji wydajności. | PerfSDK, zestaw narzędzi do rozwijania danych, internetowa aplikacja do analizy śledzenia oraz PerfTimer nie są dostępne. | PerfSDK, zestaw narzędzi do rozwijania danych, internetowa aplikacja do analizy śledzenia oraz PerfTimer są nowymi narzędziami. | Zestaw SDK umożliwia testowanie i sprawdzanie poprawności wszystkich najważniejszych wydajności w teście dla jednego użytkownika, a jeśli trzeba — dla wielu użytkowników. Zestaw narzędzie do rozwijania danych pozwala prawidłowo rozwinąć wszystkie testy wydajności, które muszą wymagają prawidłowego rozwinięcia danych głównych i transakcyjnych. Analizator śledzenia umożliwia sprawdzanie poprawności testu wydajności dla pojedynczego użytkownika lub wielu użytkowników. PerfTimer pozwala sprawdzić, czy jakakolwiek kwerenda lub wywołanie konkretnej metody powodują problemy z wydajnością. Dzięki temu nie trzeba podejmować śledzenia i analizować wszystkiego ze szczegółami. |
| Ujawnienie widoku możliwego do aktualizacji za pomocą OData. | Niedostępna | Bieżąca wersja systemu Dynamics AX wprowadza publiczny punkt końcowy usługi OData, który umożliwia spójny dostęp do danych systemu Dynamics AX z poziomu różnych aplikacji klienckich. | Twoje rozwiązania mogą współpracować z usługami RESTful, udostępniać dane w sposób umożliwiający ich odnajdywanie, oraz włączać szeroką integrację za pomocą protokołu stosu HTTP. |
| Korzystanie z programu Business Connector to tworzenia logiki biznesowej i obsługi scenariuszy integracji. | Program Business Connector jest dostępny do wywoływania kodu X++ z kodu zarządzanego. Zalecamy używanie tego programu tylko do tworzenia logiki biznesowej w języku C\#, nie w przypadku scenariuszy integracji. | Business Connector nie jest już obsługiwany. Funkcja tworzenia jest zapewniania dzięki wkompilopwaniu X ++ do kodu zarządzanego. To ułatwia międzyoperacyjność. Scenariusze integracji są realizowane za pomocą OData. | Od teraz nie można już korzystać z Business Connector. |
| Wybór skali (tj. liczby miejsc dziesiętnych) w polach rzeczywistej bazy danych i rozszerzonych typach danych (EDT). | Skala 16 jest ustawieniem domyślnym i nie programista nie może jej zmienić. | EDT i pola mają teraz właściwość skali, która może być stosowana do poszczególnych pól i rozszerzonego typu danych. Domyślna wartość to 6, a nie 16. | Tabele NCCI (obsługa w pamięci w języku SQL) działają szybciej w przypadku dużych zamówień, do których stosowana jest mniejsza skala. Skalę należy zmienić w zależności od wymagań poszczególnych pól. |

## <a name="financial-management"></a>Zarządzanie finansami

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Eksport struktur księgowych do Microsoft Excel.</td>
<td>Niedostępna</td>
<td>Teraz można wybrać strukturę konta i wyeksportować ją do programu Excel.</td>
<td>Wielu odbiorców pytało o możliwość eksportowania struktury kont do programu Excel, aby ułatwić filtrowanie.</td>
</tr>
<tr>
<td>Wyświetlanie ksiąg i struktur reguł zaawansowanych skojarzonych ze strukturą konta na jednej stronie.</td>
<td> Użytkownik musi przejść do wielu formularzy, aby zobaczyć używane księgę i strukturę konta.</td>
<td>Do strony struktury konta dodano pole informacyjne.</td>
<td>Łatwiej jest uzyskać dostęp do ważnych informacji podczas edytowania i definiowania struktury kont.</td>
</tr>
<tr>
<td>Wyświetlanie ksiąg skojarzonych z planem kont na jednej stronie.</td>
<td>Użytkownik musi przejść do każdej firmy i otworzyć formularz księgi, aby wyświetlić plan kont, który jest przypisany do księgi.</td>
<td>Do strony <strong>Plan kont</strong> dodano pole informacyjne.</td>
<td> Łatwiej jest uzyskać dostęp do ważnych informacji podczas edytowania i przypisywania planów kont.</td>
</tr>
<tr>
<td>Wyświetlanie korekt arkusza zamknięcia i transakcji zamknięcia w osobnych kolumnach na stronie listy <strong>bilansu próbnego</strong>.</td>
<td>Użytkownik widzi oba typy transakcji w jednej kolumnie.</td>
<td>Dodatkowy parametr został dodany do strony listy <strong>bilansu próbnego</strong>.</td>
<td>Umożliwia bardziej zwartą analizę danych i jest również wymagany przepisami raportowania w niektórych krajach/regionach.</td>
</tr>
<tr>
<td>Używanie nowej strony <strong>Globalny arkusz finansowy</strong>.</td>
<td>Niedostępna</td>
<td>Nowa strona <strong>Globalny arkusz finansowy</strong> do wprowadzania arkuszy finansowych. Uprawnienia wobec tej strony są dodawane do roli <strong>Księgowy</strong>.</td>
<td>Umożliwia księgowemu w centrum usług wspólnych wypełnianie arkusze finansowych różnych firm bez konieczności wychodzenia z formularza ani przełączania kontekstu firmy.</td>
</tr> 
<tr>
<td>Używanie nowej strony <strong>Eksplorator źródeł księgowania</strong>.</td>
<td>Funkcja dostępna od wersji Dynamics AX 2012 R3 z aktualizacją zbiorczą 10.</td>
<td>Nowa strona <strong>Eksplorator źródeł księgowania</strong> oraz opcje przechodzenia do niej ze strony listy <strong>Bilans próbny</strong> i strony <strong>Transakcje na załączniku</strong>.</td>
<td>Umożliwia obejrzenie najbardziej szczegółowych informacji o źródle bilansu próbnego lub wpisu księgowania w księdze głównej albo wykonanie doraźnej (ad hoc) analizy.</td>
</tr>
<tr>
<td>Dodawanie kolejnych warstw księgowania.</td>
<td>Tylko programiści mogli dodawać kolejne warstwy księgowania.</td>
<td>Teraz łącznie można mieć 10 warstw księgowania.</td>
<td>Większość klientów dodaje warstwy księgowania ponad domyślne minimum ustawione w systemie.</td>
</tr>
<tr>
<td>Używanie opcji Powiązany załącznik.</td>
<td>Niedostępna</td>
<td>Opcja Powiązany załącznik jest dostępna dla użytkowników chcących widzieć załącznik firmy przeciwstawnej podczas księgowania transakcji międzyfirmowych. W powiązanych załącznikach użytkownicy mogą kliknąć szczegóły i szybko przejść do załącznika firmy przeciwstawnej.</td>
<td>Podczas księgowania transakcji międzyfirmowych użytkownicy nie mogli zobaczyć ani dotrzeć do załącznika, który został zaksięgowany w firmie przeciwstawnej.</td>
</tr>
<tr>
<td>Grupowe zamknięcie okresu obrachunkowego</td>
<td>Niedostępna</td>
<td>Użytkownicy mogą aktualizować dostęp do modułu i zmieniać stan okresu dla wielu firm równocześnie.</td>
<td>Przed tą funkcją użytkownicy musieli zmieniać firmę, w której byli zalogowani, przechodzić do formularza kalendarza księgi oraz ręcznie aktualizować dostęp do modułu i stan okresu.</td>
</tr>
<tr>
<td>Dostarczanie kursów wymiany walut z serwisu Oanda.</td>
<td>Tylko programiści mogli konfigurować importowanie kursów wymiany z serwisu Oanda jako dostawcy.</td>
<td>Jeśli użytkownicy mają klucz dostępu do serwisu Oanda, mogą go wprowadzić podczas konfigurowania dostawcy kursów wymiany.</td>
<td>Użytkownicy mogą korzystać z gotowej funkcji importowania kursów wymiany z serwisu Oanda według ustawionego przez siebie harmonogramu.</td>
</tr>
<tr>
<td>Filtrowanie raportów finansowych (Management Reporter) na podstawie wymiarów, atrybutów, dat i scenariuszy.</td>
<td> Całość filtrowania raportów programu Management Reporter odbywa się w oparciu o projekt raportu. Na przykład jeśli użytkownik, który ma uprawnienia do przeglądania, chce wyświetlić raport dla innej daty, projektant raportu musi wprowadzić odpowiednią zmianę.</td>
<td>Dodano opcje raportu, dzięki czemu można stosować różne filtry, gdy użytkownik wyświetla raport. Nowy raport jest następnie generowany na podstawie tych filtrów.</td>
<td>Konsumenci sprawozdań finansowych mogą stosować różne filtry dla wymiarów, dat, atrybutów i scenariuszy bez konieczności aktualizowania projektów raportów.</td>
</tr>
<tr>
<td>Wyświetlanie raportów finansowych (Management Reporter) na kliencie systemu Microsoft Dynamics AX.</td>
<td>Do obsługi wyświetlania raportów programu Management Reporter użyto oddzielnego klienta sieciowego.</td>
<td>Wszystkie raporty finansowe można wyświetlić w kliencie systemu Dynamics AX. Użytkownik wybiera raport do wyświetlenia i raport jest wyświetlany na komputerze klienckim.</td>
<td>Teraz można wyświetlać raporty finansowe bez konieczności uzyskiwania dostępu do różnych aplikacji/klientów.</td>
</tr>
<tr>
<td>Drukowanie raportów finansowych (Management Reporter) z klienta systemu Microsoft Dynamics AX.</td>
<td>Drukowanie raportu odbywa się przy użyciu opcji drukowania dostępnych w przeglądarce i obejmuje tylko zawartość widzianą przez użytkownika na ekranie.</td>
<td>Użytkownik może wybrać poziom szczegółowości i ustawienia strony raportu przy użyciu opcji Drukuj dostępnej w oknie raportu finansowego na kliencie systemu Dynamics AX.</td>
<td>Raporty są drukowane w sposób oczekiwany przez użytkownika, a nie tak jak pozwala strona internetowa.</td>
</tr><tr>
<td>Analizowanie danych finansowych za pomocą pakietu zawartości „Monitorowanie wyników finansowych” dla narzędzia Power BI.</td>
<td>Niedostępna</td>
<td>Na stronie PowerBI.com wybierz opcję <strong>Pobierz dane</strong>, a następnie wybierz pakiet zawartości <strong>Dynamics AX — wyniki finansowe</strong>. Wpisz URL dla punktu końcowego Dynamics AX, aby wyświetlić dane na pulpicie nawigacyjnym.</td>
<td>W trzech lub czterech kliknięcia można wdrożyć pulpit nawigacyjny Power BI, który zawiera ważne dane finansowe. Zawartość można spersonalizować.</td>
</tr>
<tr>
<td>Śledzenie procesów zamknięcia okresu obrachunkowego.</td>
<td>Niedostępny</td>
<td>Szablony zamykania i harmonogramy mogą być tworzone za pomocą Konfiguracji zamknięcia okresu obrachunkowego. Za pomocą obszaru roboczego <strong>Zamknięcie okresu obrachunkowego</strong> można śledzić postęp harmonogramów zamknięcia w wielu firmach.</td>
<td>Ten obszar roboczy eliminuje ręczne systemy definiowania, planowania i informowania o działaniach zamknięcia. Z tego względu liczba dni do zamknięcia jest zmniejszana.</td>
</tr>
<tr>
<td>Monitorowanie budżetu w porównaniu z wartościami rzeczywistymi i tworzenie prognoz księgi za pomocą obszaru roboczego <strong>Budżety i prognozy księgi</strong> oraz dodatkowych formularzy zapytań.</td>
<td>Niedostępna</td>
<td> Obszar roboczy jest dostępny przez pulpit nawigacyjny systemu Dynamics AX. Zawiera łącza do kilku nowych stron zapytań: podsumowania <strong>Wartości rzeczywiste a budżet</strong>, podsumowanie <strong>Statystyka kontroli budżetu</strong>, <strong>Wpisy do rejestru budżetu</strong> i <strong>Plany budżetu</strong>.</td>
<td>Nowe strony zapytań zapewniają łatwy dostęp do informacji o budżecie. Obszar roboczy łączy wszystkie zadania zarządzania budżetem i monitorowania go w jednym miejscu, które jest łatwe w obsłudze dla kierowników odpowiedzialnych za budżet i księgowość.</td>
</tr>
<tr>
<td>Tworzenie układów dla planów budżetu i prognoz.</td>
<td>Dokument <strong>Plan budżetu</strong> jest wyświetlany jako lista wierszy z datami obowiązywania i kwotami dla kombinacji wymiarów finansowych. Użytkownik musi utworzyć szablony programu Excel i korzystać z nich do przeglądania danych planu budżetu w tabeli przestawnej.</td>
<td>Dostępna jest nieograniczona liczba układów dla planów budżetu i prognoz. W układzie można łączyć wybrane wymiary finansowe, zdefiniowane przez użytkownika kolumny i inne atrybuty wiersza (na przykład komentarze, projekty i zasoby). Można na bieżąco przełączać układ na dokument planu budżetu i edytować dane za pomocą dowolnego wybranego układu. Konfiguracja planowania budżetu jest uproszczona poprzez wyeliminowanie ograniczeń scenariusza i używanie układów do definiowania danych, które można wyświetlać i edytować na każdy etapie dokumentu planu budżetu.</td>
<td>To zapewnia swobodę tworzenia i edytowania planów budżetu przy użyciu programu Excel i klienta systemu Dynamics AX. Szablony skoroszytów programu Excel mogą być generowane przy użyciu ustawienia układu planu budżetu.</td>
</tr>
<tr>
<td>Drukowanie raportu <strong>Transakcje dotyczące faktury od dostawcy</strong> za pomocą informacji z raportu <strong>Szczegółowa lista transakcji do zapłaty</strong>, który zawiera dni zaległe.</td>
<td>Trzeba wydrukować dwa różne raporty: <strong>Szczegółowa lista transakcji do zapłaty</strong> i <strong>Transakcje dotyczące faktury od dostawcy</strong>.</td>
<td>Informacje na dwóch raportach zostały skonsolidowane w raporcie <strong>Transakcje dotyczące faktury od dostawcy</strong>. Raport <strong>Szczegółowa lista transakcji do zapłaty</strong> został wycofany.</td>
<td>Eliminuje to konieczność drukowania dwóch oddzielnych, ale powiązanych zez sobą raportów.</td>
</tr>
<tr>
<td>Generowanie regulaminowych raportów bezpośrednio w formacie PDF.</td>
<td>Najpierw należy wygenerować regulaminowy raport w jednym z dostępnych formatów, a następnie wyeksportować go do PDF.</td>
<td>Format PDF jest domyślny formatem dla regulaminowych raportów.</td>
<td>Oferuje ujednolicony interfejs odczytu tak na ekranie, jak i na papierze.</td>
</tr>
<tr>
<td>Uruchamianie procesu rozliczania podatku jako zadania wsadowego.</td>
<td>Niedostępny</td>
<td>Na stronie <strong>Okres rozliczenia podatku</strong> można określić, czy proces rozliczania powinien być uruchamiany w trybie wsadowym.</td>
<td>Dla okresów, które mają wiele transakcji podatku, proces rozliczenia może zajmować dużo czasu, i lepszym rozwiązaniem może być uruchomienie procesu w tle jako zadania wsadowego.</td>
</tr>
</tbody>
</table>

## <a name="foundation"></a>Podstawowy

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Dostęp do klienta w dowolnym miejscu i czasie.</td>
<td>Klient desktopowy systemu AX 2012 zawiera pełny zestaw formularzy, ale można go uruchamiać tylko na komputerach z systemem Microsoft Windows i wymaga on instalacji. Wraz z klientem desktopowym używany jest często Terminal Server, aby umożliwić dostęp przez sieć rozległą (WAN). Klient sieciowy Enterprise Portal oferuje ograniczony zestaw formularzy.</td>
<td>Dwie aplikacje klienckie systemu AX 2012 zostały zastąpione przez jedną standardową aplikację kliencką, oferującą pełne zestaw funkcji klienta desktopowoego wraz z zasięgiem dostępnym za pomocą klienta Enterprise Portal.</td>
<td>Dzięki temu prace programistyczne mogą być w prowadzone w jednym wspólnym środowisku. Dzięki zastosowaniu standardowych interfejsów sieci web Terminal Server nie jest już potrzebny.</td>
</tr>
<tr>
<td>Produktywność dzięki nowemu Rejestratorowi zadań.</td>
<td>Rejestrator zadań w systemie AX 2012 wymaga bezpośredniego dostępu do komputera serwera obiektów aplikacji (Application Object Server — AOS) i wyższych uprawnień, i nie oferuje żadnych opcji edycji.</td>
<td>Nowy Rejestrator zadań może być używany bezpośrednio z poziomu klienta sieci web. Dostęp do Rejestratora zadań nie wymaga uprawnień administratora. Zarejestrowane czynności mogą być wyświetlane na żywo podczas rejestrowania, wprowadzono nowe opcje edytowania, a Rejestrator zadań obsługuje więcej scenariuszy oprócz istniejących scenariuszy modelowania procesu biznesowego (BPM).</td>
<td>Nowy Rejestrator zadań oferuje zoptymalizowane środowisko i obsługę nowych funkcji w systemie Dynamics AX. Niektóre z tych funkcji są dostępne już teraz, a wkrótce pojawią się kolejne.</td>
</tr>
<tr>
<td>Pomaganie użytkownikom w lepszym poznaniu nachodzącej pracy dzięki obszarom roboczym.</td>
<td>Widok główny użytkownika zawiera przegląd informacji dotyczących funkcji stanowiska użytkownika w firmie lub organizacji.</td>
<td>Obszary robocze to nowa koncepcja w systemie Dynamics AX. Mają one zastąpić widoki główne użytkownika jako podstawowy sposób nawigowania do zadań i konkretnych stron. Zapewniają one jednostronicowy przegląd aktywności biznesowej i pomagają użytkownikom poznać aktualny stan, nadchodzące prace oraz efektywność procesu lub użytkownika. Obszary robocze są bardziej szczegółowe niż widoki główne użytkownika w systemie AX 2012, a użytkownik może mieć dostęp do wielu obszarów roboczych.</td>
<td>Obszary robocze mają poprawić wydajność pracy użytkowników. Programiści muszą utworzyć obszar roboczy dla każdej istotnej „aktywności” wykonywanej dla produktu. Dotychczasowy widok główny użytkownika w systemie AX 2012 zostanie przeważnie zastąpiony przez wiele obszarów roboczych w bieżącej wersji systemu Dynamics AX.</td>
</tr>
<tr>
<td>Reagowanie formularzy na wielkość okienka ekranu przeglądarki lub wielkość ekranu urządzenia.</td>
<td>W systemie AX 2012 zawartość formularza była sztywno określona przy użyciu kolumn, a ogólna wysokość/szerokość formularza w dużej mierze zależała od wielkości formantów formularza.</td>
<td>Po migracji do Internetu zastosowanej w najnowszej wersji systemu Dynamics AX wymiary formularza są teraz oparte na rozmiarze okienka ekranu przeglądarki lub rozmiarze ekranu urządzenia. Formanty i parametry układu zmodyfikowano lub dodano w taki sposób, aby lepiej reagowały na zmianę wielkości okienka ekranu.</td>
<td>Zawartości formularza musi być bardziej elastyczna, aby optymalnie wykorzystywać dostępną wysokość/szerokość przeglądarki lub urządzenia. Ta elastyczność może wymagać zmian w sposobie modelowana formularza.</td>
</tr>
<tr>
<td>Używanie wzorców w celu łatwiejszego opracowywania formularzy.</td>
<td>Szablony formularzy były dostępne jako punkty wyjściowe przy projektowania formularzy w systemie AX 2012 na podstawie stylu formularza. Opcjonalny dodatek sprawdzania stylu formularza (Form Style Checker) przekazywał informacje o tym, w taki sposób formularz odbiegał od odnośnego szablonu.</td>
<td>W obecnej wersji systemu Dynamics AX wprowadzono koncepcję wzorców formularzy. Wzorce formularzy stanowią połączenie funkcji szablonów formularzy i dodatku Form Style Checker, i są ściśle zintegrowane z procesem projektowania. Wzorce zdefiniowano na poziomie formularzy (podobnie jak w systemie AX 2012), ale dodano podwzorce na poziomach grup i kart.</td>
<td>Formularze zgodne z wzorcami mają wiele zalet, w tym bardziej spójny interfejs użytkownika, prostsze projektowanie, łatwiejszą ścieżkę uaktualniania oraz lepsze reagowanie układu na zmiany rozmiaru okna/urządzenia.</td>
</tr>
</tbody>
</table>

## <a name="help"></a>Pomoc

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Dostęp do pomocy dla procedur (przewodniki po zadaniach) i omówień różnych elementów systemu za pomocą przycisku <strong>Pomoc</strong>.</td>
<td>System AX 2012 wskazuje tematy HTML, które są przechowywane na lokalnym serwerze sieciowym. Klienci i partnerzy można utworzyć swoją własną bibliotekę tematów pomocy.</td>
<td>System pomocy w bieżącej wersji systemu Dynamics AX służy do wyświetlania przewodników po zadaniach zapisanych w Microsoft Dynamics Lifecycle Services (LCS) BPM. System pomocy wyświetla też tematy z witryny dokumentów firmy Microsoft. Aby uzyskać więcej informacji, zapoznaj się z <a href="help-overview.md" data-raw-source="[Help system](help-overview.md)">System Pomocy</a> i <a href="new-task-guides-available-february-2016.md" data-raw-source="[New task guides (February 2016)](new-task-guides-available-february-2016.md)">nowe przewodniki po zadaniach (luty 2016)</a>.</td>
<td>Przewodniki po zadaniach oferują interaktywne prezentacje poszczególnych kroków w zadaniach i procesach biznesowych. Przewodniki po zadaniach udostępnione przez Microsoft można pobrać i dostosować. Artykuł przedstawia szybsze i bardziej elastyczne sposoby tworzenia, dostarczania i aktualizowania dokumentacji produktu. To pomaga zagwarantować, że użytkownik ma dostęp do najnowszych informacji technicznych.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Zarządzanie kapitałem ludzkim

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Przenoszenie umiejętności i certyfikatów na uczestników zajęć po zakończeniu kursu.</td>
<td>Jest to proces ręczny.</td>
<td>Po ukończeniu kursu dostępna jest nowa opcja pozwalająca aktualizować rekordy uczestników o nowe umiejętności i certyfikaty.</td>
<td>Jest to nowy i wydajny sposób aktualizacji rekordów pracowników.</td>
</tr>
<tr>
<td>Szybkie weryfikowanie stanu zatrudnienia.</td>
<td>Jest to proces ręczny.</td>
<td>Dzięki temu w dziale zasobów ludzkich można szybko sprawdzić stan zatrudnienia za pomocą strony obszaru roboczego lub pracownika.</td>
<td>Pracownicy działu zasobów ludzkich nie muszą już wyświetlać wielu stron w celu sprawdzenia daty początkowej, nazwiska kierownika, miesięcy zatrudnienia na danym stanowisku i wysokości wynagrodzenia.</td>
</tr>
<tr>
<td>Zawalanie pracownikom na wyświetlanie, aktualizowanie i usuwanie informacji w systemie.</td>
<td>Dostępne, ale z ograniczonymi możliwościami wyświetlania i aktualizacji.</td>
<td>Ta funkcja jest włączona i i umożliwia pracownikom i zleceniobiorcom wyświetlanie różnych danych osobowych. Opcjonalnie do tworzenia, aktualizowania lub usuwania informacji można używać przepływu pracy.</td>
<td>To pozwala pracownikom uzyskać kontrolę nad informacjami, niezależnie od tego, czy chodzi o aktualizację adresu lub danych kontaktowych, podanie o pracę, wypełnienie kwestionariusza czy aktualizację zdjęcia. Gdy przepływ pracy jest włączony, informacje mogą być przeglądane przez osobę zatwierdzającą lub automatycznie zatwierdzane na podstawie procesów biznesowych użytkownika.</td>
</tr>
<tr>
<td>Zezwalanie kierownikom na wyświetlanie lub edytowanie informacji o pracowniku.</td>
<td>Dostępne, ale z ograniczonymi możliwościami wyświetlania i aktualizacji.</td>
<td>W zależności od ustawień konfiguracji i zabezpieczeń kierownicy mogą wyświetlać lub edytować informacje o pracowniku.</td>
<td>Dzięki temu kierownicy mają dostęp do ważnych danych pracownika, co ułatwia podejmowanie prawidłowych decyzji dotyczących zaopatrzenia, wydajności i rozwoju kadry pracowniczej.</td>
</tr>
<tr>
<td>Korzystanie z funkcji samoobsługi przez kierowników.</td>
<td>Niedostępna</td>
<td>Menedżerowie mogą teraz wysyłać wnioski o nowych pracowników (etatowych i zleceniobiorców), przeniesienia i wypowiedzenia (zakończenie zatrudnienia). Mogą również prosić o nowe stanowisko, przedłużenie czasu istnienia stanowiska lub wprowadzenie zmian na stanowisku.</td>
<td>Te scenariusze wcześniej były dostępne tylko dla pracowników działu kadr. Udostępnienie ich kierownikom w całej organizacji stanowi ogromne ułatwienie w pracy. Opcjonalnie można wdrożyć przepływy pracy zapewniające odpowiedni poziom weryfikacji i zatwierdzania.</td>
</tr>
<tr>
<td>Dostęp do wyników przetwarzania wynagrodzeń.</td>
<td>Wyniki są dostępne tylko w czasie przetwarzania.</td>
<td>Wyniki przetwarzania wynagrodzeń są teraz dostępne z dowolnego miejsca po uruchomieniu procesu.</td>
<td>Pozwala to przeprowadzić szczegółową inspekcję procesu i jego wyniku. Daje też wszechstronny ogląd danych przed zaktualizowaniem rekordów pracownika.</td>
</tr>
<tr>
<td>Dostęp do wyników przetwarzania świadczeń.</td>
<td>Wyniki są dostępne tylko w czasie przetwarzania.</td>
<td>Wyniki przetwarzania świadczeń są teraz dostępne z dowolnego miejsca po uruchomieniu procesu.</td>
<td>Dostępny jest wszechstronny widok danych, który jest aktualizowany za pomocą zapisywania na świadczenie i zmian kosztów.</td>
</tr>
<tr>
<td>Widok „Data obowiązywania” zmienia się.</td>
<td>Niedostępna</td>
<td>To narzędzie do porównywania jest dostępne dla pracowników, stanowisk i zadań. Oferuje ono wszechstronny widok zmian między jedną wersją rekordu a drugą.</td>
<td>Pozwala zaoszczędzić czas podczas wyświetlania zmian rekordów pracowników, stanowisk i zadań na przestrzeni czasu. Pozwala szybko porównywać dwie wersje rekordu lub wszystkie rekordy na osi czasu.</td>
</tr>
<tr>
<td>Wyświetlanie pracowników według firmy.</td>
<td>To jest proces wykonywany ręcznie za pomocą filtrowania.</td>
<td>Listy pracowników i zleceniobiorców są automatycznie filtrowane wg firmy, w której użytkownik jest zalogowany.</td>
<td>Zawiera ona filtrowany widok pracowników, którzy są zatrudnieni w zalogowanej firmie. Aby wyświetlić niefiltrowany widok wszystkich pracowników i zleceniobiorców, zawsze można skorzystać z listy pracowników. W bieżącej wersji systemu Dynamics AX system nie zmienia firmy według pracownika zaznaczonego na liście.</td>
</tr>
<tr>
<td>Aktualizowanie listy uczestników kursu.</td>
<td>Niedostępny</td>
<td>Uczestnicy kursu mogą być usuwani z listy uczestników.</td>
<td>Zapewnia to prosty sposób aktualizowania uczestników kursu, którzy zarejestrowali się przez pomyłkę.</td>
</tr>
<tr>
<td>Zarządzanie zdarzeniami dotyczącymi wynagrodzenia w grupie.</td>
<td>Niedostępny</td>
<td>Ta funkcja upraszcza przetwarzanie zmian wynagrodzeń dla pracowników.</td>
<td>Oferuje prosty zoptymalizowany proces aktualizacji rekordów pracowników za pomocą obszaru roboczego wynagrodzeń i powiązanych stron.</td>
</tr>
</tbody>
</table>

## <a name="inventory-management"></a>Zarządzanie zapasami

Nie dodano żadnych nowych funkcji.

## <a name="localization"></a>Lokalizacja

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Konfigurowanie i generowanie dokumentów elektronicznych pod kątem wymagań prawnych w różnych krajach/regionach.</td>
<td>Dokumenty elektroniczne są zakodowane na stałe w X++ lub jako Extensible Stylesheet Language Transformations (XSLT). Wszelkie zmiany formatu wymagają prac programistycznych. Dostęp do danych i formatowanie nie są izolowane. Rozmieszczenie poprawionych formatów wymaga nowego pakietu poprawek do systemu Microsoft Dynamics AX, który zastępuje istniejący format. Niestandardowe modyfikacje każdego formatu muszą być ręcznie przenoszone do kodu źródłowego nowego pakietu poprawki systemu Microsoft Dynamics AX.</td>
<td>Raportowanie elektroniczne (Electronic Reporting, ER) jest nowym narzędziem do konfigurowania i generowania dokumentów elektronicznych przeznaczonym dla użytkownika biznesowego, a nie dla programisty. ER pozwala ustawić modele danych, które są właściwe dla domeny i niezależnie od bazy danych systemu Microsoft Dynamics AX, jako źródła danych dla formatów dokumentów. Użytkownik biznesowy może skonfigurować formaty na podstawie tych modeli danych właściwych dla domeny (np. dla płatności, raporty Intrastat lub raporty podatkowe). Użytkownik konfiguruje formaty za pomocą prostych wizualnych narzędzi przypominających program Excel. ER aktualnie obsługuje generowanie dokumentów elektronicznych w formie tekstu, XML i plików programu Excel. Te dokumenty mogą być generowane jednocześnie i pakowane do plików zip. Modele danych i formaty obsługują przechowywanie wersji. Wersje formatów mogą mieć różne okresy. Każdy model danych lub wersja formatu są przechowywane w oddzielnej konfiguracji i dystrybuowane do partnerów i odbiorców przez LCS. Partnerzy i odbiorcy mogą dostosowywać modele danych i formaty Microsoft, albo tworzyć własne. ER zapisuje zmiany konfiguracji partnerów i odbiorców jako różnice w konfiguracjach oprogramowania Microsoft, co upraszcza uaktualnianie do nowych wersji konfiguracji takiego oprogramowania. Za pomocą portalu LCS partnerzy mogą też udostępniać swoje konfiguracje modeli danych i formatów innym partnerom i odbiorcom, którzy mogą je dostosowywać do własnych potrzeb i udostępniać danej. Dostosowanie delta i łatwe aktualizacje są obsługiwane w całym łańcuchu dostosowywania.</td>
<td>ER upraszcza tworzenie, obsługę i uaktualnianie formatów dokumentów elektronicznych pod kątem wymagań prawnych w różnych krajach/regionach. ER sprawia, że proces tworzenia lub zmieniania formatów dokumentów elektronicznych jest szybszy i łatwiejszy. Tych zmian mogą dokonywać użytkownicy biznesowi. Nie potrzebni są do tego programiści. ER przyspiesza i ułatwia uaktualnianie dostosowań formatów dokonanych przez partnerów i odbiorców do nowych wersji formatów publikowanych przez Microsoft lub innych partnerów. ER oferuje jedną metodę wspólną dla Microsoft i partnerów (przez portali LCS) w zakresie rozsyłania konfiguracji dokumentów elektronicznych do innych partnerów i odbiorców. Oprócz tego ER ułatwia partnerom i odbiorcom dostosowywanie, uaktualnianie i dystrybucję formatów dokumentów elektronicznych pod kątem ich konkretnych wymagań biznesowych.</td>
</tr>
<tr>
<td>(MEX) Generowanie regulaminowych raportów VAT w Meksyku.</td>
<td>Należy wygenerować raporty <strong>Podatek VAT od sprzedaży i kupna</strong> za pomocą funkcji niezrealizowanego podatku VAT, tak aby użytkownicy byli w stanie identyfikować transakcje należące do sekcji zrealizowanych i niezrealizowanych według stanu.</td>
<td>Raporty <strong>VAT od sprzedaży i kupna</strong> zostały zmodyfikowane i teraz uwzględniają funkcję podatku warunkowego tylko przy użyciu okresów rozliczeniowych dla definicji niezrealizowanych i zrealizowanych kodów podatku.</td>
<td>Aby użytkownicy mogli generować te raporty prawidłowo, wymagane są zmiany w konfiguracji kodów podatku. Wymagana jest funkcja podatku warunkowego i użytkownik musi skonfigurować oddzielne okresy rozliczeniowe, niezrealizowane i zrealizowane, aby zidentyfikować transakcje w obszarach powiązanej sekcji.</td>
</tr>
<tr>
<td>(JPN) Zarządzanie deklaracjami przyspieszonej amortyzacji środków trwałych w Japonii.</td>
<td>Niedostępny</td>
<td>Ważne informacje dotyczące deklaracji są przechowywane centralnie w jednym dokumencie dla ułatwiania obsługi.</td>
<td>Zgodność dokumenty z przepisami oraz łatwość zarządzania pomaga ograniczyć liczbę inspekcji i innych kontroli.</td>
</tr>
<tr>
<td>(JPN) Sprawdzanie znaków JBA na koncie bankowym.</td>
<td>Niedostępny</td>
<td>Można sprawdzić, czy pola nazwy Kana zawierają tylko znaki dopuszczalne w formacie banku JBA.</td>
<td>To pomaga ograniczyć przerwy podczas generowania pliku płatności wynikające z nieprawidłowych znaków.</td>
</tr>
<tr>
<td>(JPN) Wyrównywanie różnic groszowych dla środków trwałych w Japonii na koniec roku obrachunkowego.</td>
<td>Niedostępny</td>
<td>Na stronie <strong>Parametry środka trwałego</strong> można zaznaczyć opcję wyrównania na koniec okresu lub roku obrachunkowego.</td>
<td>Zapewnia to większą elastyczność pod kątem dopasowania do lokalnych praktyk.</td>
</tr>
<tr>
<td>(JPN) Generowanie serii 16 tabel dołączanych do japońskiej deklaracji podatkowej dla firm dla zsumowanej kwoty według głównego typu środka trwałego.</td>
<td>Niedostępny</td>
<td>Dla modeli ewidencji środków trwałych można wybrać podsumowanie według typu głównego. Domyślnie ta funkcja służy do obsługi nowo tworzonych środków trwałych.</td>
<td>W przypadku dużych korporacji, które mają tysiące środków trwałych, zsumowane raporty znacznie redukują rozmiar generowanego raportu.</td>
</tr>
<tr>
<td>(JPN) Rozpoczęcie alokacji rezerw amortyzacji specjalnej z nowego roku obrachunkowego dla środków trwałych w Japonii.</td>
<td>Niedostępny</td>
<td>W modelach ewidencji dla środka trwałego, który ma odpowiedni model amortyzacji specjalnej, można włączy rozpoczęcie alokacji z od następnego okresu lub roku obrachunkowego.</td>
<td>Zapewnia to większą elastyczność pod kątem dopasowania do lokalnych praktyk.</td>
</tr>
<tr>
<td>(JPN) Generowanie raportu podatku konsumpcyjnego w Japonii, który zawiera skorygowane stawki podatkowe.</td>
<td>Raport podatku konsumpcyjnego jest dostępny dla stawki podatku w wysokości 5%.</td>
<td>Raport podatku konsumpcyjnego zawiera sekcję dla skorygowanej stawki podatku (np. 8%).</td>
<td>Układ został na nowo ogłoszony przez rząd.</td>
</tr>
<tr>
<td>(Unia Europejska) Konfigurowanie ustawień zaokrąglania dla listy sprzedaży do UE.</td>
<td>Ustawienia zaokrąglania na potrzeby raportowania list sprzedaży do UE dla różnych krajów/regionów są trwale zapisane w kodzie źródłowym X++ lub XSLT (Extensible Stylesheet Language Transformations).</td>
<td>Ustawienia zaokrąglania są dodawane do okna Parametry handlu zagranicznego. Można skonfigurować dokładność zaokrąglania, metodę zaokrąglania, dokładność danych wyjściowych oraz zachowanie dla kwot mniejszych niż dokładność zaokrąglania.</td>
<td>To ujednolica i upraszcza konfigurację raportowania list sprzedaży do UE. Korekta ustawień zaokrąglania już nie wymaga angażowania programisty.</td>
</tr>
<tr>
<td>(Unia Europejska) Konfigurowanie reguł stosowania opłat zwrotnych.</td>
<td>Reguły stosowania opłat zwrotnych są zapisywane trwale w kodzie źródłowym dla scenariusza krajowych opłat zwrotnych. Progi stosowania można konfigurować według grup towarów. Ta funkcjonalność jest dostępna tylko w Wielkiej Brytanii.</td>
<td>Reguły stosowania opłat zwrotnych można konfigurować dla typów dokumentów (zamówienia zakupu/sprzedaży, faktury od dostawcy, faktury niezależne itp.) i grup opłat zwrotnych, które łączą w sobie towary, grupy towarów i kategorie zakupu/sprzedaży. Reguły stosowania mają daty obowiązywania. Można również oznaczyć pojedyncze kody podatków w grupach podatków jako podlegające opłatom zwrotnym. Raport o fakturach sprzedaży jest dopasowywany, aby reprezentował szczegóły zastosowanej opłaty zwrotnej. Ta funkcjonalność jest dostępna we wszystkich krajach/regionach Europy.</td>
<td>Ta zmiana ujednolica konfigurację stosowania reguł opłat zwrotnych i wspiera egzekwowanie krajowych przepisów o opłatach zwrotnych w krajach/regionach Europy.</td>
</tr>
<tr>
<td>(Niemcy) Generowanie niemieckiego pliku — GDPdUGoBD</td>
<td>Użytkownicy mogą konfigurować definicje tabel zawierających dane finansowe do wyeksportowania w formacie akceptowanym przez niemieckich audytorów i władze.</td>
<td>Ta funkcja została zaimplementowana jako konfiguracja raportowania elektronicznego. Ta funkcjonalność jest dostępna w Niemczech i Austrii.</td>
<td>Ta zmiana daje użytkownikom znacznie więcej możliwości w kwestii formatowania i przekształcania danych, a także zapewnia wszystkie korzyści wynikające z zarządzania cyklem życia konfiguracji raportowania elektronicznego, takie jak łatwe udostępnianie konfiguracji, przechowywanie wersji itd.</td>
</tr>
<tr>
<td>(Francja) Raport zestawienia bilansowego z kontami sum dla grup.</td>
<td>Raport zawierający zestawienie bilansowe z kontami sum dla grup jest zaimplementowany jako raport usługi SSRS (LedgerAccountSum_FR).</td>
<td>Raport zawierający zestawienie bilansowe z kontami sum dla grup jest zaimplementowany jako raport programu Management Reporter dostępny w bibliotece zasobów usługi LCS umieszczonej w folderze raportów finansowych.</td>
<td>Pozwala to użytkownikom korzystać ze wszystkich zalet i swobody dostosowywania raportów finansowych, jakie oferuje program Management Reporter.</td>
</tr>
<tr>
<td>(Unia Europejska) Raporty o zawiadomieniach o płatności, notatkach towarzyszących i kontrolne dla płatności.</td>
<td>Wszystkie te raporty są zaimplementowane jako raporty usługi SSRS.</td>
<td>Raporty te są zaimplementowane jako szablony Open XML, których można używać w programie Microsoft Excel.</td>
<td>Konfiguracje płatności elektronicznych zawierają ustawienia i szablony formatów plików płatności. Pozwala to użytkownikom korzystać ze wszystkich zalet i swobody dostosowywania raportów, jakie oferuje aplikacja Raportowanie elektroniczne.</td>
</tr>
<tr>
<td>(Unia Europejska) Konfigurowanie ustawień zaokrąglania dla sprawozdawczości Intrastat.</td>
<td>Ustawienia zaokrąglania na potrzeby raportowania Intrastat dla różnych krajów/regionów są trwale zapisane w kodzie źródłowym X++ lub XSLT (Extensible Stylesheet Language Transformations).</td>
<td>Ustawienia zaokrąglania są dodawane do okna Parametry handlu zagranicznego. Można skonfigurować dokładność zaokrąglania, metodę zaokrąglania, dokładność danych wyjściowych oraz zachowanie dla kwot mniejszych niż dokładność zaokrąglania.</td>
<td>To ujednolica i upraszcza konfigurację raportowania Intrastat. Korekta ustawień zaokrąglania już nie wymaga angażowania programisty.</td>
</tr>
<tr>
<td>(Unia Europejska) Ustawianie kodów asortymentu Intrastat w hierarchiach kategorii.</td>
u<td>Kody asortymentu Intrastat to osobna lista. Co prawda istnieje hierarchia kategorii typu Kod asortymentu, jednak może następować domyślne ustawianie kodów asortymentu w jednostce Centrala handlu detalicznego i kategoriach sprzedaży.</td>
<td>Odrębny wykaz kodów asortymentu Intrastat jest scalony z hierarchią produktów typu Kod asortymentu.</td>
<td>To ujednolica podejście do przypisywania kodów asortymentu do zwalnianych produktów i kategorii w dokumentach sprzedaży i zakupu.</td>
</tr>
<tr>
<td>(Unia Europejska) Zgłaszanie ilości w dodatkowych jednostkach dla Intrastat za pomocą ustawienia konwersji jednostek.</td>
<td>Kod asortymentu Intrastat ma pole tekstowe do identyfikacji dodatkowych jednostek, a karta <strong>Produkt</strong> zawiera pole do identyfikowania liczby dodatkowych jednostek w kilogramach.</td>
<td>Dodatkowe jednostki dla kodu asortymentu Intrastat wybiera się z listy jednostek. Liczba dodatkowych jednostek jest obliczana przy użyciu ustawień konwersji jednostek.</td>
<td>To ujednolica podejście do przeliczania z jednostek transakcji na dodatkowe jednostki.</td>
</tr>
<tr>
<td>(Unia Europejska) Przypisywanie domyślnej metody transportu do metody dostawy.</td>
<td>Niedostępna</td>
<td>Do metody dostawy dodano pole domyślnej metody transportu.</td>
<td>Upraszcza to przygotowywanie raportów Intrastat.</td>
</tr>
<tr>
<td>(Unia Europejska) Oznaczanie zwolnionych produktów, aby nie zgłaszane do Intrastat.</td>
<td>Niedostępna</td>
<td>Do zwolnionego produktu dodano opcję wykluczenia towaru z raportowania do Intrastat .</td>
<td>Upraszcza to przygotowywanie raportów Intrastat.</td>
</tr>
</tbody>
</table>

## <a name="manufacturing"></a>Produkcja

| Co można zrobić? | Dynamics AX 2012 |
|------------------|------------------|
| Sprawdzanie dostępności materiałów dla zleceń produkcyjnych na osobnej stronie, którą można otworzyć z obszaru roboczego **Zarządzanie halą produkcyjną**. | Niedostępne |
| Rozpoczynanie i zgłaszanie postępów zadań produkcyjnych na nowej stronie **Urządzenie karty zadań**. | Formularz **Rejestracji zadania** jest przeznaczony głównie dla dużych ekranów terminali, a interfejs obsługuje się zazwyczaj myszką. |

## <a name="master-planning-and-forecasting"></a>Planowanie główne i prognozy

| Co można zrobić? | Dynamics AX 2012 | Dynamics AX 7.0 | Dlaczego to jest ważne? |
|------------------|------------------|-----------------|------------------------|
| Ostrzeganie użytkownika, jeśli zamówienie sprzedaży lub zlecenie produkcyjne nie jest gotowe do dostarczenia w określonym czasie. | Ostrzeżenia, które są tworzone przez planowanie główne, są nazywane *komunikatami prognoz*. *Prognozy* to umowa między dwoma stronami na zakup lub sprzedaż zasobów za cenę uzgodnioną w dniu dzisiejszym ( *cena prognoz*), mimo że dostawa i płatność następuje w przyszłości (*data dostawy*). | *Komunikaty prognoz* i *daty prognoz* otrzymały nowe nazwy — odpowiednio *obliczone opóźnienia* i *daty opóźnienia*. | Terminologia, który jest używany w systemie AX 2012, była niedokładna i prowadziła do powstawania nieadekwatnych tłumaczeń. |
| Szybki wgląd w stan uruchomienia planowania głównego, pilnych planowanych zamówień oraz planowanych zamówień powodujących opóźnienia. | Informacje te są dostępne, ale są rozproszone w wielu formularzach. | Obszar roboczy **Planowanie główne** oferuje skrócone informacje o tym, kiedy ukończono ostatnie planowanie główne, czy wystąpiły jakiekolwiek błędy, jakie są pilne planowane zamówienia oraz które z planowanych zamówień powodują opóźnienia. | Dostępny przegląd danych w obszarze roboczym jest bardzo przydatny. Odpowiednie informacje są zestawiane, by ułatwiać planowanie główne i pomagać podnosić wydajność. |
| Używanie programu Excel do aktualizacji prognoz popytu. | Niedostępny | System został płynnie zintegrowany z programem Excel, ułatwiając wprowadzanie i usuwanie prognoz popytu oraz wprowadzanie aktualizacji. | Pomaga to zwiększyć efektywność i wydajność. |
| Szacowanie przyszłego popytu i tworzenie prognoz popytu na podstawie danych historycznych transakcji. | W systemie Microsoft Dynamics AX 2012 R3 modele prognoz w prognoz w Microsoft SQL Server Analysis Service służą do tworzenia przewidywań prognoz popytu. | Szacowanie przyszłego popytu za pomocą zaawansowanych i elastycznych opcji usługi chmurowej Microsoft Azure Machine Learning. Jest ona łatwa w użyciu i rozszerza modele prognozy w uczeniu maszynowym, by spełniać wymagania odbiorców. Usługa umieszcza na platformie wybór najlepiej dopasowanych modeli i oferuje kluczowe wskaźniki wydajności (KPI), które mogą być używane do obliczania dokładności prognozy. | Generowanie bardziej precyzyjnych prognoz za pomocą technik uczenia maszynowego. |
| Optymalizowanie daty i ilości zamówienia na podstawie wizualnego przeglądu powiązanych działań z uruchomienia planowania głównego. | Przegląd planu działań jest dostępny, ale wyświetla wszystkie powiązane działania. Działania znikają z listy natychmiast po ich zastosowaniu. | Plan działań oferuje lepszy przegląd. Zawiera opcje pozwalające wyświetlać tylko zastosowane działania i działania bezpośrednio powiązane. Gdy działania zostaną zastosowane, stają się wyszarzone, ale nadal widoczne. Z tego względu przegląd jest zatrzymywany. Dodatkowe informacje są dodawane do planu działań, by wyświetlić dane na jednej stronie. | Umożliwiają one użytkownikowi skorzystanie z poprawy wydajności, ponieważ umożliwiają skoncentrowanie się tylko na odpowiednich działaniach. |

## <a name="procurement-and-sourcing"></a>Zaopatrzenie i sourcing

| Co można zrobić? | Dynamics AX 2012 | Dynamics AX 7.0 | Dlaczego to jest ważne? |
|------------------|------------------|-----------------|------------------------|
| Za pomocą obszaru roboczego **Przygotowanie zamówienia zakupu** można zyskać szybko wgląd w stan zamówień zakupu, które są przygotowywane. | Nieobsługiwane | Obszar roboczy **Przygotowanie zamówienia zakupu** oferuje przegląd zamówień od momentu, gdy zostały utworzone w postaci wersji roboczej, przez stany przepływu pracy zatwierdzenia i dalej do potwierdzenia. | Dział zakupów nie musi już szukać informacji na wielu stronach, ale ma do dyspozycji praktyczny przegląd, jaki oferuje nowy obszar roboczy. |
| Za pomocą obszaru roboczego **Przyjęcie i obsługa zamówienia zakupu** można szybko wyświetlić zamówienia zakupu oczekujące na przyjęcie. To ułatwia wykonywanie dalszych działań. | Nieobsługiwane | Obszar **Przyjęcie i obsługa zamówienia zakupu** oferuje przegląd potwierdzonych zamówień zakupu, które mają oczekujące przyjęcia lub wysyłki. Obszar roboczy obejmuje listy zaległych i oczekujących przyjęć, aby ułatwić dostawcy proaktywny przegląd i kolejne działania. Obszar roboczy zawiera też listę zamówień zakupu, dla których zarejestrowano przyjęcia magazynowe. To pomaga zagwarantować, że przyjęcie jest księgowane. Przeglądać można też zwroty zamówień zakupu, które nie zostały jeszcze wysłane. | Dział zakupów może używać przeglądu dostępnego w obszarze roboczym. Odpowiednie informacje są zestawiane, by ułatwiać dalsze działania i pomagać podnosić wydajność. |
| Wysyłanie zamówień zakupu w celu potwierdzenia do portalu dostawców na kliencie systemu Dynamics AX. Zezwalanie dostawcom na potwierdzenie lub odrzucenie. | Nieobsługiwane | Interfejs portalu dostawców umożliwia dostawcom odbieranie zamówień zakupu w celu potwierdzenia lub odrzucenia. Oferuje również dostawcy podgląd na wszystkie potwierdzone zamówienia zakupu dla konta. Pracownik działu zakupów może wysłać zamówienie zakupu z żądaniem potwierdzenia od dostawcy. Dostawca musi być zarejestrowanym użytkownikiem usługi Microsoft Azure Active Directory (Azure AD) w systemie Dynamics AX, mieć wyznaczoną osobę kontaktową i posiadać dedykowaną rolę zabezpieczeń. | Zaletą dla działu zakupów jest mniej pracy z dokumentami papierowymi i ręcznym śledzeniem odpowiedzi na zamówienia zakupu, ponieważ zamówienia są kierowane bezpośrednio do systemu. Dzięki pobieraniu danych tylko z jednego źródła liczba nieporozumień między odbiorcą i dostawcą jest mniejsza. |

## <a name="projects"></a>Projekty

| Co można zrobić? | Dynamics AX 2012 | Dynamics AX 7.0 | Dlaczego to jest ważne? |
|------------------|------------------|-----------------|------------------------|
| Rezerwowanie pracowników jako zasobów w projektach. | Podobnie jak zasoby, pracownicy są rejestrowane bezpośrednio w projektach oprócz zasobów. | Tabela Biura obsługi, w które przechowywane są zasoby produkcyjne, może być teraz używana do księgowania pracowników jako zasobów w projekcie. | Aby zarezerwować projekt, wystarczy tylko zarezerwować zasoby. |

## <a name="retail-sales-marketing-and-customer-service"></a>Sprzedaż detaliczna, marketing i obsługa klienta

### <a name="retail-hq"></a>Centrala handlu detalicznego

Centrala handlu detalicznego w Microsoft Azure oferuje scentralizowane zarządzanie i pełną widoczność wszystkich aspektów operacji handlowych za pośrednictwem klienta sieci web.

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Wykonywanie operacji merchandisingu.</td>
<td>Użytkownicy mają dostęp do wielu formularzy, aby zarządzać tymi danymi:
<ul>
<li>Zarządzanie kategoriami</li>
<li>Zarządzanie produktem</li>
<li>Atrybuty produktu kanału</li>
<li>Asortymenty</li>
<li>Zarządzanie katalogami</li>
<li>Zestawy</li>
<li>Ceny i rabaty</li>
</ul></td>
<td>Obszar roboczy <strong>Zarządzanie kategoriami i produktami</strong> umożliwia obsługę następujących funkcji:
<ul>
<li>Zarządzanie asortymentem.</li>
<li>Śledzenie cyklu życia asortymentu.</li>
<li>Zarządzanie zwolnionymi produktami.</li>
</ul>
Obszar roboczy <strong>Zarządzanie cenami i rabatami</strong> oferuje następujące funkcje:
<ul>
<li>Zarządzanie cenami i rabatami dla danego kanału i kategorii.</li>
<li>Zarządzanie regułami grupy cen.</li>
<li>Priorytety cen i rabatów pozwalające na przypisywanie priorytetów do grup cen i rabatów, dzięki czemu można kontrolować kolejność, w jakiej są one stosowane.</li>
<li>Zarządzanie rabatami za przynależność i od cen katalogowych.</li>
</ul>
Obszar roboczy <strong>Zarządzanie katalogami</strong> oferuje następujące funkcje:
<ul>
<li>Podsumowanie aktywnych katalogów.</li>
<li>Śledzenie cyklu życia katalogów w jednej lokalizacji.</li>
</ul></td>
<td><ul>
<li>Obszary robocze zwiększają efektywność i produktywność pracowników, umożliwiając im centralne zarządzanie zadaniami i akcjami, które są powiązane z rolą merchandizingu.</li>
<li>Funkcja priorytetów cen i rabatów daje odbiorcom większą kontrolę nad stosowanymi cenami i rabatami. Ta funkcja umożliwia także nowe scenariusze, w których wyższe ceny w sklepach uzyskują wyższy priorytet niż ceny standardowe.</li>
</ul></td>
</tr>
<tr>
<td>Zarządzanie wdrożeniami i operacjami kanału sprzedaży.</td>
<td>Użytkownik musi mieć dostęp do wielu formularzy, aby wykonać następujące zadania:
<ul>
<li>Tworzenie i konfigurowanie nowych kanałów i powiązanych z nimi jednostek.</li>
<li>Zarządzanie codziennymi czynnościami w sklepie.</li>
<li>Przetwarzanie transakcji sieci sprzedaży w systemie Microsoft Dynamics AX, generowanie zestawień sieci sprzedaży i aktualizowanie magazynu i finansów w systemie Microsoft Dynamics AX.</li>
</ul>
</td>
<td>Obszar roboczy <strong>Wdrażanie kanału sprzedaży</strong> pozwala wykonywać następujące zadania:
<ul>
<li>Tworzenie nowych kanałów i powiązanych z nimi jednostek.</li>
<li>Śledzenie postępuj konfiguracji sklepu sieci sprzedaży.</li>
<li>Podejmowanie wymaganych kroków w celu ukończenia zadania lub dostarczanie informacji umożliwiających wykonanie zadania.</li>
<li>Śledzenie stanu urządzeń i bezpośrednie sprawdzanie poprawności i pobieranie instalacji programu Retail Modern POS (MPOS) w sklepie.</li>
<li>Dostęp do wszystkich powiązanych stron.</li>
</ul>Obszar roboczy 
<strong>Zarządzanie sklepem sieciowym</strong> pozwala wykonywać następujące zadania:
<ul>
<li>Zarządzanie pracownikami i ich uprawnieniami w punkcie sprzedaży.</li>
<li>Śledzenie stanu zmiany w wybranym sklepie lub grupie sklepów.</li>
<li>Bezpośrednie sprawdzanie poprawności i pobieranie instalacji programu MPOS w sklepach.</li>
<li>Drukowanie raportów i uzyskiwanie dostępu do powiązanych stron.</li>
</ul>Obszar roboczy 
<strong>Finanse sklepu sieciowego</strong> pozwala wykonywać następujące zadania:
<ul>
<li>Tworzenie, obliczanie i księgowanie zestawień dla danego kanału.</li>
<li>Planowanie zadań wsadowych do aktualizacji zapasów i obliczanie i księgowanie zestawień.</li>
<li>Śledzenie otwartych zestawień.</li>
<li>Śledzenie stanu zmiany w wybranym sklepie lub grupie sklepów.</li>
<li>Drukowanie raportów i szybki dostęp do wszystkich powiązanych stron.</li>
</ul></td>
<td>Obszary robocze zwiększają efektywność i produktywność pracowników, umożliwiając im centralne zarządzanie większością zadań i akcji, które są powiązane z rolą zarządzaniem kanałem, zarządzaniem sklepem oraz finansami.</td>
</tr>
<tr>
<td>Zarządzanie operacjami IT w sieci sprzedaży.</td>
<td>Użytkownik musi mieć dostęp wielu formularzy.</td>
<td>Obszar roboczy <strong>Dane IT sieci sprzedaży</strong> umożliwia wysyłanie zapytań za pośrednictwem systemu Commerce Data Exchange w jednym miejscu dla danego kanału, dzięki czemu można wykonywać następujące zadania:
<ul>
<li>Sesje pobierania.</li>
<li>Sesje przekazywania.</li>
<li>Śledzenie nieudanych sesji i ich ponowne inicjowanie lub uruchamianie.</li>
<li>Wyświetlanie i uruchamianie nadchodzących zadań.</li>
</ul></td>
<td>Obszary robocze poprawiają efektywność i wydajność pracowników, umożliwiając im centralne zarządzanie zadaniami i czynnościami powiązanymi z operacjami IT sieci sprzedaży.</td>
</tr>
<tr>
<td>Import/eksport danych za pomocą jednostek danych.</td>
<td>System AX 2012 obsługuje bezpośrednią migrację z usługi Microsoft Dynamics Retail Management System (RMS) za pośrednictwem struktury importu/eksportu danych.</td>
<td>Danych sieci sprzedaży zostały rozwinięte w celu obsługi wszystkich danych głównych i referencyjnych, które są związane z siecią sprzedaży. Ponadto jednostki danych mają rozszerzoną obsługę w całym systemie Dynamics AX.</td>
<td>Jednostki danych umożliwią odbiorcom importować/eksportować dane w oparciu o metadane. Jednostki OData pozwalają też odbiorcom integrować system Dynamics AX z programami zewnętrznymi.</td>
</tr>
<tr>
<td>Wykonywanie inteligentnych analiz za pomocą raportów BI z poziomu Dynamics Microsoft AX i aplikacji klienckiej w punkcie sprzedaży.</td>
<td>Dostępnych jest ponad 25 raportów zaplecza i 5 raportów po stronie kanału.</td>
<td>Dostępnych jest ponad 30 raportów zaplecza i 10 raportów po stronie kanału.</td>
<td>Te raporty pozwalają odbiorcom szerzej korzystać z BI w celu prognozowania trendów, odkrywania informacji i pozostawania na najwyższym poziomie wydajności.</td>
</tr>
<tr>
<td>Analizowanie danych sprzedażowych z kanału sprzedaży przy użyciu pakietu zawartości „Monitorowanie wyników kanału sieci sprzedaży” dla narzędzia Power BI.</td>
<td>Niedostępna</td>
<td>Na stronie PowerBI.com wybierz opcję <strong>Pobierz dane</strong>, a następnie wybierz pakiet zawartości <strong>Dynamics AX — Retail Channel Performance</strong>. Wpisz URL dla punktu końcowego Dynamics AX, aby wyświetlić dane na pulpicie nawigacyjnym.</td>
<td>W trzech lub czterech kliknięcia można wdrożyć pulpit nawigacyjny Power BI, który zawiera ważne dane finansowe. Zawartość można spersonalizować. Oprócz tego użytkownicy mogą osadzać kafelki pulpitu nawigacyjnego narzędzia Power BI w spersonalizowanych obszarach roboczych w systemie Dynamics AX, aby później móc wyświetlać skrócone wyniki analiz.</td>
</tr>
<tr>
<td>Konfigurowanie uprawnienia odbiorcy.</td>
<td>Niedostępna</td>
<td>Odbiorcy mogą wybrać, czy operacje w punkcie sprzedaży mogą być dostępne dla konsumentów. Usługa Retail Server używa uprawnień do wywołania interfejsu programowania aplikacji (API).</td>
<td>To daje możliwość konfigurowania uprawnień na poziomie odbiorcy.</td>
</tr>
<tr>
<td>Sprawdzani poprawność konfiguracji jednostki i zarządzanie nią.</td>
<td>Niedostępny</td>
<td>Funkcji zarządzania i kontroli konfiguracji oferuje następujące funkcje:
<ul>
<li>Zbiorcze przesyłanie danych konfiguracji</li>
<li>Sprawdzanie poprawności jednostki biznesowej</li>
</ul></td>
<td>Zapewnia możliwość inicjowania konfiguracji i sprawdzania poprawności stanu oraz kompletności konfiguracji dla różnych elementów konfiguracji.</td>
</tr>
</tbody>
</table>

### <a name="retail-hardware-station"></a>Stacja sprzętowa w punkcie sprzedaży detalicznej

| Co można zrobić? | Dynamics AX 2012 | Dynamics AX 7.0 | Dlaczego to jest ważne? |
|------------------|------------------|-----------------|------------------------|
| Włączanie urządzeń punktu sprzedaży w celu łączenia z urządzeniami zewnętrznymi, takimi jak drukarki, szuflady kasowe czy urządzenia płatności. | Profil sprzętowy programu MPOS służy do określania urządzeń, które są używane. | Dodany profil sprzętowy obsługuje bardziej zróżnicowane urządzenia między stacjami. Nowy profil stacji sprzętowej obsługuje unikatowy identyfikator terminalu dla każdej stacji sprzętowej podczas przetwarzania elektronicznego transferu środków (EFT). Obsługa EFT została połączona ze stacją sprzętową w celu ograniczenia udziału MPOS w przetwarzaniu płatności za pomocą EFT. | Zapewnia ona większą elastyczność implementacji. Ponadto oferuje większe bezpieczeństwo i redukuje kontakt z danymi kart kredytowych. |

### <a name="retail-server-and-data-management"></a>Usługa Retail Server i zarządzanie danymi

Usługa Retail Server i zarządzanie danymi pozwala odbiorcom i firmom tworzy jednolite środowisko zakupowe w rozproszonym kanale dla środowisk online, sklepu i biura obsługi.

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Łączenie z bazą danych Commerce Runtime (CRT), w której są przechowywane dane biznesowe dla kanału, za pomocą usług CRT.</td>
<td>Funkcja OData V3 jest obsługiwana.</td>
<td>Funkcja OData V4 jest obsługiwana.</td>
<td>Pomaga odbiorcom w zachowaniu zgodności z najnowszymi normami OData. Tworzy też stabilne środowisko w rozproszonym kanale dzięki integracji sprzedaży w kanałach sklepu, mobilnych i online.</td>
</tr>
<tr>
<td>Obsługa usług Retail jako zestawu usług możliwego do hostowania.</td>
<td>Interfejs API handlu elektronicznego nie jest obsługiwany w usłudze Retail Server.</td>
<td>Interfejs API handlu elektronicznego jest teraz dostępny za pośrednictwem usługi Retail Server, umożliwiając obsługę scenariuszy online.</td>
<td>Oferuje hostowane i skalowalne usługi handlu elektronicznego, które mogą być używane w sklepach internetowych innych firm.</td>
</tr>
<tr>
<td>Przenoszenie danych miedzy zapleczem systemu Microsoft Dynamics AX i kanałami za pomocą usługi Commerce Data Exchange.</td>
<td>Commerce Data Exchange to system, który przesyła dane między systemem Microsoft Dynamics AX a kanałami sieci sprzedaży, np. między sklepami internetowymi i tradycyjnymi. Aby uzyskać więcej informacji, zobacz <a href="/dynamicsax-2012/appuser-itpro/commerce-data-exchange">Commerce Data Exchange [AX 2012]</a>.</td>
<td>Funkcje pokrywają się z systemem Microsoft Dynamics AX 2012 CU8. Warto jednak pamiętać o następujących szczegółach:
<ul>
<li>Usługa Commerce Data Exchange została ponownie zaprogramowana pod kątem chmury.</li>
<li>Usługa przetwarzania asynchronicznego używa bezpośredniego dostępu do bazy danych kanału.</li>
<li>Usługa Commerce Data Exchange: Real-time jest hostowana jako niestandardowa usługa systemu Microsoft Dynamics AX.</li>
<li>Program MPOS zarządza synchronizacją między bazami danych trybu offline i usługą Retail Server.</li>
</ul></td>
<td>Usługa Commerce Data Exchange została ponownie zaprogramowana pod kątem platformy chmurowej. Nadal zarządza ona przenoszeniem danych między systemem Microsoft Dynamics AX i kanałami w sieci sprzedaży, np. między sklepami internetowymi i tradycyjnymi.</td>
</tr>
<tr>
<td>Obsługa PnP, częściowo zintegrowane przetwarzanie płatności między kanałami za pomocą zestawu SDK płatności.</td>
<td>AX 2012 oferuje następujące funkcje:
<ul>
<li>Obsługa wszystkich kanałów: punkt sprzedaży, handel elektroniczny i biuro obsługi.</li>
<li>Obsługa dostępnej karty i niedostępnej karty.</li>
<li>Strona akceptowania płatności.</li>
<li>Kod źródłowy obsługi urządzeń peryferyjnych LS5300 i MX925 jako przykład w zestawie Retail SDK.</li>
</ul></td>
<td>Aktualna wersja systemu Dynamics AX obsługuje wszystkie istniejące funkcje kart kredytowych/debetowych w systemie Microsoft Dynamics AX dla usługi Retail 2012 oraz cztery nowe rozszerzenia.</td>
<td>Umożliwia odbiorcy przetwarzanie transakcji kartą kredytową/debetową dla płatności.</td>
</tr>
<tr>
<td>Aktywacja urządzeń za pomocą konta Microsoft (Microsoft Azure Active Directory (Azure AD)).</td>
<td>Niedostępna</td>
<td>Oferowane są następujące funkcje:
<ul>
<li>Rozszerzone zabezpieczenia poprzez aktywację w chmurze opartą na usłudze Azure AD.</li>
<li>Zwiększone zabezpieczenia dla zarządzania tokenami.</li>
<li>Większa niezawodność, rozwiązywanie problemów i wyświetlanie komunikatów o błędach podczas aktywacji</li>
<li>Uproszczone zadania zarządzania środowiskiem informatycznym powiązane z aktywacją.</li>
<li>Ulepszony model przeciwdziałania zagrożeniom i poprawione błędy w zabezpieczeniach.</li>
</ul></td>
<td>Oferuje następujące korzyści:
<ul>
<li>Poziom bezpieczeństwa jest wyższy dzięki usłudze Azure AD i tokenom/identyfikatorom urządzeń (wywołania usługi RS używające tokenu, magazyn aplikacji właściwy dla użytkownika).</li>
<li>Blokuje nieautoryzowane zdalne użycie programu MPOS (brick device).</li>
<li>Śledzi urządzenia MPOS dla celów zgodności ze standardem PCI.</li>
<li>Mapuje urządzenia fizyczne z jednostką biznesową (rejestr) przy użyciu tokenu urządzenia.</li>
<li>Inicjuje ustawienia w celu usprawnienia funkcjonowania programu MPOS (sekwencje identyfikatorów i profile sprzętowe) jako pierwszy punkt stykowy programu MPOS.</li>
<li>Przekazuje informacje o urządzeniu z centrali.</li>
</ul></td>
</tr>
<tr>
<td>Zarządzanie zawartością multimediów dla tworzenia i udostępniania za pomocą Galerii multimediów.</td>
<td>Niedostępny</td>
<td><ul>
<li>Obsługa przesyłania, wyświetlania i usuwania obrazów oraz zarządzania nimi w Galerii multimediów zarówno dla obrazów hostowanych zewnętrznie, jak i tych zapisanych lokalnie w systemie handlu detalicznego.</li>
<li>Obsługa przekazywania i wyświetlania obrazów ze stron jednostek (<strong>Produkty</strong>, <strong>Katalogi</strong> itd.) poprzez tworzenie połączeń do obrazów z galerii i przekazywanie obrazów z pulpitu.</li>
<li>Optymalizowanie obrazów pod kątem miniatur, niestandardowy rozmiar i oryginału.</li>
<li>Zbiorcze łączenie jednostek za pomocą szablonów i zadań w zbiorczych zadaniach kojarzenia.</li>
<li>Integracja z programem Microsoft Excel zastępuje ograniczenia konwencji nazewnictwa i wstępnie zdefiniowanych ścieżek istniejące w grupach atrybutów.</li>
<li>Obsługa obrazów offline i zabezpieczanie obrazów w kontekście treści umożliwiających identyfikację danych osobowych (PII), np., zdjęcia pracowników i odbiorców przechowywane w usłudze Retail.</li>
</ul></td>
<td><ul>
<li>Rozwiązuje uciążliwe przełączanie między lokalizacjami w przypadku obrazów hostowanych zewnętrznie, umożliwiając zarządzanie nimi w jednym miejscu.</li>
<li>Oferuje zaawansowane opcje zarządzania treściami w Galerii multimediów dla obrazów przekazanych i hostowanych zewnętrznie, a także opcje filtrowania ułatwiające wyszukiwanie obrazów.</li>
<li>Umożliwia łatwe tworzenie zbiorczych skojarzeń między zewnętrznie hostowanymi obrazami a jednostkami takimi jak produkty i katalogi.</li>
<li>Obsługuje pamięć obrazów hostowanych zewnętrznie i integrację z programem Excel dla łatwej aktualizacji.</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="rich-clientele-experience"></a>Wzbogacone środowisko klienta

Retail oferuje imersyjne środowisko mobilne w każdym miejscu, o każdej porze i na dowolnym urządzeniu. Ta funkcja umożliwia rozszerzone środowisko zakupowe i sklepowe we wszystkich kanałach.

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Wyszukiwanie, przeglądanie lub skanowanie produktów, dodawanie produktów do koszyka, akceptowanie płatności i realizacja transakcji przy użyciu intuicyjnego, dotykowego, wzbogaconego i imersyjnego środowiska użytkownika w programie MPOS.</td>
<td>AX 2012 oferuje następujące funkcje:
<ul>
<li>Obsługa sprzedaży, zwrotów i unieważnień.</li>
<li>Tworzenie, modyfikowanie i odbiór zamówień odbiorcy.</li>
<li>Wykonywanie operacji związanych ze zmianą i szufladą kasową.</li>
<li>Pobieranie i przyjmowanie zamówień i zliczanie zapasów magazynowych.</li>
<li>Wyświetlanie raportów sklepu.</li>
</ul></td>
<td>Funkcje są równoważne z systemu AX 2012 MPOS. Obejmuje to następujące funkcje:
<ul>
<li>Wyszukiwanie odbiorców w wielu sklepach/kanałach.</li>
<li>Możliwość tworzenia zamówień odbiorców bez otwierania usługi Real-time Service.</li>
<li>Ulepszone przepływy pracy oraz komunikaty o stanie i błędach dotyczące aktywacji urządzeń.</li>
<li>Lepsza rozszerzalność, np. wyzwalacze „przed” i „po” oraz obsługa działań zwiększające możliwości dostosowywania.</li>
</ul></td>
<td>Pracownicy działu sprzedaży mogą przetwarzać transakcje sprzedaży i zamówienia odbiorców oraz wykonywać codzienne operacje i zarządzanie zapasami za pomocą urządzeń przenośnych w dowolnym miejscu w sklepie.</td>
</tr>
<tr>
<td>Uruchamianie punkt sprzedaży jako aplikacji sieci web za pomocą programu Cloud POS.</td>
<td>Niedostępny</td>
<td>Funkcje są równoważne z systemu MPOS. Obejmuje to następujące funkcje:
<ul>
<li>Aktywacja urządzeń za pomocą AAD</li>
<li>Projektowanie elastycznego układu</li>
<li>Obsługa przeglądarek Edge, Internet Explorer i Chrome.</li>
</ul></td>
<td>Oferuje aplikację sieci web punktu sprzedaży z funkcjami zgodnymi z programem MPOS i która może być używana na wielu platformach i w różnych przeglądarkach bez kosztów wdrażania.</td>
</tr>
<tr>
<td>Integracja z systemami zarządzania zawartością w celu tworzenia witryny wielokanałowego handlu elektronicznego.</td>
<td>Obsługa Microsoft SharePoint i zewnętrznych witryn sklepowych.</td>
<td>Dostępna jest platforma handlu elektronicznego obsługująca witryny sklepów internetowych innych producentów. Platforma obejmuje następujące funkcje:
<ul>
<li>Rozbudowany interfejs API odbiorców.</li>
<li>Integracja uwierzytelniania z zewnętrznymi dostawcami identyfikatorów o otwartym kodzie źródłowym.</li>
<li>Integracja płatności.</li>
</ul></td>
<td>Odbiorcy mają teraz możliwość elastycznego korzystania z wybranego przez siebie systemu zarządzania treścią.</td>
</tr>
<tr>
<td>Docieranie do odbiorców za pośrednictwem katalogów zamówień pocztowych i uproszczenie operacji poprzez szybkie wprowadzanie zamówień, sprzedaż wspomaganą i realizacja zamówień przy użyciu biura obsługi.</td>
<td><ul>
<li>Kanał biura obsługi</li>
<li>Katalogi zamówień pocztowych</li>
<li>Szybkie wprowadzanie zamówień i sprzedaż wspomagana</li>
<li>Ulepszona realizacja zamówień</li>
<li>Obsługa klienta</li>
<li>Zintegrowane wyceny i promocje/rabaty</li>
</ul></td>
<td>Dostępne jest ujednolicenie funkcji i z Biurem obsługi AX 2012 z wyjątkiem zastępowania cen.</td>
<td>Biura obsługi są rodzajem kanału sprzedaży, który umożliwia pracownikom zbierania zamówień od odbiorców przez telefon i tworzenie zamówień sprzedaży.</td>
</tr>
</tbody>
</table>

### <a name="commerce-essentials"></a>Podstawowe funkcje handlowe

Opcja konfiguracji pod kątem modułu Handel detaliczny i inny pomaga uprościć wdrażanie rozwiązań właściwych dla sieci sprzedaży.

| Co można zrobić? | Dynamics AX 2012 | Dynamics AX 7.0 | Dlaczego to jest ważne? |
|------------------|------------------|-----------------|------------------------|
| Można używać pulpitu nawigacyjnego Podstawowe funkcje handlowe. | Dostępna jest strona z łączami do elementów menu. | Pulpit nawigacyjny Podstawowe funkcje handlowe zawiera łącza do często wykonywanych zadań, łącza do obszarów roboczych, formant sieciowy usługi Power BI, ulubione, zapamiętywanie ostatnio otwieranych stron i bieżące elementy pracy. | Rozszerzony pulpit nawigacyjny daje pracownikom większe możliwości, poprawiając ich wydajność dzięki elastycznemu narzędziu do rozpoczęcia dowolnego zadnia związanego ze sprzedażą detaliczną. |
| Używanie jednostek danych w celu uzyskiwania dostępu do zmian dotyczących konta. | Zmiany dotyczące konta są eksportowane do folderu w systemie plików. | Zmiany dotyczące konta są dostępne za pośrednictwem jednostek danych. | Ta funkcja zapewnia większą elastyczność podczas przenoszenia danych między różnymi systemami. Tę funkcję można również rozszerzyć za pomocą aplikacji OData. |
| Używanie programów Cloud POS i MPOS. | Gotowy do użytku od razu po zainstalowaniu jest tylko program Enterprise POS (EPOS). | Programy MPOS i Cloud POS zastępują klienta EPOS. Kanał handlu elektronicznego jest również domyślnie dołączony do pakietu Podstawowe funkcje handlowe. | Ta funkcja umożliwia większą kontrolę od razu po zainstalowaniu w przypadku aplikacji klienckich punktu sprzedaży z opcją szybkiego wdrażania. |
| Implementacja i obsługa architektury dwuwarstwowej. | Struktura importu/eksportu danych umożliwia przenoszenie danych między systemem AX 2012 a systemami zewnętrznymi. | Jednostki danych utworzone w celu rozszerzenia obsługi architektury dwupoziomowej. | Jednostki danych i aplikacje OData oferują warstwę abstrakcji ułatwiającą implementację i obsługę scenariuszy dwupoziomowych. |
| Uproszczenie formularzy. | Aby uprościć interfejs użytkownika, niezbędny jest niestandardowy kod. | Rozszerzenia menu i formularza zawierają uproszczenia standardowego interfejsu użytkownika. | Ta funkcja umożliwia szybsze i prostsze dostosowywanie formularzy zgodnie z wymaganiami sprzedawców detalicznych. |

### <a name="pos-task-recorder"></a>Rejestrator zadań punktu sprzedaży

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Tworzenie i udostępnianie przewodników po zadaniach i dokumentów dla nowoczesnego punktu sprzedaży.</td>
<td>Niedostępny</td>
<td>Rejestrator zadań MPOS obsługuje następujące funkcje:
<ul>
<li>Tworzenie nagrań zadań dla wielu zadań wykonywanych w MPOS.</li>
<li>Generowanie dokumentu zawierającego kroki i zrzuty ekranu oraz kojarzenie go z węzłem w modelu procesu biznesowego.</li>
</ul></td>
<td>Partnerzy i niezależni dostawcy oprogramowania (ISV) mogą dostosować MPOS i udostępnić dokumenty pomocnicze do szkolenia użytkowników.</td>
</tr>
</tbody>
</table>

### <a name="extensibility"></a>Możliwości rozszerzania

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Obsługa rozszerzalnych i łatwych we wdrażaniu składników systemu handlu detalicznego w centrali, biurze obsługi, module handlu elektronicznego i punkcie sprzedaży.</td>
<td>Składniki można rozszerzyć za pomocą zestawu SDK usługi Retail. Funkcje pakowania i rozmieszczania nie są obsługiwane.</td>
<td>Możliwości rozszerzania są importowane w różnych komponentach, aby poprawić obsługę izolacji i przydatności kodu do użytku. Oto kilka dostępnych funkcji:
<ul>
<li>Przepływ pracy, działania i operacje.</li>
<li>Wyzwalacze „przed” i „po”, które pozwalają łatwo rozszerzyć przepływ pracy.</li>
<li>Wyzwalacze aplikacji i operacji.</li>
</ul>
Dostępna jest również struktura, która umożliwia tworzenie i pakowanie tych składników za pomocą programu MSBuild, a następnie bezproblemowe wdrażanie dostosowań za pośrednictwem usługi Microsoft Dynamics Lifecycle Services (LCS).</td>
<td>Detaliści mają bardzo specyficzne wymagania wynikające z rynków lub obszarów geograficznych, na których działają. Dzięki łatwo rozszerzalnej platformie, możliwe jest prowadzenie działań na różnych rynkach i różnych branżach. Ponieważ usługa Retail ma również bardzo rozproszoną architekturę, możliwość płynnego wdrażania także bardo zwiększa wydajność pracy.</td>
</tr>
</tbody>
</table>

### <a name="lifecycle-management"></a>Zarządzanie cyklem życia

Lifecycle Services (LCS) to zestaw usług, których odbiorcy i partnerzy mogą używać do zarządzania cyklem życia systemu, od logowania po codzienne operacje.

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Zarządzanie programem za pośrednictwem chmurowych usług wdrażania.</td>
<td>Niedostępny</td>
<td>W chmurze można zastosować następujące topologie:
<ul>
<li>Testowa jednostanowiskowa topologia handlu detalicznego.</li>
<li>Wielostanowiskowa topologia handlu detalicznego o wysokiej dostępności.</li>
<li>Topologia dla programistów w postaci zestawu Retail SDK.</li>
</ul>
Dostępna jest opcja ulepszonej instalacji składnika odbiorcy z niskim nakładem pracy dzięki instalacji samodzielnej:
<ul>
<li>Retail Modern POS.</li>
<li>Retail Hardware Station.</li>
<li>Obsługa przekazywania i rozpowszechniania dostosowanych pakietów za pomocą instalacji samodzielnej.</li>
</ul></td>
<td>Usługi wdrażania chmury oferują następujące zalety:
<ul>
<li>Znaczne obniżenie nakładów pracy i złożoności wdrażania składników usługi Centrala handlu detalicznego.</li>
<li>Natywne wdrożenie w chmurze publicznej Microsoft Azure.</li>
<li>Udoskonalona instalacja samodzielna składników sklepu w celu ułatwienia i zwiększenia intuicyjności konfiguracji</li>
</ul></td>
</tr>
<tr>
<td>Monitorowanie stanu systemu i diagnozowanie błędów i problemów.</td>
<td>Ta funkcja wymaga <a href="https://www.microsoft.com/en-us/download/details.aspx?id=58205">pakietu System Center 2012 Management dla programu Microsoft Dynamics AX 2012 R3 CU8 Retail</a>.</td>
<td>Monitorowanie i diagnostyka dla składników usługi Retail są teraz dostępne za pośrednictwem pulpitu nawigacyjnego <strong>Wgląd operacyjny</strong> w LCS.</td>
<td>Pulpit nawigacyjny <strong>Wgląd operacyjny</strong> to chmurowy portal monitorowania, który eliminuje konieczność instalacji infrastruktury System Center Operations Manager (SCOM).</td>
</tr>
<tr>
<td>Samodzielne tworzenie, konfigurowanie, pobranie i instalowanie stacji sprzętowej usługi Retail oraz urządzeń.</td>
<td>Za pomocą narzędzia do pakowania instalacji i portalu Enterprise Portal użytkownik może wykonywać automatyczną instalację i konfigurację wszystkich składników, które są wymagane na danym komputerze, na podstawie zdefiniowanej topologii.</td>
<td>Ponieważ istnieją tylko dwa pakiety instalacyjne, jeden dla klienta MPOS i drugi dla stacji sprzętowej usługi Retail, możliwości samodzielnej instalacji zmniejszyła nakłady pracy konieczne na poszczególnych poziomach instalacji tych składników klienckich.</td>
<td>Samoobsługa ma na celu minimalizację wymagań i ułatwia użytkownikowi wykonywanie instalacji.</td>
</tr>
</tbody>
</table>

## <a name="sales"></a>Sprzedaż

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Szybkie wyświetlanie przeglądu alternatywnych opcji dostawy w przypadku obiecanych zamówień dla odbiorcy.</td>
<td>Gdy występują ograniczenia dostępności produktów i termin dostawy dla odbiorcy dla jednego lub kilku produktów na zamówieniu nie może zostać dotrzymany, obietnica realizacji zamówienia staje się wyzwaniem. Aby znaleźć alternatywne rozwiązania umożliwiając przesunięcie dostępności i czasu dostawy, tak aby termin żądany przez odbiorcę mógł zostać dotrzymany, lub aby zaoferować odbiorcy opcję dostawy, która będzie dla niego do zaakceptowania i której ufa, osoba przetwarzająca zamówienie może być zmuszona do otwarcia kilku formularzy, z których każdy oferuje tylko część potrzebnych informacji. W szczególności chodzi o to, że jeden formularz pokazuje dostępne ilości w różnych oddziałach, inny pokazuje dostępne ilości w ustawieniu międzyfirmowym, trzeci pozwala użytkownikowi obliczyć najwcześniejszą możliwą datę tylko dla jednego oddziału lub jednego wariantu, a czwarty formularz pokazuje zamówienia podażowe. W rezultacie użytkownik zastanawia się, czy wziął pod wagę wszystkie odpowiednie opcje, zamiast po prostu wybrać rozwiązanie natychmiastowe, ale nie koniecznie optymalne. Użytkownicy mają również poczucie braku efektywności z powodu wielu przerw w przepływie realizacji obiecanych zamówień, ponieważ muszą otwierać i zamykać wiele stron i łączyć ze sobą informacje i opcje.</td>
<td>Na podstawie istniejących algorytmów obliczania daty dostawy, strona <strong>Dostawy alternatywne</strong> oferuje większy komfort obsługi obiecanych zamówień:
<ul>
<li>Gromadzi odpowiednie informacje z wielu formularzy w jednym miejscu.</li>
<li>Oferuje „gotowe” alternatywne pakiety dostawy, np. kombinowany tryb oddział/magazynowanie/wariant/transport oparty na kryterium najszybszej dostawy (najwcześniejsza dostępna data).</li>
<li>Pozwala użytkownikowi wybierać opcje z interfejsu symulacji i przenosić je do wiersza zamówienia sprzedaży.</li>
</ul></td>
<td>Firmy dążące do zapewnienia najwyższego poziomu obsługi klienta przy jednoczesnej realizacji strategii optymalizacji zapasów muszą być w stanie obiecywać zamówienia w sposób godny zaufania i konkurencyjny. W końcu ich klienci również wymagają, by produkty były dostępne w wyznaczonym czasie. Strona zadania <strong>Alternatywne dostawy</strong> przyspiesza, ułatwia i poprawia systematyczność realizacji zadań związanych z obiecywaniem zamówień dzięki wskazywaniu najlepszych alternatywnych dat dostawy w jednym interaktywnym miejscu.</td>
</tr>
</tbody>
</table>

## <a name="service-management"></a>Zarządzanie usługami

Nie dodano żadnych nowych funkcji.

## <a name="transportation-management"></a>Zarządzanie transportem

Nie dodano żadnych nowych funkcji.

## <a name="travel-and-expense"></a>Wyjazdy i wydatki

Nie dodano żadnych nowych funkcji.

## <a name="warehouse-management"></a>Zarządzanie magazynem

| Co można zrobić? | Dynamics AX 2012 | Dynamics AX 7.0 | Dlaczego to jest ważne? |
|------------------|------------------|-----------------|------------------------|
| Pobieranie, instalowanie i konfigurowanie Portalu urządzeń przenośnych używanych w magazynie. | W procesie instalacji systemu Microsoft Dynamics AX można pobrać, zainstalować i skonfigurować portal za pomocą ustawień standardowych. Wdrażanie i konfiguracja odbywa się samodzielnie i lokalnie. | Można pobrać autonomiczny instalator za pomocą menu w module Zarządzanie magazynem. Wdrażanie i konfiguracja odbywa się samodzielnie i lokalnie. | Aby skonfigurować obsługę za pomocą urządzeń przenośnych, trzeba zainstalować i skonfigurować Portal urządzeń przenośnych używanych w magazynie lokalnie i utworzyć połączenie z systemem Dynamics AX w chmurze. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Nowości i zmiany w aplikacjach finansowych i operacyjnych — strona główna](whats-new-changed.md)

[Nowe przewodniki po zadaniach (luty 2016 r.)](new-task-guides-available-february-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

