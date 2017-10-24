---
title: "Omówienie konwersji na koszt standardowy"
description: "Ten artykuł zawiera omówienie procesu ułatwiające konfigurowanie i wykonywanie konwersji na koszt standardowy. Podane kroki należy wykonać po spełnieniu warunków wstępnych konwersji na koszt standardowy."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 78212
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2e59fd6e137d5f677ed4055385ef88922c8c42ba
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="standard-cost-conversion-overview"></a>Omówienie konwersji na koszt standardowy

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie procesu ułatwiające konfigurowanie i wykonywanie konwersji na koszt standardowy. Podane kroki należy wykonać po spełnieniu warunków wstępnych konwersji na koszt standardowy. 

Do konwertowania modelu zapasów partii wybranych towarów z określania kosztu rzeczywistego na określanie kosztu standardowego służy strona **Konwersje na koszt standardowy**. Proces konwersji obejmuje wymagane zamknięcie zapasów, kilka czynności w okresie przejściowym (jest to czas między datą rozpoczęcia zamiany a planowaną datą konwersji), wykonanie konwersji i odpowiednie zamknięcie zapasów.

-   Zamknięcie zapasów przed okresem przejściowym — Zamknięcie zapasów jest wymagane, ponieważ rozlicza otwarte transakcje na towarze starą metodą wyceny. W okresie przejściowym można wprowadzać i księgować transakcje z datami wstecznymi, np. faktury, dzięki czemu można zamknąć poprzedni okres. Data zamknięcia zapasów musi przypadać jeden dzień przed datą rozpoczęcia zamiany w celu zapewnienia wyraźnej przerwy między starą a nową metodą wyceny.
-   Działania konwersji w okresie przejściowym — Na stronie **Konwersje na koszt standardowy** należy utworzyć rekord konwersji, który będzie zawierać także zdefiniowany przez użytkownika identyfikator nowej wersji obliczania kosztów. Wskazuje się towary wymagające konwersji, a następnie wprowadza oczekujące koszty standardowe towaru w nowo tworzonej wersji wyceny. Wykonuje się sprawdzenie wybranych towarów w celu wykrycia problemów mogących uniemożliwić konwersję, rozwiązuje problemy, a następnie wykonuje kolejne sprawdzenie. Po pomyślnym sprawdzeniu towarów zmienia się stan rekordu konwersji na **Gotowe**. W zaplanowanym dniu należy wykonać konwersję, a opcjonalnie można również zamknąć zapasy. Przesunięcia magazynowe towaru w okresie przejściowym są księgowane i wyceniane według starego modelu zapasów. Następnie po pomyślnym ukończeniu konwersji są ponownie wyceniane według kosztu standardowego.
-   Zamknięcie zapasów przed konwersją — Zamknięcie zapasów może być częścią konwersji w zaplanowanym dniu. Może być także wykonane oddzielnie wcześniej, przed rozpoczęciem konwersji.

