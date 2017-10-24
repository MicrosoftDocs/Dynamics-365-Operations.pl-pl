---
title: Kredyty i windykacja w rozrachunkach z odbiorcami
description: "Zarządzanie informacjami dotyczącymi windykacji w module Rozrachunki z odbiorcami odbywa się w jednym centralnym widoku przy użyciu strony Windykacja dostępnej w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Kierownicy ds. kredytów i windykacji mogą używać tego centralnego widoku do zarządzania windykacją. Agenci ds. windykacji mogą rozpocząć proces windykacji na podstawie list odbiorców, które są generowane przy użyciu wstępnie zdefiniowanych kryteriów windykacji, lub ze strony Windykacja."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 62f659d6e4529adce10e6eb2699dfc84a7329143
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="credit-and-collections-in-accounts-receivable"></a>Kredyty i windykacja w rozrachunkach z odbiorcami

[!include[banner](../includes/banner.md)]


Zarządzanie informacjami dotyczącymi windykacji w module Rozrachunki z odbiorcami odbywa się w jednym centralnym widoku przy użyciu strony Windykacja dostępnej w programie Finance and Operations. Kierownicy ds. kredytów i windykacji mogą używać tego centralnego widoku do zarządzania windykacją. Agenci ds. windykacji mogą rozpocząć proces windykacji na podstawie list odbiorców, które są generowane przy użyciu wstępnie zdefiniowanych kryteriów windykacji, lub ze strony Windykacja.

Przed rozpoczęciem konfigurowania lub pracy z windykacjami należy zapoznać się z następującymi pojęciami:
-   Migawka wiekowania odbiorcy zawiera informacje o wiekowanym saldzie w określonym momencie
-   Pule klientów związanych z windykacjami pomagają w organizacji pracy
-   Agenci ds. windykacji mają własne pule klientów
-   Strony listy organizują odbiorców związanych z windykacjami, działania i sprawy
-   Wszystkie informacje o windykacji dotyczące danego odbiorcy znajdują się na jednej stronie, na której można podejmować wymagane działania.
-   W jednym kroku można wykonać uchylenie, przywrócenie lub wycofanie odsetek
-   W jednym kroku można tworzyć transakcje odpisu
-   W jednym kroku można przetwarzać płatności przy niewystarczających funduszach.

Poniżej opisano poszczególne pojęcia.

## <a name="customer-aging-snapshots"></a>Migawka wiekowania odbiorcy 
Migawka wiekowania zawiera obliczone wiekowane salda dla odbiorcy w jednym punkcie w czasie. Informacje migawki wiekowania pojawiają się na stronie listy Wiekowane salda i na stronie Windykacja. Aby wyświetlić informacje na stronach listy windykacji, należy utworzyć migawkę wiekowania. 

Dla każdego odbiorcy migawka wiekowania zawiera nagłówek i szczegółowe zapisy dotyczące każdego okresu wiekowania w definicji okresu wiekowania. 

Nagłówek migawki wiekowania zawiera całkowitą kwotę do zapłaty, limit kredytu, dokument dostawy, kwotę, kwotę zamówienia sprzedaży, liczbę spornych transakcji i łączną kwotę spornych transakcji dla konta odbiorcy. W obliczeniach tych kwot uwzględniane są wszystkie transakcje dla danego odbiorcy. Całkowita kwota należności, limit kredytu, kwota dokumentu dostawy i kwota zamówienia sprzedaży są widoczne w polu informacji Informacje o kredycie na stronie windykacji. 

Dla każdego okresu wiekowania w definicji okresów wiekowania jest tworzony szczegółowy zapis migawki wiekowania. Każdy szczegółowy zapis migawki wiekowania zawiera identyfikator okresu wiekowania i łączną kwotę transakcji z datami w okresie wiekowania. Transakcje są przypisane do okresu wiekowania, np. 30 dni po terminie. Data jest powiązana z wiekowaniem począwszy od daty, która została określona podczas tworzenia migawki wiekowania. Informacje migawki wiekowania pojawiają się w polu informacji Wiekowane salda i na stronie Windykacja.

