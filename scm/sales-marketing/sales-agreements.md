---
title: "Umowy sprzedaży"
description: "Ten artykuł zawiera informacje o umowach sprzedaży. Umowa sprzedaży jest kontraktem, który zobowiązuje odbiorcę do zakupu produktów w określonej ilości lub za określoną kwotę w ustalonym czasie w zamian za specjalne ceny i rabaty."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesAgreementListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 9554
ms.assetid: c5d55c8d-99f2-44f9-a897-5b0dee85fc81
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 4eaa4fef65fb310524f25d052aeefb58c5f20fe4
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Umowy sprzedaży
<a id="sales-agreements" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o umowach sprzedaży. Umowa sprzedaży jest kontraktem, który zobowiązuje odbiorcę do zakupu produktów w określonej ilości lub za określoną kwotę w ustalonym czasie w zamian za specjalne ceny i rabaty.

Umowa sprzedaży jest kontraktem, który zobowiązuje odbiorcę do zakupu produktu w pewnej ilości lub kwocie w pewnym okresie czasu w zamian za specjalne ceny i rabaty, oraz z zachowaniem wszelki warunków specjalnych, takich jak warunki płatności i dostawy. Ceny i rabaty dla umowy zakupu zastępują ceny i rabaty, które są określone w jakichkolwiek istniejących umowach handlowych.  

Okres ważności wiersza umowy sprzedaży jest definiowany na postawie pól **Data obowiązywania** i **Data ważności** w wierszu umowy. Zamówienie sprzedaży odbiorcy spełnia warunki umowy, jeśli żądana data wysyłki zamówienia mieści się w okresie ważności. Wszystkie wiersze zamówienia sprzedaży, które są połączone z umową sprzedaży, przyczyniają się do realizacji tej umowy sprzedaży.  

Zamówienie sprzedaży można utworzyć bezpośrednio z umowy sprzedaży za pomocą działania **Zwolnij zamówienie**. Ewentualnie można wybrać obowiązującą umowę sprzedaży podczas przyjmowania zamówień (zobacz sekcję „Stosowanie umów sprzedaży w procesie zamawiania” w tym artykule).  

**Uwaga:** W poprzednich wersjach umowy sprzedaży były nazywane zbiorczymi zamówieniami sprzedaży.

## Typy zobowiązania
<a id="commitment-types" class="xliff"></a>
Każdy wiersz umowy sprzedaży jest zobowiązaniem do zakupu czegoś. Ogólnie są dwie kategorie zobowiązania:

-   **Zobowiązanie co do wartości**— odbiorca akceptuje zakup produktów za określoną kwotę.
-   **Zobowiązanie co do ilości**— odbiorca akceptuje zakup określonej ilości produktów.

Oprócz tego umowa może zobowiązywać odbiorcę do kupna określonego produktu lub produktów z danej kategorii. Łącząc te dwa czynniki (wartości i ilości oraz określone produkty i kategorie produktów), otrzymujemy cztery rodzaje zobowiązań:

-   **Zobowiązanie co do ilości produktu** — odbiorca akceptuje zakup określonej ilości produktów. Wiersze, w których jest używany ten typ zobowiązania, są definiowane za pomocą kodu towaru i ustalonej ilości oraz jednostki. Pole **Kwota** nie jest dostępne.
-   **Zobowiązanie co do wartości produktu** — odbiorca akceptuje zakup produktów za określoną kwotę. Wiersze, w których jest używany ten typ zobowiązania, są definiowane za pomocą kodu towaru oraz ustalonej kwoty. Pola **Ilość** i **Jednostka** nie są dostępne.
-   **Zobowiązanie co do wartości w ramach kategorii produktu** — odbiorca akceptuje zakup produktów z określonej kategorii sprzedaży i za określoną kwotę. Wiersze, w których jest używany ten typ zobowiązania, są definiowane według kategorii sprzedaży w hierarchii kategorii sprzedaży oraz kwoty. Pola **Ilość** i **Jednostka** nie są dostępne.
-   **Zobowiązanie co do wartości** — odbiorca akceptuje zakup produktów z dowolnej kategorii zaopatrzenia za określoną kwotę. Pola **Ilość** i **Jednostka** nie są dostępne.

Wiersze w tej umowie sprzedaży mogą mieć różne typy zobowiązań.

## Warunki cenowe umów sprzedaży
<a id="pricing-terms-for-sales-agreements" class="xliff"></a>
Warunki cenowe mogą się różnić w zależności od typu zobowiązania. Na podstawie zamówienia sprzedaży, który jest powiązane z umową sprzedaży, warunki cenowe z tej umowy sprzedaży zastępują wszelkie inne warunki cenowe wynikające z umów handlowych. W poniższej tabeli opisano pola związane z cenami, na które ma wpływ każdy typ zobowiązania. „Tak” oznacza, że pole może być zaktualizowane w wierszu zamówienia.

