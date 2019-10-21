---
title: Konfigurowanie fakturowania projektów międzyfirmowych
description: W tym temacie pokazano sposób konfigurowania fakturowania projektów między dwoma firmami w tej samej organizacji.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174450"
---
# <a name="configure-intercompany-project-invoicing"></a>Konfigurowanie fakturowania projektów międzyfirmowych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym temacie pokazano sposób konfigurowania fakturowania projektów między dwoma firmami w tej samej organizacji. W tym zadaniu jest wykorzystywany zestaw danych firmy USSI.

1. W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawcy**.
2. Na liście **Wszyscy dostawcy** znajdź i zaznacz odpowiedni rekord.
3. W okienku akcji wybierz pozycję **Ogólne**.
4. Wybierz **Międzyfirmowe**.
5. W ustawieniu **Aktywne zaznacz** wartość **Tak**, aby włączyć handel międzyfirmowy.
6. W polu **Firma odbiorcy** wprowadź lub wybierz wartość.
7. W polu **Moje konto** wprowadź lub wybierz wartość.
8. Wybierz opcję **Zapisz**.
9. Zamknij te strony, aby powrócić do strony głównej.
10. W okienku nawigacji przejdź kolejno do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Parametry modułu Zarządzanie projektami i ich księgowanie**.
11. Wybierz kartę **Międzyfirmowe**.
12. Przesuń suwak do pozycji **Tak**, aby włączyć międzyfirmowe planowanie zasobów i karty czasu pracy.
13. Na liście oznacz wybrany wiersz.
14. Wybierz pozycję **Nowy**.
15. W polu **Firma pożyczająca** wprowadź lub wybierz wartość.
16. Zaznacz pole wyboru **Naliczanie przychodu**.
17. W polu **Domyślna kategoria karty czasu pracy** wprowadź lub wybierz wartość.
18. W polu **Domyślna kategoria wydatku pracy** wprowadź lub wybierz wartość.
19. Wybierz opcję **Zapisz**.
20. Zamknij stronę.
21. W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Księgowanie > Konfiguracja księgowania**.
22. W polu **Typy kont księgowych** zaznacz opcję.
23. Wybierz pozycję **Nowy**.
24. W polu **Konto główne** w mpwym wierszu podaj żądane wartości.
25. Wybierz opcję **Zapisz**.
26. Zamknij stronę.
27. W okienku nawigacji przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Ustawienia > Ceny > Cena transferowa**.
28. Wybierz pozycję **Nowy**.
29. W polu **Data wejścia w życie** wprowadź datę.
30. W polu **Firma pożyczająca** wprowadź lub wybierz wartość.
31. W polu **Model ceny transferu** wybierz opcję.
32. W polu **Ceny** wpisz liczbę.
33. Wybierz opcję **Zapisz**.

