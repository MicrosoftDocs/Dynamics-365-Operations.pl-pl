---
title: Konfigurowanie instrumentów bankowych i profilów księgowania dla akredytyw
description: Ta procedura prowadzi przez proces tworzenia instrumentu bankowego i profilu księgowania wymaganych do przetwarzania akredytyw.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fe5b2ba43c4fcb4855c742bdb6f8209ebd92d68
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779470"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Konfigurowanie instrumentów bankowych i profilów księgowania dla akredytyw

[!include [banner](../../includes/banner.md)]

Ta procedura prowadzi przez proces tworzenia instrumentu bankowego i profilu księgowania wymaganych do przetwarzania akredytyw. 

Zadania wykorzystują firmę demonstracyjną „USMF”.


## <a name="general-ledger-parameter"></a>Parametr księgi głównej
1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami**.
2. Rozwiń sekcję **Dokument bankowy**.
3. Zaznacz opcję **Włączenie akredytywy importowej**.
4. Zaznacz opcję **Włączenie akredytywy eksportowej**.
5. Kliknij przycisk **Zapisz**.
6. Zamknij stronę.

## <a name="create-bank-facility"></a>Tworzenie instrumentu bankowego
1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami > Ustawienia > Instrumenty bankowe**.
2. Kliknij przycisk **Nowy**.
3. W polu **Grupa instrumentów** nadaj nazwę grupie instrumentów bankowych.
4. W polu **Opis** wprowadź opis grupy instrumentów bankowych.
5. Kliknij przycisk **Zapisz**.
6. Kliknij kartę **Typy instrumentu**.
7. Kliknij przycisk **Nowy**.
8. W polu **Typ instrumentu** wprowadź unikatowy kod.
9. W polu **Opis** wpisz wartość.
10. W polu **Grupa instrumentów** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Na liście znajdź i zaznacz odpowiedni rekord.
12. Na liście kliknij łącze w wybranym wierszu.
13. W polu **Charakter instrumentu** zaznacz charakter instrumentu bankowego.
14. Kliknij przycisk **Zapisz**.
15. Zamknij stronę.

## <a name="bank-posting-profile"></a>Profil księgowania na koncie bankowym
1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami > Ustawienia > Profil księgowania dokumentów bankowych**.
2. Kliknij przycisk **Nowy**.
3. W polu **Numer konta/grupy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. Wybierz konto główne do rozliczeń.
    * To konto będzie używane podczas obliczania prognoz przepływów pieniężnych.  
7. W polu **Konto opłaty** wybierz konto dla transakcji wydatkowych.
8. W polu **Konto marży** wybierz konto dla transakcji dotyczących marży.
    * To konto będzie obciążane podczas księgowania marży początkowej, a uznawane podczas księgowania płatności.  
9. Kliknij przycisk **Zapisz**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
