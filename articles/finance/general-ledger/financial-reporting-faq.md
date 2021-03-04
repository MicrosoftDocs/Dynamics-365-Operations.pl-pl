---
title: Raportowanie finansowe — często zadawane pytania
description: W tym temacie omówiono pytania związane z raportowaniem finansowym zgłoszone przez innych użytkowników.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3f9381f5b656d0cc0b46c8828b2ef9d024e296b0
ms.sourcegitcommit: 14785208d84b2c1efd30f140c52df35a2ccd1577
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/27/2021
ms.locfileid: "5070224"
---
# <a name="financial-reporting-faq"></a>Raportowanie finansowe — często zadawane pytania 

W tym temacie omówiono pytania związane z raportowaniem finansowym zgłoszone przez innych użytkowników. 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Jak ograniczyć dostęp do raportu przy użyciu drzewa zabezpieczeń?

Scenariusz: firma demonstracyjna USMF opracowała raport bilansowy, do którego chce ograniczyć dostęp w taki sposób, by nie wszyscy użytkownicy funkcji Financial Reporting mieli w niego wgląd w rozwiązaniu D365. Rozwiązanie: w celu ograniczenia dostępu do jednego raportu można użyć drzewa zabezpieczeń — dzięki temu dostęp do raportu będą mieć tylko wybrani użytkownicy. 

1.  Zaloguj się do Projektanta raportów modułu Financial Reporter.

2.  Utwórz nową definicję drzewa (Plik | Nowy | Definicja drzewa). a.    Kliknij dwukrotnie wiersz **Podsumowanie** w kolumnie **Zabezpieczenia jednostki**.
  i.    Kliknij pozycję Użytkownicy i grupy.  
          1. Wybierz użytkowników lub grupę do przyznania dostępu do tego raportu. 
          
[![ekran użytkownika](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)

[![ekran zabezpieczeń](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)

  b.    Kliknij przycisk **Zapisz**.
  
[![przycisk Zapisz](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)

3.  W definicji raportu dodaj nową definicję drzewa.

[![formularz definicji drzewa](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)

A.  W obszarze definicji drzewa kliknij pozycję Ustawienie i w obszarze „Wybór jednostki raportowania” zaznacz opcję „Uwzględnij wszystkie jednostki”.

[![formularz wyboru jednostki raportowania](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)

**Przed:** [![zrzut ekranu przed](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)

**Po:** [![zrzut ekranu po](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)

Uwaga: powodem wyświetlenia powyższej wiadomości jest fakt, że użytkownik nie ma dostępu do tego raportu po zastosowaniu zabezpieczeń jednostki.



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a>Jak ustalić, które konta nie są zgodne z moimi saldami w D365?

Jeśli masz raport, który zawiera inne dane niż te, których można by się spodziewać w usłudze D365, wykonaj kilka kroków w celu zidentyfikowania tych kont oraz odchyleń. 

### <a name="in-financial-reporter-report-designer"></a>W Projektancie raportów modułu Financial Reporter

1.  Utwórz nową definicję wiersza. a.    Kliknij kolejno Edycja | Wstaw wiersze z wymiarów. i.  Wybierz pozycję MainAccount [![Wybierz ekran główny](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)
    
    ii. Kliknij przycisk OK. b.    Zapisz definicję wiersza.

2.  Utwórz nową definicję kolumny [![Utwórz nową definicję kolumny](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)

3.  Utwórz nową definicję raportu. a.    Kliknij przycisk Ustawienia i usuń zaznaczenie [![formularza Ustawienia](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)
   
4.  Wygeneruj raport. 

5.  Wyeksportuj raport do programu Excel.

### <a name="in-d365"></a>W usłudze D365: 
1.  Kliknij pozycję Księga główna | Zapytania i raporty | Bilans próbny. a.    Parametry i.  Data początkowa: początek roku obrachunkowego. ii. Data końcowa: data wygenerowania raportu iii.    Zestawów wymiarów finansowych „Zestaw konta głównego” [![Formularz konta głównego](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)
      
  b.    Kliknij przycisk Oblicz.

2.  Wyeksportuj raport do programu Excel.

Teraz powinno być możliwe skopiowanie danych z raportu rozwiązania Financial Reporting w programie Excel do raportu bilansu próbnego D365 oraz porównanie kolumn „Saldo zamknięcia”.
