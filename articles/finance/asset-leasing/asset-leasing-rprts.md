---
title: Raporty dotyczące wynajmu składników majątku
description: W tym temacie wyszczególniono i pokrótce opisano raporty dostępne dla wynajmu składnika majątku.
author: moaamer
manager: Ann Beebe
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-27
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4bc4bac1a422a7505ef4c66b9c3b79a3d754cc4d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971485"
---
# <a name="asset-leasing-reports"></a>Raporty dotyczące wynajmu składników majątku

[!include [banner](../includes/banner.md)]

W tym temacie wyszczególniono i pokrótce opisano raporty dostępne dla wynajmu składnika majątku. Większość raportów jest wyświetlana przez wykonanie tych kroków lub kroków bardzo podobnych, stosownie do uwag). 

- Aby wyświetlić raporty dotyczące wynajmu składników majątku, należy wybrać **Wynajem składników majątku > Zapytania i raporty > Raporty dotyczące wynajmu** i wybrać raport do wyświetlenia. W przypadku raportów wymagających innej ścieżki wyboru kroki umożliwiające otwarcie tego raportu są dołączone do opisu tego raportu. 
- Po wybraniu raportu do drukowania zostanie otwarta strona parametrów umożliwiająca filtrowanie informacji zawartych w raporcie. Wprowadź kryteria filtrowania, a następnie kliknij przycisk **OK**, aby wygenerować raport. Wygenerowany raport będzie zawierał informacje, które spełniają kryteria określone w filtrach.

## <a name="asset-movement"></a>Przesunięcia środków
Raport przesunięcia środków trwałych służy jako raport przesunięcia do przodu sald składników majątku z prawem do użytkowania dla poszczególnych wynajmów. Ten raport umożliwia wyświetlenie transakcji środków trwałych dla wynajmu w podanym okresie. Raport zawiera następujące pola: 

|     Pola raportu                  |     opis                                                                |
|------------------------------------|--------------------------------------------------------------------------------|
|     Data rozpoczęcia              |     Data rozpoczęcia najwcześniejszej wersji wynajmu.                     |   
|     Okres wynajmu                     |     Okres wynajmu najwcześniejszej wersji wynajmu.                            |
|     Wynajem krótkoterminowy               |     Jeśli wynajem jest klasyfikowany jako krótkoterminowy, będzie wyświetlana wartość **Tak**.         |
|     Wynajem o niskiej wartości                |     Jeśli wynajem jest klasyfikowany jako wynajem o niskiej wartości, będzie wyświetlana wartość **Tak**.          |
|     Początkowy składnik majątku z prawem do użytkowania     |     Pierwotna wartość składnika majątku z prawem do użytkowania z wpisu w arkuszu początkowego uznania.      |
|     Saldo początkowe              |     Wartość księgowa netto składnika majątku z prawem do użytkowania na dzień **Data początkowa**.                         |
|     Okresowy wydatek amortyzacji    |     Kwota wydatku na amortyzację pobrana w zakresie dat zdefiniowanym dla raportu.        |
|     Umorzenie       |     Kwota umorzenia na dzień **Data początkowa**.                               |
|     Utrata wartości                     |     Kwota utraty wartości składnika majątku w zakresie dat zdefiniowanym dla raportu.               |
|     Modyfikacje                  |     Kwota korekt składnika majątku z prawem do użytkowania między parametrami daty.                            |
|     Wartość księgowa netto                 |     Końcowa wartość księgowa netto składnika majątku z prawem do użytkowania, po odjęciu umorzenia na dzień **Data początkowa**.    |

## <a name="differences-report"></a>Raport różnic
Raport różnic zawiera różnice między informacjami załadowanymi do struktury importu wynajmu a informacjami znajdującymi się aktualnie w systemie. Pozwala to na porównanie, co zostało skorygowane, zaktualizowane lub dodane za pomocą narzędzia importowania wynajmu.  

Wartości w raporcie różnią się w zależności od wybranego wynajmu. W raporcie zostaną wyświetlone tylko te pola, które różnią się od tego, co znajduje się aktualnie w systemie, oraz co znajduje się w tabelach przemieszczania. Stara wartość to co, znajduje się obecnie w systemie lub co znajdowało się poprzednio w systemie, w zależności od tego, czy został przeprowadzony proces importowania. Nowa wartość pokazuje wartość w tabeli przemieszczania, która zastąpi starą wartość.

## <a name="five-years-undiscounted-payment-forecast"></a>Pięcioletnia prognoza płatności bez rabatu
Raport Pięcioletnia prognoza płatności bez rabatu pokazuje prognozowane opłaty z tytułu wynajmu bez rabatu, które mają zostać opłacone w ciągu następnych pięciu lat od daty określonej w parametrach raportu. Raport zawiera następujące pola: 