| Typ zobowiązania                   | Cena jednostkowa | Jednostka cenowa | Procent rabatu | Kwota rabatu gotówkowego |
|-----------------------------------|------------|------------|------------------|----------------------|
| Zobowiązanie co do ilości produktu       | Tak        | Tak        | Tak              | Tak                  |
| Zobowiązanie co do wartości produktu          |            |            | Tak              |                      |
| Zobowiązanie co do wartości w ramach kategorii produktu |            |            | Tak              |                      |
| Zobowiązanie co do wartości                  |            |            | Tak              |                      |

## Zasady dotyczące umów sprzedaży
<a id="policies-for-sales-agreements" class="xliff"></a>
Następujące zasady mają wpływ na sposób działania łącza między zobowiązaniem umowy sprzedaży i odpowiadającymi mu wierszami zamówienia sprzedaży:

-   **Wymuszono maks** — Łączna ilość lub kwota dla wszystkich wierszy zamówienia nie może przekraczać ilości lub kwoty określonej w powiązanym zobowiązaniu.
-   **Cena i rabat są stałe** — Cena w wierszu zamówienia i cena na powiązanym zobowiązaniu nie mogą się różnić. Jeśli w wierszu zamówienia zostanie zmieniona cena, łącze do zobowiązania zostanie przerwane. Jeśli łącze do zobowiązania zostanie przerwane, wiersz zamówienia nie będzie brał udziału w wypełnieniu zobowiązania.
-   **Kwota minimalna zwolnienia** i **Kwota maksymalna zwolnienia** –jeśli kwota jest określona, wyświetlany jest komunikat po wprowadzeniu zmian do wiersza zamówienia, które powodują, że wiersz zamówienia jest inny niż zobowiązanie powiązane.

## Obliczenia realizacji umów sprzedaży
<a id="fulfillment-calculations-for-sales-agreements" class="xliff"></a>
Na karcie **Realizacja** na skróconej karcie **Szczegóły wiersza** na stronie **Umowy sprzedaży** pokazują ilości i kwoty realizacji.  

W obszarze **Realizacja** wyświetlane są łączne ilości oraz kwoty dla wszystkich wierszy zamówienia, które są połączone z określoną umową sprzedaży. Można także wyświetlać pozostałą kwotę lub ilość, która jest wymagana do wypełnienia zobowiązania.  

W obszarze **Umowa** można wyświetlić ilości i kwoty z określonej umowy sprzedaży. Te ilości i kwoty są to łączne ilości i kwoty, do których się zobowiązano.

## Potwierdzenia i historia wersji umów sprzedaży
<a id="confirmations-and-version-history-for-sales-agreements" class="xliff"></a>
Gdy potwierdzono umowę sprzedaży, bieżąca wersja umowy sprzedaży jest przechowywana w tabeli historii. Jeśli zmieni się umowę sprzedaży, można potwierdzić ją ponownie, aby zachować inną wersję umowy sprzedaży w historii.  

Jeśli nie potwierdzi się umowy sprzedaży, można nadal użyć jej do tworzenia zamówień sprzedaży. Jednak informacje dotyczące historii umowy sprzedaży nie będą przechowywane.  

Można wyświetlić podgląd lub wydrukować wszystkie poprawki potwierdzeń. Następnie można udostępnić zmiany odbiorcy w celu uzyskania zatwierdzenia.

## Stosowanie umów sprzedaży w trakcie procesu zamawiania
<a id="applying-sales-agreements-during-the-ordering-process" class="xliff"></a>
Jeśli nie zwolnisz zamówień sprzedaży bezpośrednio dla umów sprzedaży, można połączyć umowę sprzedaży z zamówieniem w trakcie wprowadzania zamówienia. Podczas tworzenia nowego zamówienia sprzedaży i wybierz umowę sprzedaży, warunki umowy, np. warunki płatności, dostawy i adres dostawy, są stosowane do nagłówka zamówienia, i tworzone jest połączenie między umową i zamówieniem. Następnie w wierszach zamówienia, kiedy można wybrać produkty i kategorie określone w umowie sprzedaży, ceny i rabaty są kopiowane z tej umowy. To samo zamówienie sprzedaży może zawierać zarówno wiersze, które nie są powiązane z umową sprzedaży, jak i wiersze, które mają zobowiązania dla umowy sprzedaży.

## Modyfikowanie zamówień sprzedaży, które są połączone z umowami sprzedaży
<a id="modifying-sales-orders-that-are-linked-to-sales-agreements" class="xliff"></a>
Po utworzeniu (zwolnieniu) zamówienia sprzedaży z umowy sprzedaży niektóre pola w wierszach tego zamówienia sprzedaży można modyfikować tylko po usunięciu łącza do skojarzonych wierszy umowy sprzedaży. W poniższej tabeli wymieniono niektóre z tych pól.

