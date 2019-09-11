---
title: Konfigurowanie standardowych kosztów robocizny i wydatków
description: W tym temacie pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867733"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Konfigurowanie standardowych kosztów robocizny i wydatków

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym temacie pokazano sposób konfigurowania standardowych kosztów robocizny i wydatków dla projektu. W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.

1. W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (godzina)**.
2. Wybierz pozycję **Nowy**.
3. W polu **Data wejścia w życie** wprowadź datę.
4. W polu **Koszt własny** wpisz liczbę. Można ustawić standardową wartość kosztu własnego dla kategorii projektu lub ustawić koszt własny według numeru pracownika, numeru projektu, kategorii, daty lub dowolnej kombinacji tych parametrów. Stosowany będzie koszt własny o najwyższym poziomie szczegółowości.  
5. Wybierz opcję **Zapisz**.
6. W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (godzina)**.
7. Wybierz pozycję **Nowy**.
8. W polu **Data wejścia w życie** wprowadź datę.
9. W polu **Ważny dla** wybierz opcję.
10. W polu **Ceny** wpisz liczbę. Użytkownik może ustawić standardową cenę sprzedaży dla transakcji godzinowych lub dla kategorii projektu. Może również ustawić ceny sprzedaży według numeru pracownika, numeru projektu, kategorii, daty transakcji albo dowolnej kombinacji tych wartości. Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu godzin jest ceną sprzedaży o najwyższym poziomie szczegółowości. Jeśli na przykład ustawiono zarówno ogólną cenę sprzedaży, jak i cenę sprzedaży dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.  
11. Wybierz opcję **Zapisz**.
12. Zamknij stronę.
13. W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Koszt własny (wydatek)**.
14. Wybierz pozycję **Nowy**.
15. W polu **Data wejścia w życie** wprowadź datę.
16. W polu **Koszt własny** wpisz liczbę. Można wypełnić wiele pól, ale to jest minimum niezbędne do zapisania rekordu.  
17. Wybierz opcję **Zapisz**.
18. W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena sprzedaży (wydatek)**.
19. Wybierz pozycję **Nowy**.
20. W polu **Data wejścia w życie** wprowadź datę.
21. W polu **Ważny dla** wybierz opcję.
22. W polu **Ceny** wpisz liczbę. Rzeczywista cena sprzedaży stosowana podczas wprowadzania transakcji przez pracownika w arkuszu wydatków jest ceną sprzedaży o najwyższym poziomie szczegółowości. Jeśli na przykład ustawiono cenę sprzedaży zarówno ogólną, jak i dla danego pracownika, będzie używana cena sprzedaży dla danego pracownika.  
23. Wybierz opcję **Zapisz**.

