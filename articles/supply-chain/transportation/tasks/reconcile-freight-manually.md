---
title: Ręczne uzgadnianie frachtu
description: Ta procedura pokazuje, jak uzgadniać fracht ręcznie.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee2d114b0a725b947add3e155cc6445021fee998
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556741"
---
# <a name="reconcile-freight-manually"></a>Ręczne uzgadnianie frachtu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak uzgadniać fracht ręcznie. Zazwyczaj jest to realizowane przez koordynatora transportu. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.


## <a name="select-a-load-to-reconcile"></a>Wybór ładunku do uzgodnienia
1. Wybierz kolejno opcje Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku.
2. Wyczyść pole wyboru Ukryj wysłane i odebrane. 
3. Na liście zaznacz ładunek o identyfikatorze 00006.

## <a name="create-a-carrier-invoice"></a>Tworzenie faktury przewoźnika
    * Jeśli uzgadniasz fracht ręcznie i nie otrzymujesz faktur przewoźnika automatycznie, można utworzyć fakturę na podstawie dokumentu opłaty frachtowej.  
1. Kliknij opcję Informacje pokrewne.
2. Kliknij opcję Szczegóły opłaty frachtowej.
3. Kliknij opcję Generowanie faktury za opłatę frachtową.
4. W polu Faktura wpisz wartość.
5. Kliknij przycisk OK.

## <a name="reconcile-the-invoice"></a>Uzgadnianie faktury
    * Podczas uzgadniania faktury przewoźnika z dokumentem opłaty frachtowej operacja odbywa się wiersz po wierszu.  
1. Kliknij opcję Dopasuj opłaty frachtowe i faktury.
2. Rozwiń sekcję Szczegóły faktury.
3. Rozwiń sekcję Szczegóły niedopasowanej opłaty frachtowej.
4. Na liście oznacz wybrany wiersz.
5. Kliknij przycisk Uzgodnij.
6. Rozwiń sekcję Szczegóły dopasowanej opłaty frachtowej.

## <a name="submit-the-invoice-for-approval"></a>Prześlij fakturę do zatwierdzenia
1. Kliknij opcję Prześlij do zatwierdzenia.
2. Zamknij stronę.
3. Zaznacz pole wyboru Ukryj zatwierdzone. 
4. Kliknij opcję Arkusze faktur dostawcy.
5. Kliknij, aby otworzyć łącze znajdujące się w polu Odwołanie do identyfikatora arkusza.
6. Kliknij przycisk Wiersze.

