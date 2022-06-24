---
title: Przetwarzanie wynagrodzenia
description: Funkcjonalność przetwarzania wynagrodzeń pozwala obliczyć nowe kwoty podstawy wynagrodzenia dla pracowników w oparciu o korektę wyrównawczą, cele podwyżki uznaniowej i wydajność.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 228c891e8c29cf4309856b90139d0b88805a9812
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886168"
---
# <a name="process-compensation"></a>Przetwarzanie wynagrodzenia


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Funkcjonalność przetwarzania wynagrodzeń pozwala obliczyć nowe kwoty podstawy wynagrodzenia dla pracowników w oparciu o korektę wyrównawczą, cele podwyżki uznaniowej i wydajność. Ten artykuł omawia podstawowy przepływ przetwarzania wynagrodzeń w systemach stałych wynagrodzeń bez uwzględniania wydajności pracownika.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Planowanie nowych kwot wynagrodzeń i budżetów
Aby dać pracownikom podwyżkę uznaniową, należy skonfigurować budżet stałych podwyżek dla każdego z działów: **Zarządzanie wynagrodzeniami** > **Linki** > **Cele podwyżki uznaniowej**. (Alternatywnie można otworzyć stronę z poziomu działu: **Organizacja** > **Działy**). W tym oknie można dodatkowo określić, czy pracownicy w określonym związku zawodowym lub lokalizacji powinni otrzymać inny procent podwyżki. Pola **Budżet** i **Waluta** służą celom informacyjnym i mogą służyć do zanotowania kwoty waluty dla budżetu.

## <a name="set-up-the-compensation-process"></a>Konfigurowanie przetwarzania wynagrodzenia
Na stronie **Procesy związane z wynagrodzeniem** można określić parametry przetwarzania wynagrodzenia. Obejmuje to okres do dnia, który ma zostać użyty do wyznaczenia kwot wynagrodzeń, oraz datę, od kiedy nowe kwoty wynagrodzeń powinny obowiązywać.

Opcjonalnie można uwzględnić datę określenia **stałego wynagrodzenia proporcjonalnie do zatrudnienia**, jeśli w którymkolwiek systemie stałych wynagrodzeń jest używana reguła zatrudnienia Procent. W takich systemach każdy, kto został zatrudniony po dacie **rozpoczęcia cyklu**, a przed **datą określenia stałego wynagrodzenia** proporcjonalnie do zatrudnienia, otrzyma 100% obliczonej podwyżki uznaniowej lub podwyżki ogólnej. Każdy, kto został zatrudniony po **dacie określenia stałego wynagrodzenia proporcjonalnie do zatrudnienia**, a przed **datą zakończenia cyklu**, otrzyma część obliczonej podwyżki zgodnie z liczbą dni w cyklu, przez jaką był zatrudniony. Na przykład jeśli nasz cykl trwa od 1 stycznia do 31 grudnia i mamy datę zatrudnienia z wynagrodzeniem proporcjonalnym wg stałej stawki ustawioną na 1 kwietnia, to pracownik zatrudniony w marcu otrzyma pełną obliczoną podwyżkę, podczas gdy pracownik zatrudniony 1 lipca otrzyma około połowy obliczonej podwyżki.

Zdarzenie procesowe **-Data stałego punktu odniesienia** jest używane tylko do przetwarzania w niektórych systemach wynagrodzeń o zmiennej wysokości i nie będzie tutaj omawiane. **Termin przeglądu** to termin na złożenie wszystkich propozycji płacowych, tak aby nowe kwoty wynagrodzeń mogły zostać załadowane do rekordu pracownika. Data przeglądu ma wyłącznie charakter informacyjny.

Po zapisaniu parametrów zdarzenia procesowego można kliknąć przycisk **Ustawienia** i wskazać systemy wynagrodzeń, które mają zostać uwzględnione w tej sesji przetwarzania, oraz czynności związane ze stałym wynagrodzeniem, które mają zostać wykonane dla każdego systemu.

Kliknij przycisk **Dodaj** na karcie **Plany**, aby dodać system wynagrodzeń do zdarzenia procesowego. Kolumny **Użyj innej dźwigni finansowej**, **Współczynnik dźwigni finansowej** i **Opis dźwigni finansowej** są używane tylko dla systemów wynagrodzeń o zmiennej wysokości i nie będą omówione w tym artykule.

