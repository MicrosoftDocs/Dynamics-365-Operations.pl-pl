---
title: Podstawowe pojęcia związane z zarządzaniem windykacjami
description: Tematy definiują podstawowe pojęcia dotyczące zarządzania windykacją.
author: JodiChristiansen
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 508723752ec7ae5f48e52c728b6ef526ec49e4e2
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2022
ms.locfileid: "8723031"
---
# <a name="collections-management-key-concepts"></a>Podstawowe pojęcia związane z zarządzaniem windykacjami

[!include [banner](../includes/banner.md)]

Przed rozpoczęciem konfigurowania lub pracy z windykacjami należy zapoznać się z następującymi pojęciami:

- Migawka wiekowania odbiorcy zawiera informacje o wiekowanym saldzie w określonym momencie.
- Pule klientów związanych z windykacjami pomagają w organizacji pracy.
- Agenci ds. windykacji mają własne pule klientów.
- Strony listy organizują odbiorców związanych z windykacjami, działania i sprawy.
- Wszystkie informacje o windykacji dotyczące danego odbiorcy znajdują się na jednej stronie, na której można podejmować wymagane działania.
- W jednym kroku można wykonać uchylenie, przywrócenie lub wycofanie odsetek.
- W jednym kroku można tworzyć transakcje odpisu.
- W jednym kroku można przetwarzać płatności przy niewystarczających funduszach.

W tym temacie opisano poszczególne pojęcia.

## <a name="customer-aging-snapshots"></a>Migawka wiekowania odbiorcy 

Migawka wiekowania zawiera obliczone wiekowane salda dla odbiorcy w określonym punkcie w czasie. Informacje migawki wiekowania pojawiają się na stronie listy **Wiekowane salda** i na stronie **Windykacja**. Aby można było przejrzeć informacje na stronach listy windykacji (**Wiekowanie sald**, **Działania windykacji** i **Sprawy dotyczące windykacji**), należy utworzyć migawkę wiekowania.

Dla każdego odbiorcy migawka wiekowania zawiera nagłówek i szczegółowe zapisy dotyczące każdego okresu wiekowania w definicji okresu wiekowania.

Nagłówek migawki wiekowania zawiera całkowitą kwotę do zapłaty, limit kredytu, dokument dostawy, kwotę, kwotę zamówienia sprzedaży, liczbę spornych transakcji i łączną kwotę spornych transakcji dla konta odbiorcy. W obliczeniach tych kwot uwzględniane są wszystkie transakcje dla danego odbiorcy. Całkowita kwota należności, limit kredytu, kwota dokumentu dostawy i kwota zamówienia sprzedaży są widoczne w polu informacji **Informacje o kredycie** na stronie **Windykacji**.

Dla każdego okresu wiekowania w definicji okresów wiekowania jest tworzony szczegółowy zapis migawki wiekowania. Każdy szczegółowy zapis migawki wiekowania zawiera identyfikator okresu wiekowania i łączną kwotę transakcji z datami w okresie wiekowania. Transakcje są przypisane do okresu wiekowania, np. 30 dni po terminie. Data jest powiązana z **Wiekowaniem począwszy od** daty, która została określona podczas tworzenia migawki wiekowania. Informacje pokazywane są na stronie listy **Wiekowane salda** w polu informacji **Wiekowane salda** i na stronie **Windykacja**.

## <a name="collections-customer-pools"></a> Pule klientów związanych z windykacjami

Pule klientów to kwerendy definiujące grupę rekordów odbiorców. Rekordy te mogą być używane do wyświetlania informacji dotyczących uwzględnionych kont odbiorców oraz do zarządzania windykacjami lub procesami wiekowania. Używaj pul klientów, aby filtrować informacje na stronie listy windykacji. Mogą również służyć do filtrowania kont odbiorców, które są uwzględniane podczas tworzenia migawki wiekowania.

## <a name="collections-agents"></a>Agenci ds. windykacji

Domyślnie użytkownicy mogą wyświetlać wszystkie informacje o odbiorcy na stronach listy windykacji. Rekordy agenta ds. windykacji służą do określania pul klientów, dostępnych do filtrowania informacji na stronach listy windykacji i na stronie **windykacji**.