|     Pola raportu         |     opis                                                                                       |
|-------------------------- |---------------------------------------------------------------------------------------------------    |
|     Opis wynajmu     |     Opis wynajmu z nagłówka wynajmu.                                                      |
|     Identyfikator wynajmu              |     Unikatowy identyfikator wynajmu.                                                                              |
|     Rezerwowanie                  |     Księga wynajmu skojarzona z identyfikatorem księgi.                                                         |
|     Klasyfikacja        |     Klasyfikacja wynajmu.                                                                  |
|     Warstwa księgowania         |     Warstwa, na której jest księgowany ten wynajem.                                                         |
|     Waluta              |     Waluta wynajmu.                                                                        |
|     Bieżące               |     Suma wszystkich opłat z tytułu wynajmu należnych w ciągu najbliższych 12 miesięcy od daty raportowania.          |
|     13–24 miesięcy          |     Suma wszystkich opłat z tytułu wynajmu należnych od 13 do 24 miesięcy od daty raportowania.           |
|     25–36 miesięcy          |     Suma wszystkich opłat z tytułu wynajmu należnych od 25 do 36 miesięcy od daty raportowania.           |
|     37–48 miesięcy          |     Suma wszystkich opłat z tytułu wynajmu należnych od 37 do 48 miesięcy od daty raportowania.           |
|     49–60 miesięcy          |     Suma wszystkich opłat z tytułu wynajmu należnych od 49 do 60 miesięcy od daty raportowania.           |
|     Okres późniejszy            |     Suma wszystkich opłat z tytułu wynajmu należnych 61 miesięcy od daty raportowania lub później.              |

## <a name="gaap-cash-flows-report"></a>Raporty dotyczące przepływów pieniężnych GAAP
Raport ujawnienia GAAP spełnia wymogi dotyczące ujawnienia zawarte w art. 842-20-50-4(g)(1) amerykańskiej ustawy GAAP. Aby wyświetlić ten raport, należy wybrać opcje **Wynajem składników majątku > Zapytania i raporty > Ujawnienia > GAAP – przepływy pieniężne**. 

|     Pola raportu                                 |     opis                                                                                                                                               |
|------------------------------------------------   |-----------------------------------------------------------------------------  |
|     Data Od <br> Data Do                        |     Służy do definiowania zakresu dat używanego do ograniczania informacji zawartych w raporcie.      |
|     Osoba prawna                                  |     Osoba prawna powiązana z wynajmami.                                      |
|     Typ wynajmu                                    |     Klasyfikacja wynajmu jako finansowy lub operacyjny.           |
|     Identyfikator wynajmu                                      |     Unikatowy identyfikator wynajmu.                                                      |
|     Opis wynajmu                             |     Opis wynajmu z nagłówka wynajmu.                              |
|     Księga wynajmu                                    |     Księga wynajmu, do której odwołuje się wiersz.                        |
|     Warstwa księgowania                                 |     Każda księga dołączana do środka trwałego jest konfigurowany dla konkretnej warstwy księgowania mającej ogólne zamierzenie amortyzacji.                          |
|     Grupa wynajmu                                   |     Grupa, z którą jest związany wynajem.                                     |
|     Waluta                                      |     Skrót użytej waluty transakcji. Wszystkie raporty dokonają konwersji waluty transakcyjnej na walutę raportowania.                      |
|     Leasingi finansowe — operacyjne przepływy pieniężne         |     Suma wszystkich zaksięgowanych płatności zmiennych oraz sumy płatności odsetek zaksięgowanych z harmonogramu amortyzacji między parametrami daty.        |
|     Leasingi finansowe — finansowe przepływy pieniężne           |     Suma wszystkich płatności kwoty zasadniczej z harmonogramu amortyzacji między parametrami daty.       |
|     Leasingi operacyjne — operacyjne przepływy pieniężne       |     Suma wszystkich zaksięgowanych opłat z tytułu wynajmu i zaksięgowanych płatności zmiennych między parametrami daty.            |

## <a name="lease-balances-forecast"></a>Prognoza sald wynajmu
Prognoza salda wynajmu zawiera informacje bezpośrednio z harmonogramu amortyzacji zobowiązań i harmonogramu amortyzacji środków trwałych. Raport zawiera prognozowane kwoty zobowiązania z tytułu wynajmu i składniki majątku z prawem do użytkowania w danym okresie, w tym wszystkie planowane wydatki na te wynajmy. Raport zawiera następujące pola:

