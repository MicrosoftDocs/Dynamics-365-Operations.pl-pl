---
title: Tworzenie grup uprawnień dla punktu sprzedaży
description: W tym artykule wyjaśniono, jak utworzyć grupę uprawnień dla punktu sprzedaży.
author: scott-tucker
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 009f311dd00f48edb8c0f6622f0a5107881ab2ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905431"
---
# <a name="create-pos-permission-groups"></a>Tworzenie grup uprawnień dla punktu sprzedaży

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak utworzyć grupę uprawnień dla punktu sprzedaży. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USRT. To zadanie jest przeznaczone dla roli Kierownik ds. operacyjnych handlu.

1. W okienku nawigacji przejdź do **Moduły > Retail i Commerce > Pracownicy etatpwi > Grupy uprawnień**.
2. Wybierz pozycję **Nowy**.
3. W polu **Identyfikator grupy uprawnień dla punktu sprzedaży** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. W polu **Wyświetlanie wpisów zegara** wybierz opcję **Tak**. Teraz można włączyć lub wyłączyć różne uprawnienia w grupie uprawnień dla punktu sprzedaży. Dla niektórych uprawnień można ustawić wartość, która będzie używana do oceny, czy użytkownik punktu sprzedaży może wykonać czynność. W tym podręczniku po zadaniach włączono kilka uprawnień, które można przyznać kasjerowi.  
6. W polu **Zezwalaj na tworzenie zamówienia** wybierz opcję **Tak**.
7. W polu **Zezwalaj na edytowanie zamówienia** wybierz opcję **Tak**.
8. W polu **Zezwalaj na pobieranie zamówienia** wybierz opcję **Tak**.
9. W polu **Dopuszczaj zmianę hasła** wybierz opcję **Tak**.
10. W polu **Zezwalaj na ukrycie raportu podczas zamknięcia kasy** wybierz opcję **Tak**.
11. Wybierz opcję **Zapisz**. Gdy zmiany zostaną zapisane, należy uruchomić harmonogram dystrybucji do pracowników, aby wysłać zmiany do kanałów handlu. 
12. W okienku nawigacji przejdź do **Moduły > Zasoby ludzkie > Zadania > Zadania**.
13. Następnie przypiszemy grupę uprawnień dla punktu sprzedaży do zadania. Na liście znajdź i zaznacz odpowiedni rekord.
14. Wybierz opcję **Edycja**.
15. Rozwiń sekcję **Klasyfikacja zadania** .
16. W polu Grupa uprawnień dla punktu sprzedaży wprowadź lub wybierz wartość. Wszyscy pracownicy na Stanowiskach dla tego zadania będą używali ustawień tej grupy uprawnień punktu sprzedaży, chyba że odnośne uprawnienia zostały zastąpione pracownikom na poziomie ich Stanowisk.  
17. Wybierz opcję **Zapisz**. Gdy zmiany zostaną zapisane, należy uruchomić harmonogram dystrybucji do pracowników, aby wysłać zmiany do kanałów.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]