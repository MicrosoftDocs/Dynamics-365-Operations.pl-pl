---
title: Rejestrowanie faktury od dostawcy w arkuszu faktur
description: W tym przewodniku po zadaniach pokazano sposób rejestrowania faktur dostawców, które nie są powiązane z zamówieniami zakupu.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 775f3764d34cecbfc071ff7420d32c7832b42308
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556364"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Rejestrowanie faktury od dostawcy w arkuszu faktur

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach pokazano sposób rejestrowania faktur dostawców, które nie są powiązane z zamówieniami zakupu. Przykładami tego rodzaju faktur są faktury za wydatki na materiały eksploatacyjne lub usługi.  To nagranie wykorzystuje firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Obszary robocze > Wprowadzanie faktur od dostawcy.
2. Kliknij opcję Nowy arkusz faktur.
3. Kliknij przycisk Nowy.
4. W polu Nazwa nadaj arkuszowi nazwę lub kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Wypełnij pole Opis.
6. Kliknij przycisk Wiersze.
    * W polu Data wprowadź datę księgowania, która spowoduje aktualizację Księgi głównej.  
7. W polu Konto podaj konto dostawcy.
8. W polu Faktura wprowadź numer faktury.
9. W polu Opis wpisz wartość.
10. W polu Kredyt wpisz liczbę.
11. W polu Konto przeciwstawne wpisz numer konta lub kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wartość pola Grupa podatków zostanie pobrana domyślnie z ustawień konta dostawcy.  
    * Wartość pola Grupa podatków dla towaru jest pobierana z ustawień konta głównego określonego w polu Konto przeciwstawne.  
    * Termin płatności zostanie obliczony na podstawie warunków płatności.  
    * Wartość pola Rabat gotówkowy zostanie pobrana domyślnie z ustawień konta dostawcy.  
12. Kliknij przycisk Księguj.
13. Zamknij stronę.