Zapisz rekord i kliknij przycisk **Dodaj** na karcie **Akcje**, aby dodać akcje związane ze stałym wynagrodzeniem dla wybranego systemu wynagrodzeń. Użyj opcji **Włącz rekomendacje**, aby wprowadzić kwotę inną niż obliczona podwyżka podstawowa dla czynności. Aby obliczyć akcję opartą na wyniku poprzedniej akcji w celu połączenia wielu akcji wynagrodzenia, zaznacz opcję **Użyj poprzedniego wyniku**. Akcje związane ze stałym wynagrodzeniem to typy logiki wynagrodzeń, którym można nadać opisowe nazwy. W systemach typu **Kategoria** lub **Pasmo** można dodawać tylko akcje związane ze stałym wynagrodzeniem, które mają jeden z następujących typów:

| Typ akcji związanej ze stałym wynagrodzeniem | Funkcja                  |
|-------------------------------|-------------------------------------------------------------------------|
| Kapitał własny                        | W czynnościach wyrównywania stawka płacy pracownika na ostatni dzień cyklu jest porównywana z najniższym punktem odniesienia dla poziomu wskazanego na stanowiska pracownika. Jeśli stawka płacy pracownika jest niższa od minimalnego punktu odniesienia, zostanie obliczona podwyżka konieczna do osiągnięcia minimalnego punktu przez pracownika.                                                                                |
| Wartość                         | W czynnościach uznaniowych podwyżka jest obliczana na podstawie stawki płacy pracownika na ostatni dzień cyklu oraz procentu podwyżki znalezionego w budżecie stałych podwyżek dla działu, związku zawodowego i lokalizacji pracownika.                                                                                                                                                                                         |
| Ogólne                       | W czynnościach ogólnych podwyżka jest obliczana na podstawie wartości procentowej lub pracownikom jest przyznawana kwota ryczałtowa. Jest to uzależnione od ustawień w obszarze **Stałe wynagrodzenie** na karcie **Ogólne**.                                                                                                                                                                                                                        |
| Awans                     | Akcje promocyjne zapewniają Ci nazwane miejsce, w którym możesz nagradzać podwyżki. Zaznacz opcję **Włącz propozycję**, aby wprowadzić propozycję dla pracowników, którzy będą otrzymywać promocje.  Pracownicy bez proponowanej podwyżki nie będą mieli akcji **Awans** dodanej do swoich rekordów stałego wynagrodzenia.                                                                       |
| Inna zmiana poziomu            | W powyższym przykładzie akcją **Stałe wynagrodzenie** o typie **Inna zmiana poziomu** jest akcja zatytułowana **Degradacja**. Generuje ona zerową (bez zmian) podwyżkę podstawową, w związku z czym można wpisać kwotę propozycji korygującą stawkę płacy pracownika. (Wybierz opcję **Włącz rekomendacje**). Pracownicy bez propozycji nie będą mieli tej akcji dodanej do swoich rekordów stałego wynagrodzenia. |

Do planu wynagrodzeń skokowych można dodać wyłącznie akcje **Stałe wynagrodzenie** o typie Krok.

| Typ akcji związanej ze stałym wynagrodzeniem | Funkcja                |
|--------------------------------|------------------------------|
| Krok                           | Na karcie **Ogólne** wskaż, czy ta akcja kroku powinna przenosić pracowników w przód o 0 kroków, 1 krok, czy 2 kroki.                                                                                  |
|                                | **0 kroki** — Pracownik otrzyma stawkę płacy dla bieżącego kroku, na którym się znajduje.                                                                                                                      |
|                                | **1 krok** — System sprawdzi, czy pracownik jest już w ostatnim punkcie odniesienia dla swojego poziomu.                                                                                             |
|                                | **2 kroki** —pracownik przesunie się o dwa stopnie do przodu na swoim obecnym poziomie. Jeśli pracownik osiągnął już ostatni punkt odniesienia na swoim poziomie, system może go przenieść o jeden krok lub nawet zero kroków. |

