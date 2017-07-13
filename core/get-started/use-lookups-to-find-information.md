---
title: "Używanie odnośników do znajdowania informacji"
description: "W programie Microsoft Dynamics 365 for Finance and Operations wiele pól ma odnośniki (służące do wyszukiwania), które bardzo ułatwiają znajdowanie poprawnych lub żądanych wartości. W funkcjonalności odnośników wprowadzono szereg ulepszeń, które zwiększają użyteczność tych formantów i w efekcie wydajność pracy użytkowników. W tym temacie dowiesz się więcej o tych nowych funkcjach odnośników i otrzymasz pomocne wskazówki dotyczące ich optymalnego wykorzystywania w systemie."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: a5d0a9edd2cb5747fc799c6fdca45dd9ba5720f7
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Używanie odnośników do znajdowania informacji
<a id="use-lookups-to-find-information" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W programie Microsoft Dynamics 365 for Finance and Operations wiele pól ma odnośniki (służące do wyszukiwania), które bardzo ułatwiają znajdowanie poprawnych lub żądanych wartości. W funkcjonalności odnośników wprowadzono szereg ulepszeń, które zwiększają użyteczność tych formantów i w efekcie wydajność pracy użytkowników. W tym temacie dowiesz się więcej o tych nowych funkcjach odnośników i otrzymasz pomocne wskazówki dotyczące ich optymalnego wykorzystywania w systemie.  

Odnośniki elastyczne
<a id="responsive-lookups" class="xliff"></a>
------------------

W poprzednich wersjach programu Finance and Operations podczas interakcji z formantem odnośnika użytkownik musiał jednoznacznie otworzyć menu rozwijane. Mogło się do odbywać poprzez wpisanie gwiazdki (\*) w formancie, aby wyfiltrować wyszukiwanie na podstawie bieżącej wartość formantu, kliknięcie przycisku rozwijanego lub użycie skrótu klawiaturowego **Alt**+**strzałka w dół**. Formanty wyszukiwania zostały zmodyfikowane w następujący sposób, aby lepiej pasowały do obecnych praktyk używania Internetu:

-   Menu rozwijane wyszukiwania teraz otwierają się automatycznie po krótkim wstrzymaniu pisania, z zawartością listy rozwijanej wyfiltrowaną w oparciu o wartość formantu wyszukiwania.
    -   Należy zauważyć, że stare zachowanie automatycznego otwierania listy rozwijanej po wpisaniu gwiazdki (\*) zostało wycofane.
-   Po otwarciu menu rozwijanego wyszukiwania mają miejsce następujące zdarzenia:
    -   Kursor pozostaje w formancie wyszukiwania (fokus już nie jest przenoszony do menu rozwijanego), co pozwoli dalej wprowadzać modyfikacje w wartości formantu. Jednak użytkownik może nadal używać **strzałki w górę** i **strzałki w dół**, aby zmieniać wiersze w menu rozwijanym, oraz nacisnąć klawisz Enter, aby wybrać bieżący wiersz w menu rozwijanym.
    -   Zawartość menu rozwijanego będzie się odpowiednio dopasowywać po wszelkich modyfikacjach wartości formantu wyszukiwania.

Rozważmy na przykład pole wyszukiwania o nazwie **Miejscowość**. 

Gdy fokus znajduje się w polu **Miejscowość**, można rozpocząć wyszukiwanie żądanej miejscowość, wpisując kilka liter, takich jak „kaz”.  Gdy skończysz wpisywanie, odnośnik otworzy się automatycznie z wyfiltrowanymi miejscowościami o nazwach zaczynających się od „kaz”. 

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png) 