|     Pola raportu                 |     opis                                                                                                                                                                               |
|---------------------------------  |--------------------------------------------------------------------------------------------------------------------   |
|     Saldo początkowe             |     Saldo początkowe w harmonogramie amortyzacji wynajmu dla okresu zawierającego datę rozpoczęcia raportu.            |
|     Początkowe rozpoznawanie           |     Jeśli data rozpoczęcia wynajmu przypada w zakresie dat zdefiniowanym dla raportu, w kolumnie zostanie wyświetlona wartość konta zobowiązania wpisu w arkuszu początkowego uznania.      |
|     Płatności                      |     Suma opłat z tytułu wynajmu, które mieszczą się w zakresie dat zdefiniowanym dla raportu.                               |
|     Zainteresowania                      |     Suma kosztów odsetek z tytułu wynajmu, które mieszczą się w zakresie dat zdefiniowanym dla raportu.                    |
|     Saldo końcowe                |     Saldo zobowiązań w wynajmie na dzień **Data początkowa**.                                                             |
|     Krótkoterminowe zobowiązanie          |     Kwota krótkoterminowego zobowiązania w harmonogramie amortyzacji wynajmu na dzień **Data początkowa**.                           |
|     Zobowiązanie długoterminowe           |     Kwota długoterminowego zobowiązania w harmonogramie amortyzacji wynajmu na dzień **Data początkowa**.                            |
|     Początkowa wartość księgowa netto      |     „Początkowa wartość księgowa netto” w harmonogramie amortyzacji składnika majątku dla okresu zawierającego datę rozpoczęcia raportu      |
|     Początkowe rozpoznawanie           |     Jeśli data rozpoczęcia wynajmu przypada między parametrami daty raportu, w kolumnie zostanie wyświetlona wartość konta składnika majątku wpisu w arkuszu początkowego uznania.            |
|     Wydatek amortyzacji          |     Suma kosztów amortyzacji wynajmu, które mieszczą się w zakresie dat zdefiniowanym dla raportu.                  |
|     Saldo końcowe                |     Saldo składnika majątku z tytułu wynajmu na dzień **Data początkowa**.                                                              |
|     Korekta kapitału własnego             |     Saldo początkowe pomniejszone o początkową wartość księgową netto.                                                             |

## <a name="lease-commencements-report"></a>Raport rozpoczęć wynajmu
Raport Rozpoczęcia wynajmu pokazuje wszystkie wynajmy, które rozpoczęły się w określonym zakresie dat, w tym salda początkowego zobowiązania i składnika majątku z prawem do użytkowania. Raport zawiera następujące pola: 

|     Pola raportu                 |     opis                                                                                       |
|---------------------------------  |---------------------------------------------------------------------------------------------------    |
|     Data rozpoczęcia             |     Data wpisu w arkuszu początkowego uznania, który został zaksięgowany dla tej wersji wynajmu.         |
|     Kwota początkowego zobowiązania      |     Kwota zobowiązania z wpisu w arkuszu początkowego uznania.                                  |
|     Początkowa kwota składnika majątku          |     Kwota składnika majątku z wpisu w arkuszu początkowego uznania.                                      |

## <a name="lease-modification-report"></a>Raport modyfikacji wynajmu
Raport modyfikacji wynajmu pokazuje wszystkie wynajmy, które zostały zmodyfikowane w określonym zakresie dat. Raport pokazuje także użytkownika, który skorygował wynajem oraz łączną kwotę skorygowanych zobowiązań. Raport zawiera następujące pola: 

|     Pola raportu                 |     opis           |
|---------------------------------  |-------------------------  |
|     Skorygowane przez                   |     Nazwa użytkownika osoby, która zmodyfikowała wynajem.                                |
|     Data korekty               |     Datę zaksięgowania wpisu w arkuszu korekty.                        |
|     Korekty                   |     Kwota każdego wpisu w arkuszu korekty księgowanego na koncie zobowiązań wynajmu między parametrami daty. Uznania będą miały wartość dodatnią, a obciążenia ujemną.       |
|     Kwota zysku (straty)            |     Kwota każdego wpisu w arkuszu korekty księgowanego na koncie zysków/strat wynajmu między parametrami daty. Uznania będą miały wartość dodatnią, a obciążenia ujemną.       |
|     Wstrzymane dochody             |     Kwota każdego wpisu w arkuszu korekty księgowanego na koncie zysków zatrzymanych między parametrami daty.      |
|     Końcowe saldo zobowiązań      |     Wynikowe saldo zobowiązań na dzień daty korekty wynajmu.           |

