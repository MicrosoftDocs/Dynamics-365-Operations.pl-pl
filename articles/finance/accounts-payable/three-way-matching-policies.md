---
title: Trzyelementowe zasady uzgadniania
description: Ten temat zawiera przykłady uzgadniania trzyelementowego.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 2761
ms.assetid: 70f3cb1a-18b7-4474-95ec-28b2410dd8f8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9c177f7a7b713e7b8490b718650daafeca0e937
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189391"
---
# <a name="three-way-matching-policies"></a>Trzyelementowe zasady uzgadniania

[!include [banner](../includes/banner.md)]

Ten temat zawiera przykłady uzgadniania trzyelementowego.

<a name="example-three-way-matching-for-items"></a>Przykład: Trzyelementowe uzgadniania dla towarów
-------------------------------------

**Podsumowanie:** Ken jest kontrolerem w centrali firmy Fabrikam. Chce, aby wszystkie faktury od dostawców oparte na zamówieniach zakupu były dopasowane do wierszy zamówień zakupu (uzgadnianie dwuelementowe). Dla zakupu towarów, które będą używane jako środki trwałe, faktura powinna być uzgodniona zarówno z wierszami zamówienia zakupu, jak i wierszami dokumentu przyjęcia towarów (uzgodnienie trzyelementowe).

Fabrikam ma wiele podmiotów prawnych i pracowników w różnych zakątkach świata. W miarę wzrostu liczby transakcji, rosną też rozbieżności między przyjęciami a fakturami. Skutkiem są odpisy środków trwałych. Faktury od dostawców są płacone, ale proces nie obejmuje identyfikacji rozbieżności, gdy ilość odebranych towarów jest mniejsza od ilości na zamówieniu lub gdy towary nie zostaną odebrane wcale. Rosną też wydatki, bo pracownicy nadal potrzebują narzędzi i innych materiałów do wykonywania swoich obowiązków. Ken chce upewnić się, że dostawcy wysyłają produkty, które zostały zamówione, i że produkty są odbierane przez pracowników firmy Fabrikam. Z tego względu Ken wymaga dwuelementowego i trzyelementowego uzgadniania we wszystkich podmiotach prawnych organizacji. Uzgadnianie faktur pomaga w zapewnieniu, że problemy związane ze zniknięciem lub nieotrzymaniem towarów można śledzić i rozwiązywać. 

Zasady uzgadniania faktur w tym przykładzie ułatwiają pracę osobom na następujących stanowiskach spełniać te cele:

-   Ken jest kontrolerem w firmie Fabrikam. Może on pomóc pracownikom swojej firmy w identyfikowaniu i rozwiązywaniu problemów związanych z zamawianiem, odbieraniem zamówień i płaceniem za towary lub usługi od dostawców.
-   Phyllis i April są menedżerami ds. księgowości w dziale rozrachunków z dostawcami dla oddziału firmy Fabrikam w USA. Mogą oni wymuszać stosowanie zasad korporacyjnych i zapewniać, że faktury są płacone dopiero po ich uzgodnieniu z zamówieniem zakupu i odebraniem towarów lub usług.
-   Tony jest kierownikiem produkcji w amerykańskim oddziale Fabrikam. On i inni pracownicy działu produkcji muszą upewnić się, że towary zostały odebrane zgodnie z zamówieniem od dostawcy, tak aby inni pracownicy mieli materiały potrzebne do wykonywania ich obowiązków.

### <a name="prerequisites"></a>Wymagania wstępne