Agenci ds. windykacji pracują z odbiorcami w celu upewnienia się, że płatności są inkasowane w terminie. Agentami ds. windykacji są pracownicy przypisani do użytkowników na stronie **ustawień użytkownika**.

## <a name="collections-list-pages"></a> Strony list windykacji 

Następujące strony listy pomagają organizować informacje o windykacji:

- **Wiekowane salda** — kolumny na stronie listy wyświetlają salda odbiorców i kwoty przeterminowane według okresów wiekowania. Te informacje są przechowywane w migawce wiekowania. Okresy wiekowania są określone przez używaną definicję okresu wiekowania. Definicja okresu wiekowania jest pobierana z puli klientów, o ile pula klientów została określona dla zapytania o pulę. Jeśli pula nie ma definicji okresu wiekowania, jest używana domyślna definicja okresu wiekowania określona na stronie **Parametry modułu rozrachunków z odbiorcami**. Jeśli nie określono domyślnego okresu wiekowania, używana jest pierwsza definicja okresu wiekowania ze strony **Definicje okresów wiekowania**.
- **Działania związane z windykacją** — kolumn na stronie listy wyświetla działania, które są określone jako działania związane z windykacją. Działania te są tworzone przy użyciu strony **Windykacji**. Użyj tych działań do śledzenia wykonywanej pracy powiązanej z windykacją.
- **Sprawy dotyczące windykacji** — kolumn na stronie listy wyświetla informacje dotyczące spraw, które należą do kategorii sprawy o typie sprawy dotyczącej **Windykacji**.

### <a name="aging-snapshots"></a>Migawki wiekowania

Aby wyświetlić informacje na stronach listy windykacji, należy utworzyć migawkę wiekowania. Informacje są wyświetlane tylko dla odbiorców, dla których została utworzona migawka wiekowania. Rekordy widoczne na stronie listy można dodatkowo filtrować w następujący sposób:

- Domyślnie użytkownik, ma dostęp do wszystkich odbiorców, którzy mają migawki wiekowania.
- Jeśli istnieje pula klientów, użytkownik musi być ustawiony jako agent ds. windykacji, aby korzystać z pul do filtrowania informacji na stronach listy windykacji. Informacje są ograniczone do klientów, którzy znajdują się w wybranej puli klientów.
- Jeśli użytkownik jest skonfigurowany jako agent ds., tylko pule, które są wybrane dla tego agenta, są dostępne na stronach listy windykacji. W przypadku włączenia dla danego agenta opcji **Zezwalaj agentowi na przeglądanie wszystkich pul klientów** na stronie **Agent ds. windykacji**, będzie miał dostęp do wszystkich pul.

## <a name="collections-page"></a> strona Windykacja

Strona **Windykacja** służy do wyświetlania, zarządzania i podejmowania działań względem informacji dotyczących windykacji oraz spraw danego odbiorcy.

W górnej sekcji strony są wyświetlane sprawy dla wybranego odbiorcy, sekcja środkowa pokazuje transakcje dla odbiorcy, a w dolnej sekcji są wyświetlane działania dla danego odbiorcy. Można utworzyć sprawy dotyczące windykacji, aby śledzić informacje o windykacjach dla jednej lub większej liczby transakcji lub działań. Informacje w sekcjach górnej i dolnej można filtrować według sprawy.

Pola informacji wyświetlają wiekowane salda i limit kredytu dla wybranego odbiorcy. Te informacje są przechowywane w migawce wiekowania. W razie potrzeby można aktualizować migawki wiekowania przy użyciu bieżących informacji.

Okienko akcji zawiera przyciski, które wyświetlają powiązane informacje dla wybranego odbiorcy, sprawy, transakcji lub działania. Można również wykonać typowe akcje, takie jak zmiana stanu windykacji transakcji, wysyłania wiadomości e-mail dzięki integracji ze swoim dostawcą poczty e-mail, zwrotu dla odbiorców, przetwarzania płatności przy niewystarczających funduszach i odpisy z nieściągalnych sald.

