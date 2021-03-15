---
title: Rejestrowanie faktury od dostawcy w arkuszu faktur
description: W tym przewodniku po zadaniach pokazano sposób rejestrowania faktur dostawców, które nie są powiązane z zamówieniami zakupu.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18d8b74bd8783c23e548a3185414d1461bc1d869
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971835"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Rejestrowanie faktury od dostawcy w arkuszu faktur

[!include [banner](../../includes/banner.md)]

W tym przewodniku po zadaniach pokazano sposób rejestrowania faktur dostawców, które nie są powiązane z zamówieniami zakupu. Przykładami tego rodzaju faktur są faktury za wydatki na materiały eksploatacyjne lub usługi.  To nagranie wykorzystuje firmę demonstracyjną USMF.

1. Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Obszary robocze > Wprowadzanie faktur od dostawcy**.
2. W **Okienku akcji** kliknij **Nowy arkusz faktur**.
3. Kliknij przycisk **Nowy**.
4. W polu **Nazwa** nadaj arkuszowi nazwę lub kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. W polu **Opis** wpisz wartość.
6. W **okienku akcji** kliknij pozycję **Wiersze**. W polu **Data** wprowadź datę księgowania, która spowoduje aktualizację Księgi głównej.  
7. W polu **Konto** określ **konto dostawcy**.
8. W polu **Faktura** wprowadź numer faktury.
9. W polu **Opis** wpisz wartość.
10. W polu **Kredyt** wpisz liczbę.
11. W polu **Konto przeciwstawne** wpisz numer konta lub kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wartość pola **Grupa podatków** zostanie pobrana domyślnie z ustawień konta dostawcy.  
    * Wartość pola **Grupa podatków** dla towaru jest pobierana z ustawień konta głównego określonego w polu **Konto przeciwstawne**.  
    * **Termin płatności** zostanie obliczony na podstawie warunków płatności.  
    * Wartość pola **Rabat gotówkowy** zostanie pobrana domyślnie z ustawień konta dostawcy.
12. Jeśli włączono przepływ pracy Arkusz faktur od dostawców, kliknij kolejno opcje **Przepływ pracy > Prześlij**.
    * Po zatwierdzeniu przesłanych informacji data zostanie przeniesiona do pierwszego dnia następnego otwartego okresu, jeśli data księgowania transakcji przypada w okresie wstrzymania lub zamknięcia księgowania w księdze.
12. Kliknij przycisk **Księguj**.
13. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]