-   Ken ustawia zasadę uzgadniania na poziomie firmy na uzgadnianie trzyelementowe.
-   W pola Automatycznie aktualizuj stan uzgodnienia nagłówka na poziomie firmy Ken wybiera wartość Tak.
-   Wolu Dopasuj ceny całkowite dla firmy Ken wybiera wartość Procent i wpisuje 15% jako wartość procentową rozbieżności.
-   Ken ustawia uzgodnienie trzyelementowe dla zasady uzgadniania dla pozycji 1500 — Milicron Obrabiarka na poziomie pozycji. Ta pozycja jest pozycją środka trwałego używanego do produkcji w firmie Fabrikam. Faktury dla tej pozycji są uzgadnianie z wierszami zamówienia zakupu dla cen i z dokumentami przyjęcia produktów dla ilości.
-   Tony wpisuje zapotrzebowanie na pięć obrabiarek Milicron. Alicia, pracowniczka działu zamówień zakupów w firmie Fabrikam, wysyła zamówienie zakupu do firmy o nazwie Contoso na dostawę towarów.

    | Numer pozycji                 | Ilość | Cena jednostkowa | Kwota netto | Kod opłat        | Wartość opłat |
    |-----------------------------|----------|------------|------------|---------------------|---------------|
    | 1500 — Milicron Obrabiarka | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych        | 8000,00   | 40 000,00  | Wysyłka i obsługa | 3000,00      |

-   Arnie, pracownik działu rozrachunki z odbiorcami w Contoso, sprawdza wysyłki w danym tygodniu. Wybiera transakcje wysyłki do zafakturowania dla Fabrikam za dostawę obrabiarek Milicron. Arnie uwzględnia opłatę za wysyłkę i obsługę. Fabrikam uzna, że ta opłata jest częścią kosztów środka trwałego.

### <a name="scenario"></a>Scenariusz

1.  Sammy, pracownik działu przyjęć w firmie Fabrikam, odbiera całkowitą liczbę maszyn, które zostały wysyłane z firmy Contoso. Wprowadza ilość 5 w dokumencie przyjęcia produktów. Ponieważ zamówienie zakupu zostało całkowicie otrzymane, stan zamówienia zakupu zmienia się na Otrzymane.
2.  April, koordynatorka rozrachunków z dostawcami w firmie Fabrikam, wprowadza i sprawdza fakturę przesyłaną przez firmę Contoso. Sprawdza poprawność następujących informacji:
    -   Dla towarów, które wymagają uzgodnienia trzyelementowego, ilość w wierszu faktury odpowiada ilości, która została przyjęta. Przyjęta ilość jest wskazana w dokumencie przyjęcia produktów, który jest uzgodniony z fakturą.
    -   W przypadku towarów wymagających dwuelementowego lub trzyelementowego uzgadniania ceny w wierszu faktury są w granicach tolerancji zdefiniowanych w Microsoft Dynamics 365 Finance. Obejmuje to następujące typy uzgadniania cen:
        -   Uzgadnianie ceny jednostkowej netto — cena jednostkowa netto w wierszu faktury odpowiada cenie jednostkowej w wierszu zamówienia zakupu w ramach wartości procentowej rozbieżności. W tym przykładzie tolerancja ceny jednostkowej netto to +8%.
        -   Uzgodnienie cen całkowitych — kwota netto w wierszu faktury odpowiada kwocie netto w wierszu zamówienia zakupu w ramach wartości procentowej, kwoty lub procentu i kwoty rozbieżności. W tym przykładzie tolerancja uzgadniania cen całkowitych to +15%.

Faktura papierowa z firmy Contoso zawiera następujące informacje.

| Pozycja                        | Ilość | Cena jednostkowa | Kwota netto |
|-----------------------------|----------|------------|------------|
| 1500 — Milicron Obrabiarka | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych        | 8100,00   | 40,500.00  |
| Wysyłka i obsługa       |          |            | 4,000.00   |
| Podatek                         |          |            | 0,00       |
| Razem                       |          |            | 44,500.00  |

Wiersz faktury zawiera następujące informacje.

| Identyfikator towaru                 | Ilość | Cena jednostkowa | Kwota netto wiersza | Zasady uzgadniania    | Dopasowanie ilości dokumentów przyjęcia produktów | Zgodność cen | Uzgadnianie cen całkowitych |
|-----------------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| 1500 — Milicron Obrabiarka | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych        | 8100,00   | 40 500,00       | Uzgadnianie trzyelementowe | Powodzenie                         | Powodzenie      | Powodzenie            |

Ponieważ ten wiersz jest zgodny z procesem uzgadniania faktur, fakturę można zaksięgować.

