---
title: Konfigurowanie kodów podatków
description: W tym temacie wyjaśniono sposób konfigurowania kodów podatków w Dynamics 365 Finance.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5ce2c8d9a117871191dd1c2d32d822bcc72d76fabaec146d9b8c27fc85dc058
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719205"
---
# <a name="set-up-sales-tax-codes"></a>Konfigurowanie kodów podatków

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania kodów podatków. Kody podatków tworzy się dla każdego podatku pośredniego lub cła, które firma musi naliczać, pobierać i wpłacać do urzędu skarbowego.

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]