## <a name="collections-customer-pools"></a> Pule klientów związanych z windykacjami
Pule odbiorców są kwerendami definiującymi grupę rekordów odbiorców, które mogą być wyświetlane i zarządzane dla windykacji lub procesów wiekowania. Używaj pul klientów, aby filtrować informacje na stronach listy Wiekowane salda, Działania związane z windykacją i sprawy związane z windykacją. Pule klientów mogą również służyć do filtrowania kont odbiorców, które są uwzględniane podczas tworzenia migawki wiekowania.

## <a name="collections-agents"></a>Agenci ds. windykacji
Domyślnie użytkownicy programu Microsoft Dynamics 365 for Finance and Operations mogą wyświetlać wszystkie informacje o odbiorcy na stronach listy windykacji. Rekordy agenta ds. windykacji służą do określania pul klientów, dostępnych do filtrowania informacji na stronach listy windykacji i na stronie windykacji. 

Agent ds. windykacji jest osobą, która współpracuje z odbiorcami w celu upewnienia się, że płatności są inkasowane w terminie. W programie Finance and Operations agentami ds. windykacji są pracownicy przypisani do użytkowników na stronie ustawień użytkownika.

## <a name="collections-list-pages"></a> Strony list windykacji 
Następujące strony listy pomagają organizować informacje o windykacji.
-   Wiekowane salda — kolumny na stronie listy wyświetlają salda odbiorców i kwoty przeterminowane według okresów wiekowania. Te informacje są przechowywane w migawce wiekowania. Okresy wiekowania są określone przez używaną definicję okresu wiekowania. Definicja okresu wiekowania jest pobierana z puli klientów, o ile została określona dla zapytania o pulę. Jeśli pula nie ma definicji okresu wiekowania, jest używana domyślna definicja okresu wiekowania określona na stronie Parametry modułu rozrachunków z odbiorcami. Jeśli nie określono domyślnego okresu wiekowania, używana jest pierwsza definicja okresu wiekowania ze strony Definicje okresów wiekowania.
-   Działania związane z windykacją — kolumn na stronie listy wyświetla działania, które są określone jako działania związane z windykacją. Działania te są tworzone przy użyciu strony windykacji. Użyj tych działań do śledzenia wykonywanej pracy powiązanej z windykacją.
-   Sprawy dotyczące windykacji — kolumn na stronie listy wyświetla informacje dotyczące spraw, które mają kategorię sprawy o typie sprawy dotyczącej windykacji.

> [!NOTE]
> Aby wyświetlić informacje na stronach listy windykacji, należy utworzyć migawkę wiekowania. Informacje są wyświetlane tylko dla tych klientów, dla których została utworzona migawka wiekowania. Rekordy, które zostaną wyświetlone na stronie listy można dodatkowo filtrować, w następujący sposób:
<li>Domyślnie użytkownik programu Finance and Operations ma dostęp do wszystkich odbiorców, którzy mają migawki wiekowania.</li>
<li>Jeśli istnieje pula klientów, użytkownik musi być ustawiony jako agent ds. windykacji, aby korzystać z pul do filtrowania informacji na stronach listy windykacji. Informacje są ograniczone do klientów, którzy znajdują się w wybranej puli klientów.</li>
<li>Jeśli użytkownik jest skonfigurowany jako agent ds., tylko pule, które są wybrane dla tego agenta, są dostępne na stronie listy. W przypadku włączenia dla danego agenta opcji Zezwalaj agentowi na przeglądanie wszystkich pul klientów na stronie Agent ds. windykacji, będzie miał dostęp do wszystkich pul.</li>


## <a name="collections-page"></a> strona Windykacja
Strona Windykacja służy do wyświetlania, zarządzania i podejmowania działań względem informacji dotyczących windykacji oraz spraw danego odbiorcy. 

Górne okienko wyświetla sprawy wybranego odbiorcy. Środkowe okienko pokazuje transakcje odbiorcy. Dolne okienko służy do wyświetlania działań dla odbiorcy. Można utworzyć sprawy dotyczące windykacji, aby śledzić informacje o windykacjach dla jednej lub większej liczby transakcji lub działań. Informacje w okienkach górnym i dolnym można filtrować według sprawy. 

