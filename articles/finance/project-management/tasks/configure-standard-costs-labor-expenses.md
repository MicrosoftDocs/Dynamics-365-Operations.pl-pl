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
ms.openlocfilehash: 51bbe52d70bae11cb0c95e9544f951f0fcc605f5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140100"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Konfigurowanie standardowych kosztów robocizny i wydatków

[!include [banner](../../includes/banner.md)]

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

