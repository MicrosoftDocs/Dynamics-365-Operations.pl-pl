---
title: Przewodnik po funkcji zarządzania zmianami projektowymi
description: Ten temat zawiera Instruktaż kompleksowy pokazujący sposób pracy z zarządzaniem zmianami projektowymi.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 19fab4f6b81eaf6e3605b6668212eece10606360
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987586"
---
# <a name="engineering-change-management-feature-walkthrough"></a>Przewodnik po funkcji zarządzania zmianami projektowymi

[!include [banner](../includes/banner.md)]

Ten temat zawiera Instruktaż kompleksowy pokazujący sposób pracy z zarządzaniem zmianami projektowymi. Przeprowadza przez każdy z najważniejszych scenariuszy:

- Podstawowa konfiguracja funkcji
- W jaki sposób firma projektowa tworzy nowy produkt projektowy
- W jaki sposób firma projektowa zwalnia produkt projektowy do firmy lokalnej
- Sposób, w jaki firma lokalna może przejrzeć i zaakceptować produkt, który został do niej wydany przez firmę projektową
- W jaki sposób firma lokalna może skorzystać z produktu projektowego w transakcjach standardowych
- Sposób dodawania produktu projektowego do zamówienia sprzedaży
- Jak zażądać zmian w produkcie projektowym przez utworzenie projektowego żądania zmiany
- Sposób planowania i implementowania żądanych zmian przez utworzenie projektowego zlecenia zmiany
- Sposób zwolnienia produktu, który został zmieniony

Wszystkie ćwiczenia przedstawione w tym temacie wykorzystują standardowe dane przykładowe dostarczane dla rozwiązania Microsoft Dynamics 365 Supply Chain Management. Ponadto każde ćwiczenie opiera się na poprzednim. Z tego względu zaleca się wykonanie ćwiczeń po kolei od początku do końca, zwłaszcza jeśli funkcja zarządzania zmianami projektowymi nigdy nie była wcześniej używana. Dzięki temu użytkownik uzyska pełne zrozumienie tej funkcji.

## <a name="set-up-for-the-sample-scenario"></a>Konfiguracja scenariusza z przykładu

Aby wykonać przykładowy scenariusz przedstawiony w tym temacie, należy najpierw przygotować funkcję, udostępniając dane demonstracyjne i dodając kilka rekordów niestandardowych.

Przed próbą wykonania dowolnego z tych ćwiczeń w pozostałej części tego tematu postępuj zgodnie z instrukcjami podanymi w poniższych podsekcjach. Te podsekcje przedstawiają również kilka ważnych stron ustawień, które będą używane podczas konfigurowania zarządzania zmianami projektowymi dla własnej organizacji.

### <a name="make-standard-demo-data-available"></a>Udostępnianie standardowych danych demonstracyjnych