Pola informacji wyświetlają wiekowane salda i limit kredytu dla wybranego odbiorcy. Te informacje są przechowywane w migawce wiekowania. W razie potrzeby można aktualizować migawki wiekowania przy użyciu bieżących informacji. 

Okienko akcji zawiera przyciski, które wyświetlają powiązane informacje dla wybranego odbiorcy, sprawy, transakcji lub działania. Można również wykonać typowe akcje, takie jak zmiana stanu windykacji transakcji, wysyłania korespondencji e-mail dzięki integracji ze swoim dostawcą poczty e-mail, zwrotu dla odbiorców, przetwarzania płatności przy niewystarczających funduszach i odpisy z nieściągalnych sald.

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a> Uchylanie, przywracanie lub wycofywanie odsetek lub opłat 
Można uchylić, przywróć lub wycofać pełne noty odsetkowe, opłaty i odsetki transakcji, które są częścią not odsetkowych. Można to zrobić na karcie Windykacja w okienku akcji na stronie listy wszystkich odbiorców, klikając notę odsetkową, odsetki transakcji lub opłaty. 

Te zmiany wpływają tylko na noty odsetkowe oraz odsetki i opłaty, których dotyczą. Należy wykonać kroki w sekcji „Tworzenie transakcji odpisu w jednym kroku”, aby odpisać łączną kwotę zobowiązań odbiorcy.

Aby uzyskać więcej informacji, zobacz [Tworzenie kodu odsetek z zakresem](tasks/create-interest-code-range.md) i [Przetwarzanie odsetek](tasks/process-interest.md). 

## <a name="create-writeoff-transactions"></a>Tworzenie transakcji odpisu
Można odpisać nieściągalne długi, klikając Odpisz w formularzu Windykacja i na stronach listy Wiekowane salda, Odbiorcy i Otwarte faktury dla odbiorców. 

Gdy odpisujesz transakcje dla odbiorcy, wszystkie transakcje dla tego odbiorcy są automatycznie oznaczane do rozliczenia. Odpisywana kwota zależy od kwoty netto oznaczonych transakcji. Transakcja odpisu jest tworzona w arkuszu finansowym i może zawierać maksymalnie trzy typy wierszy arkusza.

-   Pierwszy typ wiersza arkusza zawiera wpis odpisu odbiorcy. Jeśli zaznaczone transakcje zawierają wiele kombinacji kodu waluty, wymiarów i profili księgowania, tworzony jest osobny wiersz arkusza dla każdej kombinacji.
-   Drugi typ wiersza arkusza zawiera wpis odpisu księgi głównej. Jeśli zaznaczone transakcje zawierają wiele kombinacji kodu waluty, wymiarów i profili księgowania, tworzony jest osobny wiersz arkusza dla każdej kombinacji.
-   Trzeci typ wiersza arkusza zawiera informacje o odpisie księgi głównej dotyczące podatków. Ten wiersz arkusza jest tworzony tylko wtedy, gdy wybrano przełącznik Oddziel podatek na stronie parametrów rozrachunków z odbiorcami. Jeśli zaznaczone transakcje zawierają wiele kombinacji konta płatności podatku, wymiarów i kodu podatku, tworzony jest osobny wiersz arkusza dla każdej kombinacji.

Transakcja odpisu jest tworzona w walucie transakcji.

Aby uzyskać więcej informacji, zobacz [Tworzenie arkusza odpisów dla odbiorcy](tasks/create-write-off-journal-customer.md).

<a name="process-not-sufficient-funds-nsf-payments"></a>Przetwarzanie płatności przy niewystarczających funduszach  
--------------------------------------------

Klikając płatności przy niewystarczających funduszach na stronie kolekcje można przetwarzać płatności przy niewystarczających funduszach. Po kliknięciu tego przycisku nastąpi anulowanie płatności. Jeśli do odbiorcy ma być stosowana opłata za niewystarczające fundusze, w arkuszu płatności jest tworzona transakcja opłat. Kwota opłaty jest oparta na ustawieniach dla automatycznych opłat. Automatyczne opłaty, które są stosowane do płatności przy niewystarczających funduszach, są określone przez grupę opłat wybraną na stronie Konta bankowe dla danego konta bankowego.