## <a name="waiving-reinstating-or-reversing-interest-and-fees"></a>Uchylanie, przywracanie lub wycofywanie odsetek lub opłat

Można uchylić, przywróć lub wycofać pełne noty odsetkowe, opłaty i odsetki transakcji, które są częścią not odsetkowych. Można to zrobić na karcie **Windykacja** w okienku akcji na stronie listy **wszystkich odbiorców**, klikając **notę odsetkową**, **odsetki transakcji** lub **opłaty**.

Te zmiany wpływają tylko na noty odsetkowe oraz odsetki i opłaty, których dotyczą. Aby uzyskać informacje dotyczące sposobu wypisywania wszystkich opłat, które jest należny od odbiorcy, zapoznaj się z sekcją [Tworzenie transakcji odpisu](#creating-write-off-transactions) w tym temacie.

Aby uzyskać więcej informacji, zobacz Tworzenie kodu odsetek z zakresem i Przetwarzanie odsetek.

## <a name="creating-write-off-transactions"></a>Tworzenie transakcji odpisu

Można odpisać nieściągalne zadłużenie, wybierając opcję **Odpis** na stronie **Windykacje** i strony listy windykacji.

Gdy odpisujesz transakcje dla odbiorcy, wszystkie transakcje dla tego odbiorcy są automatycznie oznaczane do rozliczenia. Odpisywana kwota zależy od kwoty netto oznaczonych transakcji. Transakcja odpisu jest tworzona w arkuszu finansowym i może zawierać maksymalnie trzy typy wierszy arkusza:

- Pierwszy typ wiersza arkusza zawiera wpis odpisu odbiorcy. Jeśli zaznaczone transakcje zawierają wiele kombinacji kodów waluty, wymiarów i profili księgowania, tworzony jest osobny wiersz arkusza dla każdej kombinacji.
- Drugi typ wiersza arkusza zawiera wpis odpisu księgi głównej. Jeśli zaznaczone transakcje zawierają wiele kombinacji kodów waluty, wymiarów i profili księgowania, tworzony jest osobny wiersz arkusza dla każdej kombinacji.
- Trzeci typ wiersza arkusza zawiera informacje o odpisie księgi głównej dotyczące podatków. Ten wiersz arkusza jest tworzony tylko wtedy, gdy wybrano przełącznik **Oddziel podatek** na stronie **parametrów rozrachunków z odbiorcami**. Jeśli zaznaczone transakcje zawierają wiele kombinacji kont płatności podatku, wymiarów i kodów podatku, tworzony jest osobny wiersz arkusza dla każdej kombinacji. Transakcja odpisu jest tworzona w walucie transakcji. Aby uzyskać więcej informacji, zobacz Tworzenie arkusza odpisów dla odbiorcy.

## <a name="process-nsf-payments"></a>Proces dotyczący płatności przy niewystarczających funduszach

Klikając **płatności przy niewystarczających funduszach** na stronie **Windykacje** można przetwarzać płatności przy niewystarczających funduszach. Po wybraniu tego przycisku nastąpi anulowanie płatności. Jeśli do odbiorcy ma być stosowana opłata za niewystarczające fundusze, w arkuszu płatności jest tworzona transakcja opłat. Kwota opłaty jest oparta na ustawieniach dla automatycznych opłat. Automatyczne opłaty, które są stosowane do płatności przy niewystarczających funduszach, są określone przez grupę opłat wybraną na stronie **Konta bankowe** dla danego konta bankowego.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Ustawienia parametrów modułu Zarządzanie kredytami odbiorcy](./cm-credit-mgmt-setup.md)

[Ustawienia informacji modułu Zarządzanie kredytami odbiorcy](./cm-setup-information.md)

[Dodaj informacje dotyczące zarządzania kredytem odbiorcy](./cm-add-credit-mgmt-information-customer.md)

[Grupy kredytowe odbiorcy](./cm-customer-credit-groups.md)

[Korekty limitu kredytu odbiorcy](./cm-credit-limit-adjustments.md)

[Obsługa wstrzymania kredytu zamówień sprzedaży](./cm-sales-order-credit-holds.md)

[Zadania okresowe zarządzania kredytami odbiorcy](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