## <a name="example-three-way-matching-for-item-and-vendor-combinations"></a> Przykład: trzyelementowe uzgadnianie dla kombinacji towaru i dostawcy
Podsumowanie: Ken jest kontrolerem w centrali firmy Fabrikam. Chce, aby wszystkie faktury oparte na zamówieniach zakupu były dopasowane do wierszy zamówień zakupu (uzgadnianie dwuelementowe). Cassie jest kontystką w malezyjskim oddziale firmy Fabrikam. Określa, że wybrane elementy, które zostały zamówione od określonych dostawców w Malezji powinny być uzgadniane zarówno z wierszami zamówienia, jak i z wierszami dokumentu przyjęcia produktów (uzgadnianie trzyelementowe). Może ona również zastąpić zasadę uzgadniania regułą wyższego poziomu dla określonych zamówień zakupu. 

Wielkości i kwoty są małe i w przeszłości zdarzały się problemy z dostawami od niektórych dostawców z Malezji. Z tego powodu Cassie ustawia poziom kontroli dla niektórych kombinacji towaru i dostawcy, które są nabywane w Malezji, na uzgadnianie trzyelementowe. 

Zasady uzgadniania faktur w tym przykładzie ułatwiają pracę osobom na następujących stanowiskach spełniać te cele:
-   Ken jest kontrolerem w firmie Fabrikam. Może on pomóc pracownikom swojej firmy w identyfikowaniu i rozwiązywaniu problemów związanych z zamawianiem, odbieraniem zamówień i płaceniem za towary lub usługi od dostawców.
-   Cassie jest kontystką w malezyjskim oddziale firmy Fabrikam. Może ona wymuszać stosowanie zasad korporacyjnych i zapewniać, że faktury są płacone dopiero po ich uzgodnieniu z wierszami zamówienia zakupu i dokumentem przyjęcia produktów będącym dowodem odebrania towarów lub usług. Może ona także podnieść poziom kontroli do uzgadniania trzyelementowego dla określonych towarów, by umożliwić kontrolę kosztów operacyjnych.

### <a name="prerequisites"></a>Wymagania wstępne

-   Ken ustawia zasadę uzgadniania na poziomie firmy na uzgadnianie dwuelementowe.
-   Wolu Dopasuj ceny całkowite dla firmy Ken wybiera wartość Procent i wpisuje 10% jako wartość procentową rozbieżności.
-   Ken ustawia tolerancję ceny jednostkowej dla wszystkich pozycji na 2%.
-   Cassie ustawia zasadę uzgadniania trzyelementowego dla kombinacji towaru i dostawcy (PH2500 — komputer i dostawca Contoso).
-   Alicia, która pracuje w dziale zamówień zakupów w malezyjskim oddziale firmy Fabrikam, wystawia zamówienie zakupu firmie Contoso na trzy pozycje, jak pokazano w tabeli poniżej. Kiedy tworzy zamówienie zakupu, zastępuje zasadę uzgadniania dla bezprzewodowej myszy na trzyelementowe zamiast dwuelementowego.

    | Numer pozycji           | Ilość | Cena jednostkowa | Kwota netto | Zasady uzgadniania (domyślna) | Zasada uzgadniania (w wierszu zamówienia zakupu) |
    |-----------------------|----------|------------|------------|---------------------------------|----------------------------------------------|
    | PH2500 – komputer     | 2        | 2500,00   | 5000,00   | Uzgadnianie trzyelementowe              | Uzgadnianie trzyelementowe                           |
    | MM01 – mysz bezprzewodowa | 2        | 40,00      | 80,00      | Uzgadnianie dwuelementowe                | Uzgadnianie trzyelementowe                           |
    | Napęd USB             | 200      | 10,00      | 2000,00   | Uzgadnianie dwuelementowe                | Uzgadnianie dwuelementowe                             |

### <a name="scenario"></a>Scenariusz