## <a name="run-the-compensation-process"></a>Wykonywanie procesu wynagrodzenia
Po skonfigurowaniu zdarzenia procesu wraz z niezbędnymi polami dat, planami i działaniami kliknij **Uruchom proces** na stronie **Zdarzenie procesu** — otworzy się okno dialogowe **Uruchom zdarzenia procesu wynagrodzeń**. Kliknij opcję **Pokaż wyniki przetwarzania**, aby zobaczyć, jak kwoty wynagrodzeń zostały obliczone dla każdego pracownika. Kliknięcie przycisku **OK** spowoduje uruchomienie przetwarzania wynagrodzeń dla wszystkich pracowników istniejących w wybranych systemach wynagrodzeń na dzień zakończenia cyklu.

## <a name="view-the-process-results"></a>Wyświetlanie wyników przetwarzania
Aby wyświetlić wyniki przetwarzania, otwórz stronę **Wyniki procesu**. Po każdym uruchomieniu zdarzenia procesowego jest tworzone nowe zdarzenie dotyczące wynagrodzeń. W ten sposób można wykonywać przebiegi próbne, wprowadzać korekty i uruchamiać zdarzenia związane z wynagrodzeniami wiele razy, aby zobaczyć, jak różne zmiany wpływają na wynagrodzenia pracowników.

Strona **Wyniki procesu** zawiera informacje na temat sesji przetwarzania, w tym czas wykonania przetwarzania, nazwa użytkownika, który uruchomił proces, oraz czy wystąpiły błędy podczas wykonywania procesu. Wybierz opcję **Zablokowane**, aby wyłączyć przycisk **Załaduj wynagrodzenie** i uniemożliwić wszystkim osobom ładowanie zdarzeń dotyczących wynagrodzenia do rekordów pracowników. Kliknięcie przycisku **Wyniki pracowników** spowoduje wyświetlenie listy pracowników uwzględnionych w sesji przetwarzania.

Opcja **Wyniki pracownika etatowego** powoduje wyświetlenie informacji na temat samego procesu, a także o wszelkich czynnościach związanych z wynagrodzeniami wykonanych w procesie. Sekcja **Stałe wynagrodzenie** będzie zawierać rekord dla każdej akcji uwzględnionej w zdarzeniu procesowym dla systemu wynagrodzeń. Kolumny **Bieżąca podstawa** i **Propozycja** zawierają więcej informacji dla akcji wybranej w sekcji **Stałe wynagrodzenie**. Jeśli dla czynności zaznaczoną opcję **Włącz rekomendacje**, pola **Rekomendacja** będzie można edytować. Pozwoli to na ręczne korygowanie kwot dla pracownika. Należy zauważyć, że jeśli dla akcji w zdarzeniu procesowym zaznaczono opcję **Użyj poprzedniego wyniku**, należy ręcznie zaktualizować kwoty dla wszystkich zależnych akcji.

Po dokonaniu przeglądu kwot wynagrodzeń dla pracownika i wprowadzeniu korekt w proponowanych wartościach można zmienić wartość atrybutu **Stan** w wierszu **Zdarzenie pracownika**, aby wskazać, czy zdarzenie zostało zatwierdzony, czy też powinno być ignorowane. Opcjonalnie można wymazać wszystkie zmiany propozycji płacowych dla pracownika, klikając przycisk **Oblicz ponownie**. Spowoduje to oznaczenie istniejącego zdarzenia pracownika stanem Ignoruj i utworzenie nowego zdarzenia pracownika z przeliczonymi wartościami.

## <a name="loading-approved-compensation-changes"></a>Ładowanie zatwierdzonych zmian wynagrodzeń
Gdy jedno lub więcej zdarzeń pracowników otrzyma aktualizację stanu do **Zatwierdzone**, mogą zostać załadowane do rekordów stałego wynagrodzenia pracowników. Można to zrobić poprzez zaznaczenie pojedynczo każdego zdarzenia pracownika i kliknięcie przycisku **Załaduj wynagrodzenie pracownika etatowego** na stronie **Wyniki pracownika etatowego** albo poprzez kliknięcie przycisku **Załaduj wynagrodzenie** na stronie **Wyniki procesu** i załadowanie na raz wszystkich zatwierdzonych zdarzeń pracowników.

Kliknięcie przycisku **OK** w oknie dialogowym **Załaduj wynagrodzenie** spowoduje dodanie wierszy niezerowych akcji dotyczących wynagrodzeń do strony **Stałe wynagrodzenie pracownika etatowego**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