Pracuj w systemie, w którym [zainstalowano standardowe dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Standardowe dane demonstracyjne dodają dane dla kilku demonstracyjnych osób prawnych (firm i organizacji). Podczas pracy nad ćwiczeniami można używać narzędzia do wyboru firmy z prawej strony paska nawigacyjnego, aby przełączać między jedną firmą (*DEMF*) skonfigurowaną jako *organizację projektową* i inną firmą (*USMF*) skonfigurowaną jako *organizację operacyjną*.

### <a name="set-up-an-engineering-organization"></a>Konfigurowanie organizacji projektowej

Organizacja projektowa posiada dane projektowe i jest odpowiedzialna za projekt produktu i zmiany produktu. Aby skonfigurować organizacje projektowe, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Konfiguracja &gt; Organizacje projektowe**.
1. Wybierz opcję **Nowy** w celu dodania wiersza do siatki i określ dla niego następujące wartości:

    - **Organizacja projektowa:** *DEMF*
    - **Nazwa organizacji:** *Contoso Entertainment Systems w Niemczech*

    ![Dodawanie organizacji projektowej](media/engineering-org.png "Dodawanie organizacji projektowej")

### <a name="set-up-the-version-product-dimension-group"></a>Konfigurowanie grupy wymiarów produktu dla wersji

1. Przejdź do **Zarządzanie informacjami o produktach &gt; Konfiguracja &gt; Grupy wymiarów i wariantów &gt; Grupy wymiarów produktu**.
1. Wybierz pozycję **Nowy**, aby utworzyć grupę wymiaru produktu.
1. Ustaw pole **Nazwa** na *Wersja*.
1. Wybierz opcję **Zapisz**, aby zapisać nowy wymiar i załaduj wartości do skróconej karty **Wymiary produktu**.
1. W skróconej karcie **Wymiary produktu** należy określić **Wersję** jako aktywny wymiar produktu.

    ![Dodawania grupy wymiaru produktu](media/product-dimension-groups.png "Dodawania grupy wymiaru produktu")

### <a name="set-up-product-lifecycle-states"></a>Konfigurowanie stanów cyklu życia produktu

Ponieważ produkt inżynieryjny przechodzi przez swój cykl życia, ważne jest, aby mieć możliwość kontrolowania, które transakcje są dozwolone w każdym stanie cyklu życia. Aby skonfigurować stany cyklu życia produktu, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Konfiguracja &gt; Stan cyklu życia produktu**.
1. Wybierz opcję **Nowy** w celu dodania stanu cyklu życia i określ dla niego następujące wartości:

    - **Stan:** *Działa*
    - **Opis:** *Działa*

1. Wybierz opcję **Zapisz**, aby zapisać nowy stan cyklu życia i załaduj wartości do skróconej karty **Włączone procesy biznesowe**.
1. Na skróconej karcie **Włączone procesy biznesowe** wybierz procesy biznesowe, które powinny być dostępne. W tym przykładzie należy pozostawić pole **Zasady** ustawione na wartość *Włączone* dla wszystkich procesów biznesowych.

    ![Włączanie procesów biznesowych dla stanu cyklu życia](media/product-lifecycle-states-1.png "Włączanie procesów biznesowych dla stanu cyklu życia")

1. Wybierz opcję **Nowy** w celu dodania następnego stanu cyklu życia i określ dla niego następujące wartości:

    - **Stan:** *Prototyp*
    - **Opis:** *Prototyp*

1. Wybierz opcję **Zapisz**, aby zapisać nowy stan cyklu życia i załaduj wartości do skróconej karty **Włączone procesy biznesowe**.
1. Na skróconej karcie **Włączone procesy biznesowe** wybierz procesy biznesowe, które powinny być dostępne. W tym przykładzie należy ustawić pole **Zasady** ustawione na wartość *Włączone z ostrzeżeniem* dla wszystkich procesów biznesowych.

    ![Włączanie (z ostrzeżeniem) procesów biznesowych dla stanu cyklu życia](media/product-lifecycle-states-2.png "Włączanie (z ostrzeżeniem) procesów biznesowych dla stanu cyklu życia")

### <a name="set-up-a-version-number-rule"></a>Konfigurowanie reguły numeracji wersji

1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Konfiguracja &gt; Reguła numeracji wersji produktu**.
1. Wybierz opcję **Nowa** w celu dodania reguły i określ dla niej następujące wartości:

    - **Nazwa:** *Automatycznie*
    - **Reguła numeracji:** *Automatycznie*
    - **Format:** *V-\#\#*

    ![Dodawanie reguły numeracji wersji produktu](media/version-number-rule.png "Dodawanie reguły numeracji wersji produktu")

### <a name="set-up-a-product-release-policy"></a>Skonfiguruj zasady zwalniania produktów

1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Konfiguracja &gt; Reguły zwalniania produktu**.
1. Wybierz opcję **Nowa** w celu dodania reguły zwalniania i określ dla niej następujące wartości:

    - **Nazwa:** *Składniki*
    - **Opis:** *Składniki*

1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Typ produktu:** *Przedmiot*
    - **Zastosuj szablony:** *Zawsze*
    - **Aktywne:** *Tak*

1. Na skróconej karcie **Wszystkie produkty** wybierz opcję **Dodaj**, aby dodać wiersz, a następnie określ dla niego następujące wartości:

    - **Firma:** *DEMF*
    - **Zwolniony produkt szablonowy:** *D0006*

1. Wybierz polecenie **Dodaj**, aby dodać dodatkowy wiersz i określ dla niego następujące wartości:

    - **Identyfikator kont firmy:** *USMF*
    - **Zwolniony produkt szablonowy:** *D0006*
    - **Odbiór BOM:** Zaznacz to pole wyboru.
    - **Kopiuj zatwierdzenie BOM:** Zaznaczyć to pole wyboru.
    - **Kopiuj aktywację BOM:** Zaznacz to pole wyboru.
    - **Odbiór marszruty:** Zaznacz to pole wyboru.
    - **Kopiuj zatwierdzenie marszruty:** Zaznacz to pole wyboru.
    - **Kopiuj aktywację marszruty:** Zaznacz to pole wyboru.

    ![Dodawanie zasady zwalniania produktów](media/product-release-policy.png "Dodawanie zasady zwalniania produktów")

### <a name="set-up-an-engineering-product-category"></a>Konfigurowanie kategorii produktów projektowych 

Kategorie produktów projektowych stanowią podstawę do tworzenia produktów projektowych (to znaczy produktów podlegających wersji i kontrolowanych za pośrednictwem zarządzania zmianami projektowymi). Aby skonfigurować kategorie produktów projektowych, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Szczegóły kategorii produktów projektowych**.
1. Wybierz pozycję **Nowa**, aby utworzyć kategorię.
1. Na skróconej karcie **Szczegóły** ustaw następujące wartości:

    - **Nazwa:** *Składniki*
    - **Organizacja projektowa:** *DEMF*
    - **Typ produktu:** *Przedmiot*
    - **Śledź wersję w transakcjach:** *Tak*
    - **Grupa wymiarów produktu:** *Wersja*
    - **Stan cyklu życia produktu podczas tworzenia:** *Działa*
    - **Reguła numeracji wersji:** *Automatycznie*
    - **Wymuszaj efektywność:** *Nie*
    - **Zastosuj nomenklaturę reguły numeracji:** *Nie*
    - **Zastosuj nomenklaturę reguły nazywania:** *Nie*
    - **Zastosuj nomenklaturę reguły opisywania:** *Nie*

1. W skróconej karcie **Zasady zwalniania**, w polu **Zasady zwalniania produktów** należy określić wartość *Składniki*.
1. Wybierz opcję **Zapisz**.

    ![Dodawanie kategorii produktów projektowych](media/product-category-details.png "Dodawanie kategorii produktów projektowych")

### <a name="set-up-product-acceptance-conditions"></a>Konfigurowanie warunków akceptacji produktów

1. Aby przełączyć się na osobę prawną (firmę) *USMF*, należy skorzystać z narzędzia do wyboru firmy znajdującego się po prawej stronie paska nawigacyjnego.
1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Konfiguracja &gt; Parametry zarządzania zmianami projektowymi**.
1. Na karcie **Kontrola wydania**, w sekcji **Akceptacja produktu**, w polu **Przyjęcie produktu**, określ wartość *Ręcznie*.

    ![Konfigurowanie warunków akceptacji produktów](media/engineering-change-management-parameters.png "Konfigurowanie warunków akceptacji produktów")

## <a name="create-a-new-engineering-product"></a>Tworzenie nowego produktu projektowego

Produkt projektowy to produkt, który jest zgodny z wersją techniczną i kontrolowany za pośrednictwem zarządzania zmianami projektowymi. Innymi słowy, można kontrolować zmiany w czasie jego użytkowania, a informacje o zmianach zostaną zapisane przy użyciu poleceń zmiany projektowej. Aby utworzyć produkty projektowe, wykonaj następujące kroki.

1. Upewnij się, że jesteś w osobie prawnej swojej organizacji projektowej (w tym przykładzie *DEMF*). W razie potrzeby należy skorzystać z procedury wyboru firmy znajdującej się po prawej stronie paska nawigacji.
1. Otwórz stronę **Zwolnione produkty**, wykonując jeden z następujących kroków:

    - Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**.
    - Przejdź do **Zarządzanie zmianami projektowymi &gt; Typowe &gt; Zwolnione produkty**.

1. W okienku akcji na karcie **Produkt** w grupie **Nowy** wybierz opcję **Atrybuty produktu**.
1. W wyświetlonym oknie dialogowym **Nowy produkt** można ustawić następujące wartości:

    - **Kategoria produktów projektowych:** *Składniki*
    - **Numer produktu:** *Z0001*
    - **Nazwa produktu:** *Zestaw głośników*

    ![Dodawanie produktu projektowego](media/new-product-dialog.png "Dodawanie produktu projektowego")

    Należy zauważyć, że pole **Wersji** jest ustawiane automatycznie przy użyciu zdefiniowanej wcześniej reguły numerowania wersji produktu.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe produkt.
1. Zostanie otwarta strona szczegółów nowego produktu. Zauważ, że wartości są już wypełnione dla niektórych pól, takich jak **Grupa wymiarów magazynowania**, **Grupa wymiarów śledzenia** i/lub **Grupa modeli pozycji**. Te pola zostały ustawione automatycznie, ponieważ produkt jest zwalniany w osobie prawnej *DEMF* i korzysta z zasady wydania produktów *Składniki*, która jest skojarzona z kategorią produktów projektowych *Składniki*. Ponieważ poprzednio użyto pozycji *D0006* jako szablonu w celu skonfigurowania wiersza dla osoby prawnej *DEMF*, wprowadzone wartości zostały pobrane z pozycji *D0006*.

    ![Szczegóły zwolnionego produktu](media/product-details.png "Szczegóły zwolnionego produktu")

1. W okienku akcji na karcie **Projekt** w grupie **Zarządzanie zmianami projektowymi** wybierz opcję **Wersje projektowe**, aby wyświetlić wersje produktu.

    ![Wersje projektowe](media/engineering-versions-list.png "Wersje projektowe")

1. Na stronie **Wersje projektowe** zwróć uwagę, że jest tylko jedna wersja produktu i jest ona aktywna.
1. Wybierz wersję, aby wyświetlić jej szczegóły.

    ![Szczegóły wersji projektowej](media/engineering-version-details.png "Szczegóły wersji projektowej")

1. Na stronie **Wersja projektowa** na skróconej karcie **Lista składowa (BOM)** wybierz opcję **Utwórz BOM**.
1. W oknie dialogowym **Utwórz BOM** ustaw następujące wartości:

    - **Identyfikator BOM:** Z0001
    - **Nazwa:** Zestaw głośników
    - **Oddział:** 1

    ![Tworzenie BOM](media/create-bom.png "Tworzenie BOM")

1. Naciśnij przycisk **OK**, aby dodać BOM i zamknąć okno dialogowe.
1. Na skróconej karcie **Lista składowa (BOM)** wybierz opcję **Lista składowa (BOM)**.
1. Na stronie **Lista składowa (BOM)**, na skróconej karcie **Wiersze listy składowa (BOM)** dodaj trzy wiersze, po jednym dla kodów towarów *D0001*, *D0003* i *D0006*.

    ![Dodawanie wierszy BOM](media/bom.png "Dodawanie wierszy BOM")

1. Wybierz opcję **Zapisz**.
1. Zamknij stronę.
1. Na stronie **Wersja projektowa** na skróconej karcie **Lista składowa (BOM)** wybierz opcję **Zatwierdź**.
1. W oknie dialogowym wybierz **Ok**.

    ![Zatwierdzanie BOM](media/approve-dialog.png "Zatwierdzanie BOM")

1. Na stronie **Wersja projektowa** na skróconej karcie **Lista składowa (BOM)** wybierz opcję **Aktywuj**.
1. Zauważ, że pola wyboru **Aktywne** i **Zatwierdzone** są zaznaczone dla BOM.

    ![Aktywne i zatwierdzone BOM](media/approved-bom.png "Aktywne i zatwierdzone BOM")

1. Zamknij stronę.

## <a name="release-an-engineering-product-to-a-local-company"></a><a name="release"></a>Zwalnianie produktu projektowego do firmy lokalnej

Produkt został teraz zaprojektowany przez dział projektowy. W tym przykładzie produkt jest prototypem opracowanym dla klienta. Ponieważ klientem jest klient osoby prawnej *USMF*, produkt musi zostać zwolniony do tej osoby prawnej.

1. Zachowaj osobę prawną ustawioną na *DEMF*. (W razie potrzeby należy skorzystać z procedury wyboru firmy znajdującej się po prawej stronie paska nawigacji.)
1. Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**.
1. Wybierz produkt *Z0001*.
1. W okienku akcji na karcie **Produkt**, w grupie **Zarządzanie** wybierz pozycję **Struktura wydania produktu**, by otworzyć kreatora **Wydanie produktów**.
1. Na stronie **Wybierz produkty projektowe do zwolnienia** zaznacz pole wyboru **Zaznacz** dla produktu *Z0001*.

    ![Wybieranie produktów projektowych do zwolnienia](media/select-eng-product-to-release.png "Wybieranie produktów projektowych do zwolnienia")

1. Wybierz **Szczegóły zwolnienia**.
1. Zostanie wyświetlona strona **Szczegóły wydania produktu**, na której możesz przejrzeć szczegóły produktu, który zostanie zwolniony, oraz strukturę produktu. Zauważ, że opcja **Wyślij BOM** jest ustawiona wartość *Tak*. Z tego względu zarówno produkt *Z0001*, jak i wszystkie jego elementy podrzędne z BOM zostaną zwolnione.

    W celu przejrzenia szczegółów można wybrać dowolny element podrzędny w lewym okienku. Jeśli dowolny element podrzędny ma BOM, można również wybrać opcję zwolnienia BOM dla tego elementu podrzędnego.

    ![Przeglądanie szczegółów wydania produktu](media/product-release-details.png "Przeglądanie szczegółów wydania produktu")

1. Zamknij stronę, aby powrócić do kreatora **Wydanie produktów**.
1. Wybierz **Dalej**, by otworzyć stronę **Wybierz produkty do wydania**. Jeśli wybrano produkty standardowe (inne niż projektowe), pojawią się one na tej stronie. Należy zauważyć, że po zwolnieniu produktu standardowego przez wybranie opcji **Zwalnianie struktury produktu** zwalniane są także jego BOM i marszruta.

    ![Wybieranie produktów standardowych do zwolnienia](media/select-std-product-to-release.png "Wybieranie produktów standardowych do zwolnienia")

1. Wybierz **Dalej**, by otworzyć stronę **Wybierz warianty produktów do wydania**. W tym przykładzie nie ma żadnych wariantów.
1. Wybierz **Dalej**, by otworzyć stronę **Wybierz firmy**.
1. Wybierz firmy, do których ma zostać zwolniony produkt. W tym przykładzie zaznacz pole wyboru dla **USMF**.

    ![Wybieranie firm, do których ma być zwolniony](media/select-release-companies.png "Wybieranie firm, do których ma być zwolniony")

1. Wybierz **Dalej**, by otworzyć stronę **Potwierdź wybór**.
1. Wybierz **Zakończ**.

## <a name="review-and-accept-the-product-before-you-release-it-in-the-local-company"></a><a name="accept"></a>Przejrzyj i zaakceptuj produkt przed jego zwolnieniem w firmie lokalnej

Dział projektowy udostępnił informacje firmom lokalnym, w których produkt będzie używany. W tym przykładzie firmą lokalną jest *USMF*.

Ponieważ pole **Akceptacja produktu** jest ustawiane na *Ręczne* na stronie **Parametry zarządzania zmianami projektowymi** dla firmy *USMF*, produkty należy ręcznie zaakceptować przed ich zwolnieniem do tej firmy. Innymi słowy, należy je przejrzeć i zatwierdzić, zanim staną się produktami zwolnionymi.

Aby przejrzeć produkt i zwolnić go w firmie *USMF*, należy wykonać następujące kroki.

1. Ustaw osobę prawną na *USMF*. (Należy skorzystać z procedury wyboru firmy znajdującej się po prawej stronie paska nawigacji.)
1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Typowe &gt; Wydania produktów &gt; Otwarte wydania produktów**.

    Na stronie **Otwórz wydania produktów** jest wyświetlany produkt *Z0001*, który ma stan *Oczekujący na akceptację*.

    ![Otwórz wersje produktów](media/open-product-releases.png "Otwórz wersje produktów")

1. Wybierz wartość w kolumnie **Numer produktu**, aby otworzyć stronę **Szczegóły wydania produktu**. Warto pamiętać o następujących szczegółach:

    - Skrócona karta **Ogólne** zawiera informacje o wydaniu produktu, takie jak firma zwalniająca (*DEMF* dla tego przykładu), zwalniający oddział (*1*) i oddział przyjęcia (*1*). Ponieważ w kreatorze **Produktów wydania** nie określono oddziału przyjęcia, wartość zwalniania oddziału jest kopiowana do oddziału przyjęcia.
    - Skrócona karta **Szczegóły wydania** zawiera informacje o produkcie i wersji, które zostały wydane. W tym miejscu można zmodyfikować ustawienia, takie jak daty wejścia w życie.
    - Skrócona karta **Marszruta** przedstawia marszrutę produktu. Jednak w tym przykładzie nie zostały wydane żadne marszruty.

    ![Szczegóły zwolnienia produktu](media/product-release-details-2.png "Szczegóły zwolnienia produktu")

1. Po przejrzeniu informacji można już zaakceptować produkt i w ten sposób zwolnić go w firmie *USMF*. W okienku akcji wybierz pozycję **Akcje &gt; Akceptuj**.
1. Produkt został teraz zwolniony w firmie *USMF*. Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**. Powinna być widoczna pozycja *Z0001*.

## <a name="use-the-product-in-transactions-in-the-local-company"></a>Użycie produktu w transakcjach w firmie lokalnej

Menedżer danych głównych dla firmy *USMF* chce upewnić się, że produkt znajduje się w stanie *Prototyp*, aby zapewnić, że użytkownicy będą ostrzegani, jeśli przypadkowo dodadzą go do procesów, nad którymi pracują.

1. Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**.
1. Wybierz produkt *Z0001*, aby otworzyć jego stronę szczegółów. (Do wyszukania produktu można użyć filtra.)
1. W okienku akcji na karcie **Projekt** w grupie **Zarządzanie zmianami projektowymi** wybierz opcję **Wersje projektowe**.
1. Na stronie **Wersje projektowe** wybierz numer wersji *V-01*, aby otworzyć stronę szczegółów.
1. W okienku akcji na karcie **Produkt** w grupie **Stan cyklu życia** wybierz opcję **Zmień stan cyklu życia**.
1. Na oknie dialogowym listy rozwijanej **Zmień stanu cyklu życia** ustaw **Stan** na *Prototyp*, a następnie kliknij przycisk **OK**.

    ![Zmiana stanu cyklu życia](media/change-lifecycle-state.png "Zmiana stanu cyklu życia")

## <a name="add-the-engineering-product-to-a-sales-order"></a>Dodaj produkt projektowy do zamówienia sprzedaży

Produkt może być teraz sprzedany klientowi. Aby dodać produkt do zamówienia sprzedaży, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing &gt; Zamówienia sprzedaży &gt; Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz *US-0002*, a następnie wybierz **OK**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj wiersz i w polu **Identyfikator pozycji** ustaw wartość *Z000*.
1. Na okienku akcji wybierz opcję **Zapisz**.

    Zostanie wyświetlony komunikat ostrzegawczy informujący, że pozycja ma stan *Prototyp*. Ponieważ jednak komunikat jest tylko ostrzeżeniem, zamówienie sprzedaży zostało utworzone.

    ![Zamówienie sprzedaży dla produktu projektowego](media/sales-order-eng-product.png "Zamówienie sprzedaży dla produktu projektowego")

## <a name="request-changes-in-the-engineering-product"></a>Zażądaj wprowadzenie zmian w produkcie projektowym

Produkt został wysłany do klienta, ale klient nie był w pełni zadowolony i przesyła opinię zawierającą propozycje ulepszeń. Podczas rozmowy telefonicznej klienta ze sprzedawcą sprzedawca może poprosić o zmiany, które klient opisuje.

1. Wybierz kolejno opcje **Sprzedaż i marketing &gt; Zamówienia sprzedaży &gt; Wszystkie zamówienia sprzedaży**.
1. Znajdź i otwórz zamówienie sprzedaży utworzone w poprzednim ćwiczeniu.
1. W skróconej karcie **Wiersze zamówienia sprzedaży** wybierz **Zarządzanie zmianami projektowymi &gt; Nowe żądanie o zmiany projektowe**.

    ![Tworzenie żądania o zmianę projektową na podstawie zamówienia sprzedaży](media/sales-order-eng-change-request.png "Tworzenie żądania o zmianę projektową na podstawie zamówienia sprzedaży")

1. Wprowadź w żądaniu zmiany projektowe na podstawie opinii klienta. W tym przykładzie ustaw następujące wartości:

    - **Żądanie zmiany:** *555*
    - **Tytuł:** *Zmiana klienta Z0001*
    - **Priorytet:** *niski*
    - **Kategoria:** zmiana ustawienia
    - **Ważność:** *Średnia*

1. Na skróconej karcie **Informacje** wybierz **Nowe &gt; Uwaga**, aby dodać uwagę do siatki.
1. W polu nowej uwagi **Opis** wskaż, że pozycja *D0003* powinna zostać usunięta z BOM. Jeśli trzeba dodać więcej informacji w uwadze, można wprowadzić tekst w polu **Uwagi**.

    ![Żądanie zmian projektowych](media/eng-change-request.png "Żądanie zmian projektowych")

1. Na okienku akcji wybierz opcję **Zapisz**.
1. Zauważ, że pozycja została automatycznie dodana do skróconej karty **Produkty** i że źródło tego żądania zmiany projektowej (zamówienie sprzedaży) zostało dodane w skróconej karcie **Źródło**.

## <a name="make-changes-to-the-product-by-using-an-engineering-change-order"></a>Wprowadzanie zmian w produkcie przy użyciu zlecenia zmiany projektowej

Pracownik działu sprzedaży wie, że produkt jest ważny i został zaprojektowany specjalnie dla tego klienta. W związku z tym pracownik działu sprzedaży dzwoni do inżyniera w firmie *DEMF* w celu powiadomienia go o żądaniu zmiany. W ten sposób inżynier może przyspieszyć proces.

Inżynier przegląda teraz żądanie od klienta i tworzy zamówienie zmiany dla produktu.

1. Ponieważ inżynier pracuje w firmie *DEMF*, należy skonfigurować osobę prawną do *DEMF*. (Należy skorzystać z procedury wyboru firmy znajdującej się po prawej stronie paska nawigacji.)
1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Typowe &gt; Żądania zmiany projektowej**.
1. Otwórz żądanie zmiany *555*.
1. Przejrzyj informacje, a następnie zatwierdź zmianę. W okienku akcji, na karcie **Żądanie zmiany** w grupie **Zmień stan** wybierz **Zatwierdź**.
1. Przejdź do **Zarządzanie zmianami projektowymi &gt; Typowe &gt; Zlecenie zmiany projektowej**.
1. W okienku akcji wybierz opcję **Nowa**, aby utworzyć zlecenie zmiany, i określ dla niej następujące wartości:

    - **Zlecenie zmiany:** *555*
    - **Tytuł:** *Zmiana klienta Z0001*
    - **Kategoria:** *Zmiana klienta*
    - **Priorytet:** *Niski*
    - **Ważność:** *Średnia*

1. Na skróconej karcie **Produkty, który dotyczy** wybierz opcję **Nowe &gt; Dodaj istniejący produkt**, aby dodać wiersz do siatki, a następnie określ dla niego następujące wartości:

    - **Produkt:** *Z0001*
    - **Wpływ:** *Nowa wersja*

    ![Tworzenie zlecenia zmiany projektowej](media/eng-change-order.png "Tworzenie zlecenia zmiany projektowej")

1. Zwróć uwagę, że ponieważ pole **Wpływ** jest ustawiane na *Nową wersję*, pole **Nowa wersja** na karcie **Szczegóły** skróconej karty **Szczegóły produktu** zawiera informacje o nowym numerze wersji (w tym przykładzie *V-02*).

    ![Szczegóły produktu dla zlecenia zmiany projektowej](media/eng-change-order-product-details.png "Szczegóły produktu dla zlecenia zmiany projektowej")

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W skróconej karcie **Szczegóły produktu**, na karcie **Lista składowa (BOM)** wybierz opcję **Wiersze**, aby otworzyć BOM dla wersji *V-01* produktu *Z0001*.

    ![Wiersze BOM produktu projektowego](media/eng-product-bom-lines.png "Wiersze BOM produktu projektowego")

1. Wybierz wiersz dla identyfikatora pozycji *D0003*, a następnie w okienku akcji wybierz opcję **Usuń**. Wartość w polu **Typ zmiany** dla tego wiersza zmieni się na *Usunięte*.
1. Na okienku akcji wybierz opcję **Zapisz**.

    ![Wiersze BOM zmodyfikowanego produktu projektowego](media/eng-product-bom-lines-modified.png "Wiersze BOM zmodyfikowanego produktu projektowego")

1. Zamknij stronę **Wiersz BOM** w celu powrotu do strony **Zlecenie zmiany projektowej**.
1. W skróconej karcie **Szczegóły produktu** na karcie **Lista składowa (BOM)** należy zauważyć, że wartość w polu **Typ zmiany** dla *Z0001* list składowej (BOM) wynosi teraz *Zmienione*.

    ![Zlecenie zmiany projektowej zawierające zmienioną BOM](media/eng-change-order-changed-bom.png "Zlecenie zmiany projektowej zawierające zmienioną BOM")

    Przed przetwarzaniem zmian należy teraz zatwierdzić zlecenie. Podczas przetwarzania zmian produkty są aktualizowane przy użyciu zmian uwzględnionych w zleceniu zmiany projektowej. W tym przykładzie osoba tworząca zlecenie zmiany projektowej została określona jako osoba zatwierdzająca.

1. W okienku akcji, na karcie **Zlecenie zmiany** w grupie **Zmień stan** wybierz **Zatwierdź**.
1. Wybierz opcję **Przetwórz**, aby zaktualizować informacje o produkcie.
1. Wybierz opcję **Zakończ**, aby oznaczyć zamówienie zmiany jako zakończone.

## <a name="release-the-changed-product"></a>Zwolnij zmieniony produkt

Produkt może zostać teraz zwolniony do firmy *USMF*, a następnie wysłany do klienta. Aby zwolnić produkt bezpośrednio ze zlecenia zmiany projektowej, wykonaj następujące kroki.

1. Otwórz zamówienie zmiany projektowej utworzone w poprzednim ćwiczeniu, jeśli nie zostało jeszcze otwarte.
1. W okienku akcji, na karcie **Zlecenie zmiany** w grupie **Wydania produktu** wybierz **Szukaj**.
1. Wyniki wyszukiwania pokazują, do których firm zmienione produkty zostały wydane. Zamknij wyniki wyszukiwania.
1. W okienku akcji, na karcie **Zlecenie zmiany**, w grupie **Wydania produktów** wybierz opcję **Widok**, aby otworzyć okno dialogowe **Zwolnienia**, w którym możesz przejrzeć wyniki poprzedniego wyszukiwania.
1. Wybierz każdą firmę, do której chcesz zwolnić produkty.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Wydania** i wrócić do strony zlecenia zmiany.
1. W okienku akcji na karcie **Zlecenie zmiany** w grupie **Wydania produktów** wybierz opcję **Przetwórz**, aby zwolnić zmienione produkty do wybranych firm. Możesz również wybrać opcję **Zwolnij strukturę produktu**, aby rozpocząć proces zwalniania.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]