| Pole                                                             | Opis                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Żądana data wysyłki                                               | Jeśli zmienisz żądaną datę wysyłki na datę wcześniejszą niż **Data obowiązywania** określona w wierszu umowy sprzedaży, trzeba usunąć łącze do wiersza umowy sprzedaży, aby można było zapisać zmienioną datę wysyłki. Jeśli zmienisz żądaną datę wysyłki na datę późniejszą niż **Data ważności** określona w wierszu umowy sprzedaży, trzeba usunąć łącze do wiersza umowy sprzedaży, aby można było zapisać zmienioną datę wysyłki. |
| Kwota CurrencyDiscount, percentDiscountUnit, pricePrice, unitNet | Jeśli zmienisz wartość w którymkolwiek z tych pól i jeśli pole wyboru **Cena i rabat są stałe** jest zaznaczone w wierszu skojarzonej umowy sprzedaży, wyświetlane jest pole umożliwiające zapisanie zmian. Kliknij opcję **Tak**, aby usunąć łącze do wiersza umowy sprzedaży i ponownie obliczyć cenę. Kliknij opcję **Nie**, aby usunąć łącze do wiersza umowy sprzedaży bez przeliczania ceny.                                                                   |
| Kwota netto                                                        | Jeśli określisz kwotę, która przewyższa kwotę określoną w wierszu umowy sprzedaży, i jeśli pole **Wymuszono maks.** jest zaznaczone, wyświetlany jest monit o zapisanie zmienionej kwoty. Kliknij opcję **Tak**, aby usunąć łącze do wiersza umowy sprzedaży i ponownie obliczyć cenę. Kliknij opcję **Nie**, aby usunąć łącze do wiersza umowy sprzedaży bez przeliczania ceny.                                                                 |
| Ilość                                                          | Jeśli określisz ilość, która przewyższa ilość określoną w wierszu umowy sprzedaży, i jeśli pole **Wymuszono maks.** jest zaznaczone, wyświetlany jest monit o zapisanie zmienionej ilości. Kliknij opcję **Tak**, aby usunąć łącze do wiersza umowy sprzedaży i ponownie obliczyć cenę. Kliknij opcję **Nie**, aby usunąć łącze do wiersza umowy sprzedaży bez przeliczania ceny.                                                            |

## Zwracanie towaru zamówionego z umowy sprzedaży
<a id="returning-an-item-that-was-ordered-from-a-sales-agreement" class="xliff"></a>
W przypadku zwrotu przez odbiorcę produktu, który został zamówiony na podstawie umowy sprzedaży, program Microsoft Dynamics 365 for Finance and Operations może odnaleźć powiązane zobowiązanie w umowie sprzedaży i automatycznie je zaktualizować, uwzględniając zmianę kwoty lub ilości. Tworząc zamówienie zwrotu oparte na oryginalnym zamówieniu sprzedaży, które jest połączone z umową sprzedaży, można ustalić stosunek między zobowiązaniem z umowy sprzedaży, wierszem zamówienia sprzedaży i fakturą zamówienia zwrotu.  

Jeśli nie chcesz, aby ilość zwróconych towarów była odejmowana ze zobowiązania z umowy sprzedaży, możesz użyć formantu **Usuwanie łącza** na stronie **Zwróć zamówienie**, aby usunąć łącze między zamówieniem zwrotu i zobowiązaniem z umowy sprzedaży. Jeśli później trzeba ponownie utworzyć łącze, kliknij przycisk **Utwórz łącze**.  

**Uwaga:** zamówienie zwrotu można łączyć tylko z jedną umową sprzedaży. Jeśli odbiorca zwraca więcej niż jeden produkt, który zamówił z więcej niż jednej umowy sprzedaży, należy utworzyć nowe zamówienie zwrotu dla każdego produktu i łącze do odpowiedniej umowy sprzedaży.

## Automatyczne wyszukiwanie umów sprzedaży
<a id="automatic-search-for-sales-agreements" class="xliff"></a>
W pewnych sytuacjach, kiedy zamówienia sprzedaży są tworzone bezpośrednio, np. gdy tworzona jest faktura korygująca lub międzyfirmowe zamówienia sprzedaży, można określi, czy program Microsoft Dynamics 365 for Finance and Operations ma automatycznie wyszukiwać odnośne umowy sprzedaży.

## Wymiary finansowe umów sprzedaży
<a id="financial-dimensions-on-sales-agreements" class="xliff"></a>
Wymiary finansowe można skopiować do nagłówków dokumentu lub pojedynczych wierszy umowy sprzedaży. W każdej chwili można zmienić wymiary w nagłówku umowy lub wiersza umowy. W takim przypadku wymiary są automatycznie kopiowane do nagłówka zwolnienia lub wiersza zwolnienia na zleceniach zwolnienia.




