---
title: Ręczne uzgadnianie frachtu
description: Ta procedura pokazuje, jak uzgadniać fracht ręcznie.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8679a729dc17e3ee85468b459da3956a92160ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974067"
---
# <a name="reconcile-freight-manually"></a>Ręczne uzgadnianie frachtu

[!include [banner](../../includes/banner.md)]]

Ta procedura pokazuje, jak uzgadniać fracht ręcznie. Zazwyczaj jest to realizowane przez koordynatora transportu. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.


## <a name="select-a-load-to-reconcile"></a>Wybór ładunku do uzgodnienia
1. Wybierz kolejno opcje Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku.
2. Wyczyść pole wyboru Ukryj wysłane i odebrane. 
3. Na liście zaznacz ładunek o identyfikatorze 00006.

## <a name="create-a-carrier-invoice"></a>Tworzenie faktury przewoźnika
Jeśli uzgadniasz fracht ręcznie i nie otrzymujesz faktur przewoźnika automatycznie, można utworzyć fakturę na podstawie dokumentu opłaty frachtowej.  
1. Kliknij opcję Informacje pokrewne.
2. Kliknij opcję Szczegóły opłaty frachtowej.
3. Kliknij opcję Generowanie faktury za opłatę frachtową.
4. W polu Faktura wpisz wartość.
5. Kliknij przycisk OK.

## <a name="reconcile-the-invoice"></a>Uzgadnianie faktury
Podczas uzgadniania faktury przewoźnika z dokumentem opłaty frachtowej operacja odbywa się wiersz po wierszu.  
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