Po pomyślnym zakończeniu procesu konwersji model zapasów każdego towaru bazuje na koszcie standardowym i koszt standardowy towaru jest włączony. Kolejne transakcje magazynowe będą wyceniane według standardowego kosztu towaru. Ponadto system przekonwertuje fizyczne transakcje magazynowe przyjęć i wydań towaru na koszt standardowy zgodnie z datą konwersji. System przekonwertuje także finansowo dostępne zapasy towaru na koszt standardowy i zaksięguje różnicę wartości jako przeszacowanie wartości zapasów. Wszystkie transakcje dokonane po konwersji są wyceniane według standardowego kosztu towaru. Nie można wprowadzać transakcji z datą wsteczną przed datą konwersji, ponieważ magazyn trzeba zamknąć jeden dzień przed datą konwersji. Konwersję można wykonać tylko wtedy, jeśli zapasy zostały zamknięte jeden dzień wcześniej. Tego zamknięcia zapasów nie można anulować.

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a>1. Definiowanie rekordu konwersji na koszt standardowy i powiązanej z nim wersji wyceny
Na stronie **Konwersje na koszt standardowy** można utworzyć rekord konwersji. Warunkiem utworzenia nowego rekordu konwersji jest wypełnienie istniejących rekordów tego typu. Czas trwania planowanego okresu przejściowego jest definiowany za pomocą daty początkowej przejścia i daty planowanej konwersji. Planowany okres przejściowy może wynosić nawet jeden dzień. Zaplanowany okres przejściowy pomaga się upewnić, że jest dość czasu na wykonanie wszystkich kroków procesu konwersji. Na dzień przed datą początkową zamiany musi zostać wykonane zamknięcie zapasów, aby zagwarantować ukończenie rozliczeń przed rozpoczęciem procesu konwersji. Aby zagwarantować poprawne dopasowanie dat rozpoczęcia przejścia i zamknięcia zapasów, można zmienić datę początkową przejścia na jeden dzień po istniejącym zamknięciu zapasów lub wykonać zamknięcie zapasów. Podczas wprowadzania rekordu konwersji można także wprowadzić zdefiniowany przez użytkownika identyfikator dla nowej wersji wyceny, która będzie zawierać koszty standardowe konwertowanych towarów. Wersja wyceny jest generowana automatycznie podczas zapisywania rekordu konwersji.

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a>2. Przegląd i modyfikacja nowej wersji wyceny dla rekordu konwersji
Nowa wersja wyceny jest dedykowana rekordowi konwersji, tak jak wskazuje typ wyceny **Konwersja**. Dedykowana wersja wyceny przypomina wersję wyceny dla kosztów standardowych i zawiera rekordy kosztów towaru powiązanych z rekordem konwersji. Dedykowana wersja wyceny rekordu konwersji ma następujące ustawienia umieszczone na różnych kartach, które należy przejrzeć i w razie potrzeby zmodyfikować:

-   **Typ wyceny:** W tym polu należy ustawić wartość **Koszt standardowy**.
-   **Wersja:** Identyfikator odzwierciedla informacje wprowadzone w rekordzie konwersji dla identyfikatora wersji wyceny.
-   **Nazwa:** Domyślnie pole nazwy jest puste. Można w nim opcjonalnie wpisać nazwę.
-   **Zablokuj:** W tym polu należy ustawić wartość **Nie**. W wersji wyceny można wprowadzać rekordy kosztów do czasu, aż stan rekordu konwersji zostanie zmieniony na **Gotowe**. Stan **Gotowe** oznacza, że wybrane towary zostały sprawdzone, w związku z czym modyfikowanie rekordów kosztów jest zabronione.
-   **Blokada aktywacji:** W tym polu należy ustawić wartość **Tak**. Wtedy nie można ręcznie uaktywnić oczekującego rekordu kosztu w dedykowanej wersji wyceny. Aktywacja następuje podczas wykonywania konwersji.
-   **Od dnia:** Data początkowa odzwierciedla datę planowanej konwersji wprowadzoną w rekordzie konwersji.
-   **Oddział:** To pole pozostanie puste, dzięki czemu rekordy kosztów będzie można wprowadzać dla dowolnego oddziału.
-   **Grupa pól Zezwól na typ ceny:** W tym polu ustaw wartość **Tak**, dzięki czemu będzie można wprowadzać tylko rekordy kosztu własnego.
-   **Zasada alternatywnego źródła:** W tym polu ustaw wartość **Brak**. Jeśli potrzebne są informacje o kosztach uaktywnione w innych wersjach wyceny, zmień wartość tego ustawienia na **Aktywne**. Na przykład w celu obliczenia kosztów wytwarzanych towarów mogą być wymagane informacje o kosztach składników, kategoriach kosztów i kosztach pośrednich.
-   **Alternatywna wersja wyceny:** Pozostaw to pole puste.

