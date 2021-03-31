---
title: EUR-00012 Wystawianie świadectwa wywozowego UE
description: Ta procedura poprowadzi przez proces włączania obsługi świadectw wywozowych UE, konfigurowania konta odbiorcy do obsługi świadectw oraz wystawiania świadectw.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95c1f3f87175a2c2a2887a4ed2ebde1bd7d1c0b9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227970"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a>EUR-00012 Wystawianie świadectwa wywozowego UE

[!include [banner](../../includes/banner.md)]
Ta procedura poprowadzi przez proces włączania obsługi świadectw wywozowych UE, konfigurowania konta odbiorcy do obsługi świadectw oraz wystawiania świadectw. Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.


## <a name="enable-entry-certificate-management"></a>Włącz zarządzanie świadectwami wywozowymi
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia > Parametry modułu rozrachunków z odbiorcami.
2. Kliknij kartę Wysyłki.
3. Rozwinięcie sekcję Świadectwo wywozowe.
4. W polu Włącz zarządzanie świadectwami wywozowymi zaznacz opcję Tak.
5. W polu Włącz opcję wystawiania świadectwa wywozowego zaznacz opcję Tak.
6. Kliknij kartę Sekwencje numerów.
7. Na liście znajdź i zaznacz wiersz Świadectwo wywozowe.
8. W polu Kod sekwencji numerów wprowadź lub wybierz wartość.

## <a name="set-up-a-customer"></a>Konfigurowanie odbiorcy
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Konto z wartością „DE-015”.
3. Otwórz szczegóły konta odbiorcy.
4. Kliknij przycisk Edytuj.
5. Rozwiń sekcję Faktura i dostawa.
6. W polu Wymagane jest świadectwo wywozowe zaznacz opcję Tak.
7. W polu Wystaw świadectwo wywozowe zaznacz opcję Tak.
8. Kliknij przycisk Zapisz.

## <a name="create-an-eu-entry-certificate-automatically"></a>Automatyczne tworzenie świadectwa wywozowego UE
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wprowadź lub wybierz wartość.
4. Kliknij przycisk OK.
5. W polu Numer towaru wprowadź lub wybierz wartość.
6. Kliknij przycisk Zapisz.
7. W okienku akcji kliknij opcję Pobierz i zapakuj.
8. Kliknij opcję Księguj dokument dostawy.
9. Rozwiń sekcję Parametry.
10. W polu Ilość zaznacz opcję Wszystko.
11. Wyczyść pole wyboru Wystaw świadectwo wywozowe.
    * Świadectwo wywozowe może zostać wystawione podczas księgowania dokumentu dostawy lub podczas fakturowania zamówienia. Aby wystawić je później, pozostaw niezaznaczone pole wyboru Wystaw świadectwo wywozowe.  
12. Kliknij przycisk OK.
13. Kliknij przycisk OK.
14. W okienku akcji kliknij pozycję Faktura.
15. Kliknij opcję Faktura.
    * Sprawdź, czy w sekcji Przegląd są zaznaczone pola wyboru Wymagane jest świadectwo wywozowe i Wystaw świadectwo wywozowe.  Można również zaznaczyć pole wyboru Drukuj świadectwo wywozowe, aby pozwolić na drukowanie certyfikatu.  
16. Kliknij przycisk OK.
17. Kliknij przycisk OK.
18. W okienku akcji kliknij pozycję Faktura.
19. Kliknij opcję Faktura.
20. W okienku akcji kliknij pozycję Faktura.
21. Kliknij opcję Wyświetl wystawione świadectwa wywozowe.
22. Kliknij przycisk Drukuj.
23. Zamknij stronę.
24. Kliknij przycisk Zmień stan.
25. W polu Nowy stan wybierz opcję.
26. Kliknij przycisk OK.
27. Zamknij stronę.

## <a name="create-an-eu-entry-certificate-manually"></a>Ręczne tworzenie świadectwa wywozowego UE
1. W okienku akcji kliknij pozycję Faktura.
2. Kliknij opcję Utwórz świadectwo wywozowe.
3. Kliknij przycisk OK.
4. W okienku akcji kliknij pozycję Faktura.
5. Kliknij opcję Wyświetl wystawione świadectwa wywozowe.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]