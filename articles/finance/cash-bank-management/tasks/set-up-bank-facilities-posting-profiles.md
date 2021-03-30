---
title: Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń
description: To zadanie tworzy instrument bankowy oraz profil księgowania, który jest potrzebny do przetwarzania poręczenia.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0b72a412aaaf1c70b4414d00e99b923380f7dd86
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225304"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń

[!include [banner](../../includes/banner.md)]

To zadanie tworzy instrument bankowy oraz profil księgowania, który jest potrzebny do przetwarzania poręczenia.



W zadaniu wykorzystano firmę demonstracyjną USMF. 




## <a name="general-ledger-parameter"></a>Parametr księgi głównej
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.
2. Rozwiń sekcję Dokument bankowy.
3. Zaznacz opcję Włączanie poręczenia.
4. W polu Arkusz transakcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
6. Na liście kliknij łącze w wybranym wierszu.
7. Kliknij kartę Sekwencje numerów.
    * Zdefiniuj kod sekwencji numeracji odwołań do numeru poręczenia i numeru transakcji poręczenia.  
8. Kliknij przycisk Zapisz.
9. Zamknij stronę.

## <a name="create-bank-facility"></a>Tworzenie instrumentu bankowego
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Instrumenty bankowe.
2. Kliknij przycisk Nowy.
3. W polu Grupa instrumentów wprowadź nazwę grupy instrumentów bankowych dla transakcji poręczenia.
4. Wypełnij pole Opis.
5. Kliknij przycisk Zapisz.
6. Kliknij kartę Typy instrumentu.
7. Kliknij przycisk Nowy.
8. W polu Typ instrumentu wprowadź nazwę typu instrumentów bankowych, który jest powiązany z umową instrumentu bankowego.
9. W polu Opis wpisz wartość.
10. W polu Grupa instrumentów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Na liście znajdź i zaznacz odpowiedni rekord.
12. Na liście kliknij łącze w wybranym wierszu.
13. W polu Charakter instrumentu wybierz opcję.
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.

## <a name="bank-posting-profile"></a>Profil księgowania na koncie bankowym
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Profil księgowania dokumentów bankowych.
2. Kliknij przycisk Nowy.
3. W polu Numer konta/grupy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Konto rozliczeniowe wybierz konto główne do rozliczenia.
7. W polu Konto opłaty wybierz konto dla transakcji wydatkowych.
8. W polu Konto marży wybierz konto dla transakcji dotyczących marży.
9. W polu Konto likwidacji wybierz konto likwidacji dla transakcji poręczenia. 
10. Kliknij przycisk Zapisz.
11. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]