Informacjami o kosztach towarów w dedykowanej wersji wyceny można zarządzać tylko na stronie **Konwersje na koszt standardowy**. Nie można używać strony **Konfiguracja wersji wyceny** ani strony **Obsługa wersji wyceny** do obliczania kosztów w wersji wyceny podczas konwersji. Można jednak używać tych stron do zarządzania dedykowaną wersją wyceny po zakończeniu procesu konwersji.

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a>3. Określanie towarów do przekonwertowania na koszt standardowy
Na stronie **Konwersje na koszt standardowy** należy określić poszczególne towary, które powinny zostać przekonwertowane na wycenę według kosztu standardowego. W celu dodania wielu towarów należy użyć strony **Dodaj pozycje do konwersji na koszt standardowy**. Zazwyczaj wszystkie wytwarzane towary trzeba umieścić w jednym rekordzie konwersji, aby zagwarantować poprawność liczenia kosztów.

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a>4. Wprowadzanie lub obliczanie oczekującego kosztu standardowego dla każdego konwertowanego towaru
Za pomocą strony **Cena pozycji** wprowadź oczekujące koszty standardowe w dedykowanej wersji wyceny dla towarów kupowanych i przenoszonych. Rekordy kosztów dotyczą tylko określonego oddziału, dlatego koszty oczekujące towaru muszą zostać wprowadzone odnośnie do każdego oddziału. Użyj strony **Cena pozycji** do obliczania oczekujących kosztów standardowych towarów wytwarzanych. Koszty oczekujące wytwarzanego towaru należy obliczyć osobno dla każdego oddziału produkcyjnego, chyba że oddział jest objęty operacją przenoszenia. W takim przypadku koszty oczekujące należy wprowadzić ręcznie. Niektóre towary mogą mieć wymiary koloru, rozmiaru czy konfiguracji produktu. Na stronie **Konwersje na koszt standardowy** pole wyboru **Użyj kosztu własnego według wariantu** umożliwia wyświetlenie kosztu standardowego dla każdej kombinacji wymiarów produktu. Jeśli to pole wyboru jest wyczyszczone, trzeba wprowadzić tylko koszt oczekujący danego towaru.

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a>5. Wykrywanie i rozwiązywanie wszystkich problemów z konwertowanymi towarami
Ustal, jakie problemy występują, korzystając z raportu **Testy konwersji na koszt standardowy**. Jeśli z danym towarem nie jest związany żaden problem, jego stan w rekordzie konwersji zmienia się na **Sprawdzone**. Wykryty problem należy rozwiązać, a następnie należy ponownie uruchomić raport, aby stan towaru zmienił się na **Sprawdzone**. Jeśli problemów nie da się rozwiązać na czas, można opcjonalnie usunąć dany towar z rekordu konwersji i przekonwertować go później.

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a>6. Zmiana stanu rekordu konwersji na Gotowe
Po zmianie stanu rekordu konwersji na **Gotowe** system wykonuje ostatnie sprawdzenie tego rekordu, a następnie uruchamia konwersję na koszt standardowy. Zmiana stanu na **Gotowe** następuje tylko po spełnieniu następujących warunków:

-   Każdy towar w rekordzie konwersji ma stan **Sprawdzone**.
-   Wykonano zamknięcie zapasów na dzień przed datą rozpoczęcia przejścia. Aby zagwarantować poprawne dopasowanie dat rozpoczęcia przejścia i zamknięcia zapasów, można zmienić datę początkową przejścia na jeden dzień po istniejącym zamknięciu zapasów lub wykonać zamknięcie zapasów.

