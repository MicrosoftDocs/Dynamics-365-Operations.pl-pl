---
title: Konfigurowanie kodów podatków
description: W tym temacie wyjaśniono sposób konfigurowania kodów podatków w Dynamics 365 for Finance and Operations.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3419c6b569093d717158e80bd9bc01054d82bff9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834837"
---
# <a name="set-up-sales-tax-codes"></a>Konfigurowanie kodów podatków

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym temacie wyjaśniono sposób konfigurowania kodów podatków w Dynamics 365 for Finance and Operations. Kody podatków tworzy się dla każdego podatku pośredniego lub cła, które firma musi naliczać, pobierać i wpłacać do urzędu skarbowego.

W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Otwórz **Okienko nawigacji > Podatek > Podatki pośrednie > Podatek > Kody podatków**.
2. Wybierz pozycję **Nowy**.
3. W polu **Kod podatku** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. Wybierz **okres rozliczenia**, otwierając listę rozwijaną, aby określić, do którego urzędu skarbowego i w których interwałach ten podatek musi być zgłaszany i płacony.
6. Wybierz **grupę księgowania**, aby określić konta główne w Księdze głównej, na których będzie księgowany podatek.
7. Rozwiń skróconą kartę **Obliczanie**. Zawiera ona wiele pól, które kontrolują sposób obliczania kwot podatków. Odpowiednio wypełnij te pola.  
8. W **okienku akcji** u góry interfejsu wybierz **Kod podatku**.
9. Wybierz **Wartości**.
10. Wprowadź wartość dla tego kodu podatków w kolumnie **Wartość**.
    - Jeśli na skróconej karcie **Obliczanie** w polu Podstawa opodatkowania wybrano opcję Kwota na jednostkę, w celu obliczenia kwoty podatku wartość będzie mnożona przez ilość w transakcji.  Jeśli kod podatku nie dotyczy podatku jednostkowego, w celu obliczenia kwoty podatku wartość jest procentem stosowanym do podstawy opodatkowania dla tego kodu podatku.     
11. Wybierz opcję **Zapisz**.
12. Zamknij stronę.
13. Wybierz opcję **Zapisz**.

