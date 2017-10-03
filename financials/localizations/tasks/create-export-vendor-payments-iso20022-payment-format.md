--- 
title: "Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022"
description: "W tej procedurze pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 16c2af862a73047a2e6ebdc056275392fa8a0d93
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022. 

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF.

Jest to piąta z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="create-payment-lines"></a>Tworzenie wierszy płatności
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Nazwa wprowadź lub wybierz wartość.
5. Kliknij przycisk Wiersze.
6. Kliknij opcję Propozycja płatności.
7. Kliknij opcję Utwórz propozycję płatności.
8. Rozwiń sekcję Rekordy do uwzględnienia.
9. Kliknij przycisk Filtr.
10. Na liście zaznacz wiersz dla tabeli Dostawcy i pola Konto dostawcy.
11. W polu Kryteria wprowadź lub wybierz wartość.
    * Można stosować dowolne kryteria w celu wybrania transakcji z dostawcą, które mają zostać opłacone. W tym przykładzie zostanie użyte kryterium DE-001 jako konto dostawcy.  
12. Kliknij przycisk OK.
13. Kliknij przycisk OK.
14. Kliknij opcję Utwórz płatności.

## <a name="generate-an-iso20022-payment-file"></a>Generowanie pliku płatności ISO20022


