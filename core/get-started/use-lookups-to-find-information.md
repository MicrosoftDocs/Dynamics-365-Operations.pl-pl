---
title: "Użyj wyszukiwania, aby znaleźć informacje"
description: "W programie Microsoft Dynamics 365 dla operacji wiele pól mają wyszukiwania, które mogą pomóc szybko znaleźć zainstalowanego lub żądaną wartość. Kilka ulepszeń zostały dodane do odnośników, które czynią te formanty bardziej użyteczny i użytkownik był bardziej wydajne. W tym temacie będzie więcej informacji na temat tych nowych funkcji wyszukiwania i otrzyma kilka pomocnych wskazówek, aby uzyskać optymalne wykorzystanie spośród wyszukiwań w systemie."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 6a25593632575dcd71fa4a3c9cf5b83c9f8ecd39
ms.lasthandoff: 03/31/2017


---

# <a name="use-lookups-to-find-information"></a>Użyj wyszukiwania, aby znaleźć informacje

W programie Microsoft Dynamics 365 dla operacji wiele pól mają wyszukiwania, które mogą pomóc szybko znaleźć zainstalowanego lub żądaną wartość. Kilka ulepszeń zostały dodane do odnośników, które czynią te formanty bardziej użyteczny i użytkownik był bardziej wydajne. W tym temacie będzie więcej informacji na temat tych nowych funkcji wyszukiwania i otrzyma kilka pomocnych wskazówek, aby uzyskać optymalne wykorzystanie spośród wyszukiwań w systemie.  

<a name="responsive-lookups"></a>Elastyczne wyszukiwań
------------------

W poprzednich wersjach programu Dynamics 365 dla operacji, podczas interakcji z formant wyszukiwania użytkownik musiałby jednoznacznym otworzyć menu rozwijane. Może być to po wpisaniu gwiazdki (\*) w kontroli filtrować odnośnika opartego na bieżącą wartość formantu, klikając przycisk listy rozwijanej, lub za pomocą **Alt**+**Strzałka w dół** skrót klawiaturowy. Formanty wyszukiwania zostały zmienione w następujący sposób, aby lepiej wyrównać z aktualną praktyką w sieci web:

-   Menu rozwijane Wyszukaj teraz zostanie automatycznie otwarty po wstrzymaniu nieznaczne pisania, z listy rozwijanej zawartość menu filtrowane w oparciu o wartość formant wyszukiwania odnośników.
    -   Należy zauważyć, że stare zachowanie automatycznego otwierania listy rozwijanej po wpisaniu gwiazdki (\*) jest przestarzała.
-   Po otwarciu menu rozwijanego odnośników, mają miejsce następujące czynności:
    -   Kursor pozostanie w formant wyszukiwania odnośników (zamiast fokus do menu rozwijanego), nadal można wprowadzać modyfikacje do wartości formantu. Jednak użytkownik może nadal używać **Strzałka w górę** i **Strzałka w dół** Aby zmienić wiersze w menu rozwijane i enter, aby wybrać bieżący wiersz w menu rozwijanego.
    -   Wszelkich modyfikacji wartości formantu wyszukiwania będzie dopasować zawartość menu rozwijanego.

Rozważmy na przykład pole wyszukiwania o nazwie **miasta**. 

Gdy fokus znajduje się w **miasta** pole, można rozpocząć wyszukiwanie miejscowość, w której chcesz wpisać kilka liter, takie jak "kol."  Po zakończeniu wpisywania, wyszukiwania zostanie automatycznie otwarty, filtrowane, aby tych miast, które zaczyna się od "col". 

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png) 