W tym momencie kursor jest nadal w polu wyszukiwania. Jeśli będziesz kontynuować wpisywanie, tak że wartość zmieni się na „kazim”, zawartość odnośnika automatycznie się dostosuje i będzie odzwierciedlała najnowszą wartość w formancie. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Mimo iż fokus jest nadal w formancie wyszukiwania, można również użyć klawiszy **strzałki w górę** lub **strzałki w dół**, aby zaznaczyć wiersz, który chcesz wybrać. Jeśli naciśniesz klawisz **Enter**, zaznaczony wiersz zostanie wybrany w odnośniku, a wartość formantu zostanie zaktualizowana. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## Wpisywanie nie tylko identyfikatorów
<a id="typing-in-more-than-ids" class="xliff"></a>
Podczas wprowadzania danych jest naturalne dla użytkowników, że próbują identyfikować jednostkę, taką jak odbiorca lub dostawca, za pomocą nazwy, a nie oficjalnego identyfikatora. W obecnej wersji programu Finance and Operations wiele (choć nie wszystkie) odnośniki pozwalają teraz na kontekstowe wprowadzanie danych. Ta zaawansowana funkcja umożliwia użytkownikowi wpisanie identyfikatora lub odnośnej nazwy w formancie wyszukiwania. 

Na przykład rozważmy pole **Konto odbiorcy** podczas tworzenia zamówienia sprzedaży. To pole zawiera **identyfikator konta** odbiorcy, ale podczas tworzenia zamówienia sprzedaży użytkownik zazwyczaj wolałby wpisać **nazwę konta** zamiast **identyfikatora konta**, np. „Hurtownia leśna” zamiast „PL-003”.

Jeśli użytkownik zacznie wpisywać **identyfikator konta** w formancie wyszukiwania, menu rozwijane otworzy się automatycznie zgodnie z opisem w poprzedniej sekcji i użytkownik zobaczy odnośnik, jak pokazano niżej.

[![Wyszukiwanie kontekstowe po wprowadzeniu identyfikatora konta odbiorcy](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

Jednak użytkownik może teraz również wprowadzić początek **nazwy konta**. Jeśli system to wykryje, użytkownik zobaczy poniższy odnośnik. Zwróć uwagę, jak kolumna **Nazwa** przesunęła się i jest teraz pierwszą kolumną w odnośniku, a odnośnik został posortowany i wyfiltrowany w oparciu o zawartość kolumny **Nazwa**.

[![Wyszukiwanie kontekstowe po wprowadzeniu nazwy odbiorcy](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## Używanie nagłówków kolumn siatki do bardziej zaawansowanego filtrowania i sortowania
<a id="using-grid-column-headers-for-more-advanced-filtering-and-sorting" class="xliff"></a>
Ulepszenia odnośników omówione w poprzednich dwóch rozdziałach znacznie poprawiają zdolność użytkownika do nawigowania po wierszach odnośnika w oparciu o wyszukiwanie „zaczyna się od” zastosowanego do pola **Identyfikator** lub **Nazwa** w odnośniku. Jednak istnieją sytuacje, w których do znalezienia prawidłowego wiersza jest potrzebne bardziej zaawansowane filtrowanie (lub sortowanie). W takich sytuacjach użytkownik musi użyć opcji filtrowania i sortowania nagłówków kolumn siatki wewnątrz odnośnika. Rozważmy na przykład pracownika wprowadzającego wiersz zamówienia sprzedaży, który musi odnaleźć prawidłowy „kabel” jako produkt. Wpisanie słowa „kabel” w formancie **Numer pozycji** nie wystarczy, ponieważ nie istnieją żadne nazwy produktów rozpoczynające się od „kabel”. 

![emptyitemlookup](./media/emptyitemlookup.png) 

Zamiast tego użytkownik musi wyczyścić wartości formantu wyszukiwania, otworzyć menu rozwijane wyszukiwania i wyfiltrować to menu przy użyciu nagłówka kolumny siatki, jak pokazano niżej. Użytkownik posługujący się myszą (lub ekranem dotykowym) może po prostu kliknąć (lub dotknąć) dowolny nagłówek kolumny, aby uzyskać dostęp do opcji filtrowania i sortowania tej kolumny. Użytkownik posługujący się klawiaturą musi po prostu nacisnąć kombinację klawiszy **Alt**+**strzałka** **w dół** drugi raz, aby przenieść fokus do menu rozwijanego, po czym klawiszem tabulacji przejść do odpowiedniej kolumny i nacisnąć kombinację klawiszy **Ctrl**+**G**, a zostanie otwarte menu rozwijane nagłówka kolumny siatki. 

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png) 

Po zastosowaniu filtra (zobacz obraz poniżej) użytkownik może odnaleźć i zaznaczyć wiersz w zwykły sposób. 

![filtereditemlookup](./media/filtereditemlookup.png)




