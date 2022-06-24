---
title: Obliczanie i korygowanie podatku na fakturze od dostawcy
description: W tym artykule wyjaśniono, jak dostosować podatek od sprzedaży na fakturze od dostawcy w Dynamics 365 Finance.
author: twheeloc
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a1093631688351d065d6b55bc65055b6f92d256
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868381"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Obliczanie i korygowanie podatku na fakturze od dostawcy

[!include [banner](../../includes/banner.md)]

W tym artykule wyjaśniono, jak dostosować podatek od sprzedaży na fakturze od dostawcy. Jeśli oryginalny dokument źródłowy zawiera kwoty podatku inne niż obliczone, można skorygować te kwoty przed zaksięgowaniem. W zadaniu wykorzystano firmę demonstracyjną DEMF.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami > Faktury > Arkusz faktur**.
2. Wybierz pozycję **Nowy**.
3. W polu **nazwa** nowego wiersza wybierz opcję z menu rozwijanego.
4. W okienku akcji wybierz **Wiersze**.
5. W polu **Konto** podaj żądane wartości.
6. W polu **Faktura** wpisz wartość.
7. W polu **Kredyt** wpisz liczbę.
8. W polu **Konto przeciwstawne** podaj żądane wartości.
9. Wybierz **Podatek**.
10. W polu **Całkowita rzeczywista kwota podatku** wpisz liczbę.
11. Na karcie **Korekta** można skorygować kwoty podatku według kodów podatków.
12. Wybierz **Resetuj aktualne kwoty na podstawie obliczonych**.
13. Kliknij przycisk **OK**.
14. Wybierz opcję **Zapisz**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