## <a name="lease-movement-report"></a>Raport przesunięcia wynajmu
Raport przesunięcia wynajmu służy jako raport przesunięcia do przodu sald zobowiązania z tytułu wynajmu dla poszczególnych wynajmów. Ten raport umożliwia wyświetlenie transakcji zobowiązania wynajmu w podanym okresie.

|     Pola raportu             |     opis                                               |
|----------------------------   |-------------------------------------------------------------- |
|     Data rozpoczęcia         |     Data rozpoczęcia najwcześniejszej wersji wynajmu.    |
|     Okres wynajmu                |     Okres wynajmu najwcześniejszej wersji wynajmu.           |
|     Pozostałe płatności        |     Liczba płatności, które nie zostały jeszcze zaksięgowane dla wynajmu.                       |
|     Saldo początkowe         |     Suma wszystkich transakcji wpływających na zobowiązania z tytułu wynajmu, które wystąpiły przed datą rozpoczęcia raportu.             |
|     Początkowe rozpoznawanie       |     Kwota transakcji początkowego uznania wynajmu, które zostały zaksięgowane w zakresie dat zdefiniowanym dla raportu.     |
|     Płatności                  |     Suma transakcji opłat z tytułu wynajmu, które zostały zaksięgowane w zakresie dat zdefiniowanym dla raportu. Wartości w tej kolumnie będą wyświetlane jako wartości ujemne, ponieważ płatności zmniejszają saldo zobowiązań z tytułu wynajmu.  |
|     Zainteresowania                  |     Suma naliczonych odsetek, które zostały zaksięgowane w ciężar wynajmu w zakresie dat zdefiniowanym dla raportu.            |
|     Korekty               |     Suma zaksięgowanych transakcji korekty z tytułu wynajmu, które mieszczą się w zakresie dat zdefiniowanym dla raportu.                               |
|     Saldo końcowe            |     Saldo wszystkich transakcji zobowiązań z tytułu wynajmu, które zostały zaksięgowane do dnia **Data początkowa** raportu.                  |

## <a name="lease-transactions-report"></a>Raport transakcji wynajmu
Zapytanie o transakcje wynajmu pokazuje wszystkie wpisy w arkuszu, które zostały wygenerowane przez wynajem składnika majątku. Każdy wpis w arkuszu jest połączony z identyfikatorem księgi, z którego pochodzi. Umożliwia to łatwe kojarzenie wpisu w arkuszu z odpowiednim wynajmem. Zapytanie o transakcje wynajmu działa podobnie do strony **Transakcje na załączniku** w księdze głównej.

## <a name="weighted-average-discount-rate-report"></a>Raport Średnia ważona stawka rabatu
Raport Średnia ważona stawka rabatu spełnia wymogi dotyczące ujawniania średniej ważonej stawki rabatu określone w ASC 842-20-50-4 (4) amerykańskiej ustawy GAAP. Aby wyświetlić ten raport, należy wybrać opcje **Wynajem składników majątku > Zapytania i raporty > Ujawnienia > Średnia ważona stawka rabatu**. Raport zawiera następujące pola: 

|     Pola raportu                     |     opis                                                           |
|------------------------------------   |------------------------------------------------------------------------   |
|     Na dzień                        |     Ten raport będzie uwzględniał wszystkie wynajmy, które rozpoczęły się w dniu parametru daty **Data** lub przed nim. Raport ten powinien być uruchamiany ostatniego dnia okresu, który ma być ujawniony.      |
|     Osoba prawna                      |     Osoba prawna, która jest powiązana z wynajmem.                           |
|     Identyfikator wynajmu                          |     Unikatowy identyfikator wynajmu.                                                  |
|     Opis wynajmu                 |     Opis wynajmu z nagłówka wynajmu.                          |
|     Rezerwowanie                              |     Określony typ księgi wyświetlonego wynajmu.                                                                                                                                            |
|     Warstwa księgowania                     |     Każda księga dołączana do środka trwałego jest konfigurowany dla konkretnej warstwy księgowania mającej ogólne zamierzenie amortyzacji.      |
|     Grupa wynajmu                       |     Grupa, do której należy wynajem.                                 |
|     Stawka rabatu                     |     Stawka używana do obliczania rabatu opłat z tytułu wynajmu.                             |
|     Waluta                          |     Skrót użytej waluty transakcji. Wszystkie raporty dokonają konwersji waluty transakcyjnej na walutę raportowania.  |
|     Pozostałe opłaty z tytułu wynajmu          |     Suma kwot niezapłaconych opłat z tytułu wynajmu z harmonogramu płatności od dnia **Data**.            |
|     Pozostałe ważone płatności       |     Pozostałe opłaty z tytułu wynajmu pomnożone przez zastosowaną stawkę rabatu.   |
