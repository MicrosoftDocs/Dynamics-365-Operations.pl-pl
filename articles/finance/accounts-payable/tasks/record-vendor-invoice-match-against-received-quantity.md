---
title: Rejestrowanie faktury od dostawcy i porównywanie z przyjętą ilością
description: Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę.
author: ShivamPandey-msft
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9d3fab4be1de90783d5885cf46b9e0cf6ee74b5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820624"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>Rejestrowanie faktury od dostawcy i porównywanie z przyjętą ilością

[!include [banner](../../includes/banner.md)]

Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę. Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur. 

Na stronie Parametry modułu rozrachunków z dostawcami upewnij się, że zaznaczono opcję Włącz weryfikację uzgadniania faktur, w polu Księguj fakturę z rozbieżnościami zaznaczono opcję Wymagaj zatwierdzania, a pole Zasady uzgadniania wierszy ma wartość Uzgadnianie trzyelementowe.

Ta procedura wykorzystuje firmę demonstracyjną USMF. Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości.


## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu
1. Przejdź do okna Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. W polu Konto dostawcy wpisz wartość.
5. Kliknij przycisk OK.
6. Kliknij przycisk Dodaj wiersz.
7. W polu Numer towaru wpisz wartość.
8. W okienku akcji kliknij pozycję Zakup.
9. Kliknij przycisk Potwierdź.

## <a name="post-a-product-receipt"></a>Księgowanie dokumentu przyjęcia produktów
1. W okienku akcji kliknij pozycję Odbierz.
2. Kliknij opcję Dokument przyjęcia produktów.
3. Na liście oznacz wybrany wiersz.
4. W polu Dokument przyjęcia produktów wpisz wartość.
5. Kliknij przycisk OK.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Rejestrowanie i uzgadnianie faktury od dostawcy z dokumentem przyjęcia produktów
1. W okienku akcji kliknij pozycję Faktura.
2. Kliknij opcję Faktura.
3. W polu Numer wpisz wartość.
4. Na liście Domyślnie z zaznacz opcję Zamówiona ilość, aby otworzyć rozwijane okno dialogowe.
5. W polu Domyślna ilość dla wierszy zaznacz opcję.
6. Kliknij przycisk OK.
7. Kliknij przycisk Tak.
8. Kliknij opcję Dopasuj dokumenty przyjęcia produktów.
9. Kliknij przycisk OK.
10. W okienku akcji kliknij pozycję Przegląd.
11. Kliknij przycisk Szczegóły uzgadniania.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]