## <a name="7-back-up-the-database-before-conversion"></a>7. Tworzenie kopii zapasowej bazy danych przed konwersją
Kopia zapasowa pozwoli przywrócić bazę danych w przypadku wystąpienia błędów w procesie konwersji.

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a>8. Wykonywanie konwersji, gdy rekord konwersji ma stan Gotowe
Proces konwersji wymaga wykonania zamknięcia zapasów na dzień przed terminem planowanej konwersji. Ten wymóg pomaga zapewnić, że w okresie przejściowym nie będzie można wprowadzać transakcji z datą wsteczną. Jeśli zamknięcie zapasów nie zostało jeszcze wykonane, pojawi się monit o przeprowadzenie tej operacji w ramach procesu konwersji. Towary są konwertowane pojedynczo, począwszy od tych na najniższym poziomie w strukturze produktów (decydują szczegółowe kody towarów). Po pomyślnym przekonwertowaniu towaru jego stan w rekordzie konwersji zmienia się na **Przekonwertowane**. Jeśli proces konwersji zostanie przerwany, wszystkie towary, które nie zostały pomyślnie przekonwertowane, będą nadal miały stan **Sprawdzone**. Pomyślne zakończenie procesu konwersji powoduje następujące skutki:

-   Stan rekordu konwersji zmienia się z **Gotowe** na **Zakończone**, a stan każdego wybranego towaru ze **Sprawdzone** na **Przekonwertowane**.
-   Grupa modeli towarów, do której należą przekonwertowane towary, zostaje zmieniona, tak aby odzwierciedlała nową grupę o modelu zapasów typu „koszt standardowy”.
-   Koszty standardowe przekonwertowanych towarów zostają włączone w dedykowanej wersji wyceny.
-   Typ wyceny w wersji wyceny zmienia się z **Konwersja** na **Koszt standardowy**, a wersja wyceny jest teraz taka sama jak inne wersje wyceny dla kosztów standardowych.

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a>9. Sprawdzenie poprawności i uzgodnienie wartości zapasów dla przekonwertowanych towarów
Raport **Sprawozdanie z analizy odchyleń** umożliwia analizowanie odchyleń przeszacowania wartości, a raport **Wartość zapasów** służy do wyświetlania wartości zapasów na określony dzień.

-   Przeanalizuj odchylenia względem przeszacowania. W raporcie **Sprawozdanie z analizy odchyleń** przejrzyj odchylenia przeszacowania wartości zapasów przekonwertowanych towarów. Można także na stronie **Transakcje kosztu standardowego** wyświetlić transakcje przeszacowania wartości zapasów dla przekonwertowanych towarów, które istnieją w zapasach.
-   Przeanalizuj wartość zapasów sprzed daty początkowej przejścia. Za pomocą raportu **Wartość zapasów** przejrzyj wartości zapasów dla przekonwertowanych towarów. W ustawieniu raportu Do dnia użyj daty, która przypada jeden dzień przed datą rozpoczęcia zamiany.
-   Przeanalizuj wartość zapasów sprzed daty konwersji. Za pomocą raportu **Wartość zapasów** przejrzyj wartości zapasów dla przekonwertowanych towarów. W ustawieniu raportu Do dnia użyj daty, która przypada jeden dzień przed datą konwersji.
-   Przeanalizuj wartość zapasów w dniu konwersji. Za pomocą raportu **Wartość zapasów** przejrzyj wartości zapasów na dzień konwersji. Ustawienia raportu Od dnia i Do dnia powinny mieć wartość daty konwersji. Kryteria wyboru dla raportu powinny być zgodne z przekonwertowanymi towarami.
-   Przeanalizuj przesunięcia magazynowe z datą wsteczną. Korzystając z raportu **Wartość zapasów**, wyświetl przesunięcia magazynowe z datami wstecznymi wprowadzone po konwersji. Ustawienia raportu Od dnia i Do dnia powinny odpowiadać dacie początkowej przejścia i datę konwersji minus jeden dzień. Kryteria wyboru dla raportu powinny być zgodne z przekonwertowanymi towarami. W raporcie zostaną wyświetlone przesunięcia magazynowe wykonane według kosztu standardowego w trakcie okresu przejściowego.


<a name="see-also"></a>Informacje dodatkowe
--------

[Wymagania wstępne dotyczące konwersji na koszt standardowy](prerequisites-standard-cost-conversion.md)




