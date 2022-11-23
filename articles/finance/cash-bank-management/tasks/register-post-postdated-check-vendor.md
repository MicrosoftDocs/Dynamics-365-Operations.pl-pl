---
title: Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy
description: Za pomocą załącznika arkusza można zarejestrować szczegóły czeku postdatowanego przed wysłaniem go dostawcy.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 312f7c58352e3cb86c22f8c34b1b6c11456c0083
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779487"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a>Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy

[!include [banner](../../includes/banner.md)]

Za pomocą załącznika arkusza można zarejestrować szczegóły czeku postdatowanego przed wysłaniem go dostawcy. Można także zaksięgować postdatowany czek i wygenerować transakcje finansowe. Przed zarejestrowaniem i zaksięgowaniem postdatowanego czeku od dostawcy należy wykonać następujące zadanie: 

Konfigurowanie czeków postdatowanych na stronie **Zarządzanie gotówką i bankami**. 

Rolą w tym przewodniku po zadaniach jest Skarbnik. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami > Płatności > Arkusz płatności**.
2. Kliknij przycisk **Nowy**.
3. W polu **Nazwa** wpisz „VendPay”.
4. Kliknij przycisk **Wiersze**.
5. W polu **Konto** podaj żądane wartości.
6. Na liście oznacz wybrany wiersz.
7. W polu **Debet** wpisz liczbę.
8. W polu **Metoda płatności** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wybierz metodę płatności dla czeku postdatowanego.  
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście kliknij łącze w wybranym wierszu.
11. Kliknij kartę **Czeki postdatowane**.
12. W polu **Numer czeku** wpisz wartość.
    * Wprowadź lub zmodyfikuj numer czeku postdatowanego.  
13. W polu **Nazwa banku** wystawiającego wpisz wartość.
    * Wprowadź dane banku wystawcy.  
14. Kliknij kartę **Lista**.
15. Kliknij przycisk **Księguj**.
16. Zamknij stronę.
17. Kliknij kartę Czeki postdatowane.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