W tym momencie kursor jest nadal w polu wyszukiwania. Jeśli będziesz kontynuować wpisywanie więc wartość jest "colum", zawartość odnośników automatycznie dostosowuje się do odzwierciedlenia najnowszych wartości w formancie. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Nawet jeśli fokus jest nadal w formant wyszukiwania odnośników, można również użyć **Strzałka w górę** lub **Strzałka w dół** klawiszy, aby zaznaczyć wiersz, który chcesz zaznaczyć. Jeśli naciśniesz **Enter** zaznaczony wiersz zostanie zaznaczony w polu wyszukiwania, a wartość formantu zostanie zaktualizowana. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Pisanie w więcej niż identyfikatory
Podczas wprowadzania danych, to naturalne użytkownikom zmierzające do zidentyfikowania jednostki, takie jak nabywca lub Dostawca, pod względem nazwy, a nie identyfikator reprezentujący jednostkę. W obecnej wersji systemu Dynamics 365 dla operacji wyszukiwania wiele (ale nie wszystkie) teraz można wprowadzać dane kontekstowe. Tej zaawansowanej funkcji umożliwia użytkownikowi w formant wyszukiwania odnośników wpisz identyfikator lub odpowiadającej mu nazwy. 

Na przykład, rozważmy **konto odbiorcy** pól podczas tworzenia zamówienia sprzedaży. To pole zawiera **identyfikator konta** dla odbiorcy, ale użytkownik zazwyczaj wolą wprowadź **nazwa konta** zamiast **identyfikator konta** dla tego pola podczas tworzenia zamówienia sprzedaży, takie jak "Las hurtowni" zamiast "US-003."

Jeśli użytkownik rozpoczął do wprowadzania **identyfikator konta** w formancie wyszukiwania menu rozwijanego automatycznie otworzy zgodnie z opisem w poprzedniej sekcji i użytkownik zobaczy odnośnika, tak jak pokazano poniżej.

[![Wyszukiwanie kontekstowe po wprowadzeniu Identyfikatora konto klienta](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

Jednak użytkownik może teraz również wprowadzić na początku **nazwa konta** również. Jeśli to jest wykrywane, użytkownik zobaczy następujące wyszukiwania. Zawiadomienie jak **nazwa** kolumna jest przesuwana za pierwszej kolumny odnośnika i jak odnośnika jest sortowane i filtrowane w oparciu **nazwa** kolumny.

[![Wyszukiwanie kontekstowe po wprowadzeniu imienia i nazwiska odbiorcy](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Za pomocą nagłówków kolumn siatki dla bardziej zaawansowane filtrowanie i sortowanie
Rozszerzenia wyszukiwania omówionych w poprzednich rozdziałach znacznie poprawić zdolność użytkownika do przejść wierszy w oparciu o wyszukiwaniu "zaczyna się od" do wyszukiwania **ID** lub **nazwa** pól odnośnika. Jednak istnieją sytuacje, w których bardziej zaawansowane filtrowanie (lub sortowania) jest potrzebna do znalezienia prawidłowego wiersza. W takich sytuacjach użytkownik musi użyć opcji filtrowania i sortowania w nagłówkach kolumn siatki wewnątrz odnośnika. Rozważmy na przykład jeden pracownik wprowadzania wiersza zamówienia sprzedaży musi zlokalizować prawo "kabla" jako produkt. Wpisując "kabla" w **numer** formant nie jest przydatne, ponieważ istnieją żadne nazwy produktu, rozpoczynające się od "kabla". 

![emptyitemlookup](./media/emptyitemlookup.png) 

Zamiast tego użytkownik musi Wyczyść wartości formantu wyszukiwania, otwórz menu rozwijane wyszukiwania i filtrowania listy rozwijanej przy użyciu nagłówka kolumny siatki, tak jak pokazano poniżej. Myszy (lub dotykowego) użytkownik może po prostu (i kliknij) dowolny nagłówek kolumny, aby uzyskać dostęp do opcji filtrowania i sortowania dla tej kolumny. Dla użytkownika klawiatury, po prostu należy nacisnąć **Alt**+**w dół****strzałka** drugi raz, aby przenieść fokus do menu rozwijanego, po czym użytkownik może zakładkę, aby odpowiednie kolumny, a następnie naciśnij **Ctrl**+**G** otworzyć menu rozwijane nagłówka kolumny siatki. 

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png) 

Po zastosowano filtr (zobacz obraz poniżej), użytkownik może znaleźć i zaznacz wiersz w zwykły sposób. 

![filtereditemlookup](./media/filtereditemlookup.png)


