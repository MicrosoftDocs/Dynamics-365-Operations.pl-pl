---
title: Korzystanie z portali usługi Microsoft Power Apps z modelem danych strony
description: W tym artykule opisano zmiany ról sieci web portali Microsoft Power Apps z powodu modelu danych stron w trybie podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: 8d7a6ae48834ddd5f06f73bfe3129e44d14d86b8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288995"
---
# <a name="using-microsoft-power-apps-portals-with-the-party-data-model"></a>Korzystanie z portali usługi Microsoft Power Apps z modelem danych strony

[!INCLUDE[banner](../../includes/banner.md)]



Wersja rozwiązania Dual-write Application Orchestration 2.0.999.0 a następnie zawiera zmiany modelu danych w tabelach Party i globalna książka adresowa Danych i Kontakt. Zmiany umożliwiają obsługę relacji typu „wiele do wielu”, które obsługują zaawansowane scenariusze biznesowe. Te zmiany nie są obsługiwane przez role sieci web portalu, w tym portal dla klientów, które są wysyłane poza polem lub istniały w środowisku przed zainstalowaniem podwójnego zapisu. Aby role sieci web działały zgodnie z oczekiwaniami, trzeba utworzyć nowe role sieci web przy użyciu nowego modelu danych. 

Podsumowując, sposób interakcji tabel uległ zmianie, ale uprawnienia tabel w portalu klientów nie zostały zmienione. W tym artykule opisano sposób tworzenia nowych ról sieci web, które działają z nowym zaawansowanym modelem danych.

Ten schemat przedstawia relację tabeli **bez** strony globalna książka adresowa modelu danych:

   ![bez modelu strony.](media/without-party-model.PNG)

Ten schemat przedstawia relację tabeli **ze** stroną globalnej książki adresowej modelu danych:

   ![z modelem strony.](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Utwórz nowe uprawnienie do tabeli

Aby utworzyć nowe uprawnienia tabeli, należy wykonać następujące czynności:

1. Zaloguj się do [Power Apps](https://make.powerapps.com) i przejdź do aplikacji.
2. Wybierz aplikację Zarządzanie portalem.
3. Na pasku bocznym wybierz pozycję **Zabezpieczenia > Uprawnienia tabeli**.

    Należy utworzyć trzy nowe uprawnienia:

    + Tabela połączenia **osoba kontaktowa** ze **stroną**
    + Tabela połączenia **Strona** z **Konto**
    + Tabela połączenia **Konto** z **Zamówienie**

4. Utwórz i zapisz nowe uprawnienie dla kontaktu do połączenia ze stroną, ustawiając następujące parametry:

    + **Nazwa**: tabela połączenia **Strona** z **Konto** (lub wybór użytkownika)
    + **Nazwa tabeli**: msdyn_contactforparty
    + **Witryna**: Portal klienta
    + **Zakres:** Osoba kontaktowa
    + **Uprawnienia**: zaznacz wszystkie
    + **Role sieci Web:** uwierzytelnieni użytkownicy, przedstawiciel odbiorcy (lub wybór użytkownika)

5. Utwórz i zapisz nowe uprawnienie dla kontaktu do połączenia ze stroną, ustawiając następujące parametry:

    + **Nazwa:** stroną połączonego konta (lub do wyboru)
    + **Nazwa tabeli**: konto
    + **Witryna**: Portal klienta
    + **Zakres**: nadrzędny
    + **Uprawnienia**: zaznacz wszystkie
    + **Uprawnienie tabeli nadrzędnej**: połączenie ze stroną

6. Utwórz i zapisz nowe uprawnienie dla konta do połączenia z zamówieniem, ustawiając następujące parametry:

    + **Nazwa:** konto do połączenia z zamówieniem (lub do wyboru)
    + **Nazwa tabeli**: zamówienie sprzedaży
    + **Witryna**: Portal klienta
    + **Zakres**: nadrzędny
    + **Uprawnienia**: zaznacz wszystkie
    + **Uprawnienie tabeli nadrzędnej**: połączenie strona do konta

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