1.  Towary są dostarczane. Sammy, pracownik działu przyjęć w malezyjskim oddziale firmy Fabrikam, nie księguje dokumentu przyjęcia produktów natychmiast, bo coś odrywa go od pracy.
2.  April, koordynatorka rozrachunków z dostawcami w firmie Fabrikam, wprowadza i sprawdza fakturę przesyłaną przez firmę Contoso. Sprawdza poprawność następujących informacji:
    -   Dla towarów, które wymagają uzgodnienia trzyelementowego, ilość w wierszu faktury odpowiada ilości, która została przyjęta. Przyjęta ilość jest wskazana w dokumencie przyjęcia produktów, który jest uzgodniony z fakturą.
    -   W przypadku towarów wymagających dwuelementowego lub trzyelementowego uzgadniania ceny w wierszu faktury są w granicach tolerancji zdefiniowanych w aplikacji. Obejmuje to następujące typy uzgadniania cen:
        -   Uzgadnianie ceny jednostkowej netto — cena jednostkowa netto w wierszu faktury odpowiada cenie jednostkowej w wierszu zamówienia zakupu w ramach wartości procentowej rozbieżności. W tym przykładzie tolerancja ceny jednostkowej netto to +2%.
        -   Uzgodnienie cen całkowitych — kwota netto w wierszu faktury odpowiada kwocie netto w wierszu zamówienia zakupu w ramach wartości procentowej, kwoty lub procentu i kwoty rozbieżności. W tym przykładzie tolerancja uzgadniania cen całkowitych to +10%.

Faktura papierowa z firmy Contoso zawiera następujące informacje.

| Pozycja                  | Ilość | Cena jednostkowa | Kwota netto |
|-----------------------|----------|------------|------------|
| PH2500 – komputer     | 2        | 2500,00   | 5000,00   |
| MM01 – mysz bezprzewodowa | 2        | 41.00      | 82.00      |
| Napęd USB             | 200      | 10.05      | 2,010.00   |
| Suma faktury         |          |            | 7,092.00   |

Wiersz faktury zawiera następujące informacje.

| Identyfikator towaru           | Ilość | Cena jednostkowa | Kwota netto wiersza | Zasady uzgadniania    | Dopasowanie ilości dokumentów przyjęcia produktów | Zgodność cen | Uzgadnianie cen całkowitych |
|-----------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| PH2500 – komputer     | 2        | 2500,00   | 5000,00        | Uzgadnianie trzyelementowe | Błąd                         | Powodzenie      | Powodzenie            |
| MM01 – mysz bezprzewodowa | 2        | 41.00      | 82.00           | Uzgadnianie trzyelementowe | Błąd                         | Błąd      | Powodzenie            |
| Napęd USB             | 200      | 10.05      | 2010.00         | Uzgadnianie dwuelementowe   |                                | Powodzenie      | Powodzenie            |

Należy uwzględnić następujące elementy:
-   Dla wiersza PH2500 — komputer, kolumna Dopasowanie ilości dokumentów przyjęcia produktów zawiera ikonę ostrzeżenia, bo wiersz faktury nie jest uzgodniony z dokumentem przyjęcia produktów.
-   Dla wiersza MM01 — mysz bezprzewodowa, kolumna Dopasowanie ilości dokumentów przyjęcia produktów zawiera ikonę ostrzeżenia, bo wiersz faktury nie jest uzgodniony z dokumentem przyjęcia produktów. Kolumna Uzgodnienie cen jednostkowych zawiera ikonę ostrzeżenia, ponieważ przekroczono 2% tolerancję ceny jednostkowej netto.
-   Dla wiersza Napęd USB kolumna Dopasowanie ilości dokumentów przyjęcia produktów jest pusta, bo uzgadnianie dwuelementowe nie pasuje do ilości w wierszu faktury ani w wierszu dokumentu przyjęcia produktów.

Jeśli zatwierdzenie jest wymagane, aby można było zaksięgować faktury z rozbieżnościami uzgadniania, opcja Zatwierdzaj księgowanie w razie rozbieżności w uzgadnianiu na stronie Szczegóły uzgadniania faktur musi być wybrana, zanim faktura będzie mogła być zaksięgowana z błędami uzgadniania cen i błędami uzgadniania ilości. Jeśli zatwierdzanie nie jest wymagane, przetwarzanie faktury może być kontynuowane, jeśli nie ma żadnych innych błędów księgowania.


Aby uzyskać więcej informacji, zobacz [Uzgadnianie faktur rozrachunków z dostawcami](accounts-payable-invoice-matching.md).



