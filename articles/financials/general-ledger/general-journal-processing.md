---
title: Przetwarzanie arkuszy finansowych
description: Ten temat opisuje funkcje rozwiązania Microsoft Dynamics 365 for Finance and Operations, które mogą ułatwić przetwarzanie arkusza finansowego, a także zagwarantować rejestrowanie właściwych danych i bezpieczeństwo dla aparatu wewnętrznej kontroli.
author: ShylaThompson
manager: AnnBe
ms.date: 09/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7efd250428f7675b96674dd02e3aeccefe653fe
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839238"
---
# <a name="general-journal-processing"></a>Przetwarzanie arkuszy finansowych

[!include [banner](../includes/banner.md)]

Ten temat opisuje funkcje rozwiązania Microsoft Dynamics 365 for Finance and Operations, które mogą ułatwić przetwarzanie arkusza finansowego, a także zagwarantować rejestrowanie właściwych danych i bezpieczeństwo dla aparatu wewnętrznej kontroli.  

## <a name="journal-names"></a>Nazwy arkuszy

Jednym z najważniejszych obszarów do skonfigurowania są nazwy arkuszy. Dobrze jest używać określonych nazw arkusza do każdego celu, np. międzyfirmowe, korekty naliczania i korekcja błędów. Można dostosować nazwę każdego arkusza, aby wprowadzanie danych dla każdego celu było łatwe i bezpieczne. 

Na stronie **Nazwy arkuszy** można skonfigurować następujące elementy:

-   **Zatwierdzanie w ramach przepływu pracy** — aby podnieść poziom kontroli wewnętrznej, można zdefiniować przepływy pracy określające limity materiałów dla poszczególnych kroków sprawdzania i zatwierdzania na podstawie takich kryteriów, jak łączna kwota debetu. Można skonfigurować przepływy pracy dla arkuszy finansowych na stronie **Przepływy pracy dla księgi głównej**.
-   **Wartości domyślne** — można wybrać wartości domyślne kont przeciwstawnych, waluty i wymiarów finansowych.
-   **Kontrola arkusza** — można skonfigurować ograniczenia dla typu firmy i konta, a także wartości segmentów. 

**Przykłady**

Nazwa arkusza może być używana tylko do korekt. W takim przypadku można wskazać, że dla wszystkich firm ważne jest tylko konto typu **Księga**. 

[![Typy kont kontroli arkusza](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Nazwa arkusza może być używana tylko dla określonego segmentu lub w określonym zakresie dla kont głównych. 

[![Segment kontroli arkusza](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

Opcja **Automatyczne stornowanie** jest dostępna w arkuszach finansowych. Na przykład użytkownik ma korektę naliczania, jeśli dokument nie został jeszcze przetworzony, jak pokazano na poniższej ilustracji.
[![Stornowanie arkusza finansowego](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

Dodatek programu Microsoft Excel z funkcjonalnością wpisów arkusza oferuje dodatkowy poziom automatyzacji i ułatwia wprowadzanie danych. Działanie **Otwórz wiersze w programie Excel** jest dostępne na stronach **Arkusz finansowy** i **Załącznik arkusza**. 

Na stronie **Arkusze okresowe** można skonfigurować dzienniki cykliczne automatyzujące przetwarzanie arkuszy. 

Możesz skorzystać z szablonów załącznika w dowolnym momencie. Na stronie **Arkusz finansowy** działania **Zapisz** i **Wybierz szablon załącznika** są dostępne na stronie **Załącznik arkusza** w sekcji **Funkcje** dla wierszy załącznika.

## <a name="related-setup"></a>Pokrewna konfiguracja
Następująca konfiguracja nie jest właściwa dla arkuszy finansowych, ale ułatwia prawidłowe wprowadzanie danych.

### <a name="main-account"></a>Konto główne

Konfiguracja konta głównego oferuje wiele opcji przetwarzania arkusza finansowego:

-   **Wymagane debet lub kredyt** — użyj tej opcji, jeśli konto główne jest ograniczone do transakcji po stronie debetowej lub kredytowej. Po zweryfikowaniu lub zaksięgowaniu arkusza następuje sprawdzenie poprawności konfiguracji.

-   **Domyślne konto przeciwstawne**
-   **Zawieszone** — pozwala zawiesić konto główne dla wprowadzania danych we wszystkich firmach lub dla konkretnej firmy.
-   **Nie zezwalaj na wprowadzanie ręczne** — uniemożliwia użytkownikom ręczne wprowadzanie wartości dla konta w arkuszach.
-   **Domyślna waluta/Sprawdź poprawność waluty**
-   **Firma zastępuje** — to ustawienie jest właściwe dla zdefiniowanej firmy/podmiotu prawnego:
    -   **Domyślny podatek/Sprawdź poprawność podatku**
    -   **Wymiar domyślny** — **Niestałe** lub **Stała wartość**. **Stała wartość** pomaga zagwarantować, że wszystkie księgowania dla tego konta głównego zawsze używają wartości wymiarów określonych jako **Stałe**.
-   **Weryfikacja księgowania**
    -   **Weryfikacja użytkownika** — ta opcja pozwala kontrolować, którzy użytkownicy mogą księgować na koncie głównym.
    -   **Weryfikacja typów księgowania** — ta opcja pozwala kontrolować, które typy księgowania są dopuszczalne na koncie głównym.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Struktury księgowania i struktury reguł zaawansowanych

Struktury księgowania i struktury zaawansowanych reguł są bardzo ważne do zagwarantowania, że dane, które są wymagane do raportowania finansowego i śledzenia wydajności, są rejestrowane przy przetwarzaniu arkusza finansowego i wszelkich dokumentów. Struktury księgowania i struktury reguły zaawansowanych pozwalają dostosować sposób wprowadzania danych. Można zezwolić na wprowadzanie danych tylko dla wymiarów finansowych, które są odpowiednie w poszczególnych sytuacjach, a można też wymuszać wymaganie, by rejestrowane były tylko dane wymagane i rzetelne.

Aby uzyskać więcej informacji, zobacz następujące tematy:
- [Planowanie: Obsługa planu kont](plan-chart-of-accounts.md). 
- [Tworzenie reguł zaawansowanych dla arkuszy](tasks/create-advanced-rules-journals.md)
- [Tworzenie wpisu w arkuszu za pomocą szablonu](tasks/create-journal-entry-template.md)
- [Tworzenie i sprawdzanie arkuszy](tasks/create-validate-journals.md)
- [Księgowanie arkuszy okresowych](tasks/post-periodic-journals.md)
- [Przetwarzanie arkusza alokacji księgi](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a>Symuluj księgowanie
Opcja **Symuluj księgowanie** znajduje się w menu **Sprawdź poprawność** w większości arkuszy. Podczas sprawdzania poprawności arkusza za pomocą funkcji **Sprawdź poprawność** system bada arkusza pod kątem określonych błędów. Jeśli używasz funkcji **Symuluj księgowanie**, system uruchamia wszystkie te same procesy, które są wykonywane podczas księgowania, ale faktycznie nie księguje arkusza. Następnie można przejrzeć wyświetlone komunikaty o księgowaniu oraz poprawić wszystkie znalezione błędy, po czym kliknąć menu **Księguj**, aby zaksięgować arkusz. 

Funkcja **Symuluj księgowanie** jest niedostępna dla przetwarzania wsadowego. Jest jednak dostępny kod źródłowy umożliwiający symulację przetwarzania wsadowego i deweloperzy mogą za jego pomocą dodać tę funkcjonalność.  
