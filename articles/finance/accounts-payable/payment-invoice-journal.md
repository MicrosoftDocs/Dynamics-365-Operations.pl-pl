---
title: Stosowanie harmonogramu płatności do arkusza faktur
description: Ten artykuł opisuje, jak dodać płatność do dziennika faktur od dostawcy.
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f3ae08ea46be66dd8bf26f7f91bd73f6c5b9192f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863138"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Stosowanie harmonogramu płatności do arkusza faktur

[!include [banner](../includes/preview-banner.md)]

W wersji 10.0.25 aplikacji Microsoft Dynamics 365 Finance harmonogram płatności jest teraz obsługiwany w **Dzienniku faktur od dostawców**.

Aby móc korzystać z tej funkcjonalności, musisz włączyć funkcję **Zastosuj harmonogram płatności do dziennika faktur** w Zarządzaniu funkcjami.

Po włączeniu tej funkcji do strony **Dziennika faktur** dodawane jest nowe pole **Harmonogram płatności**. Kiedy tworzysz linię dziennika faktur, jeśli warunki płatności są zachowane dla sprzedawcy, a warunki płatności są wybrane w harmonogramie płatności, pole **Harmonogram płatności** jest aktualizowane na stronie **Dziennika faktur**.

Możesz zmienić harmonogram płatności, który jest używany, zgodnie z Twoimi wymaganiami biznesowymi. Podczas księgowania dziennika faktur dla dostawców, otwarte transakcje dla dostawców zostaną utworzone zgodnie z harmonogramem płatności.

 - Aby przejrzeć wiele otwartych transakcji sprzedawcy, które zostały wygenerowane z harmonogramu płatności, przejdź do **Rozrachunki z dostawcami \> Faktury \> Otwarte faktury sprzedawcy** i wpisz numer faktury lub konto sprzedawcy.
 - Aby przejrzeć lub skonfigurować harmonogram płatności, przejdź do **Rozrachunki z dostawcami \> Konfiguracja płatności \> Harmonogram płatności**.
 - Aby skonfigurować warunki płatności i przypisać harmonogram płatności, przejdź do **Rozrachunki z dostawcami \> Konfiguracja płatności \> Warunki płatności**.
 - Aby zachować warunki płatności dla danego sprzedawcy, przejdź do **Rozrachunki z dostawcami\> Wszyscy sprzedawcy**, wybierz konto sprzedawcy, a następnie w zakładce **Płatności** ustaw pole **Warunki płatności**.

Funkcja harmonogramu płatności jest również dostępna w procesie **Rejestr faktur dostawcy**. Jeśli w dzienniku rejestru faktur wybrano harmonogram płatności, linie płatności dla wielu kontrahentów **nie** zostaną wygenerowane podczas księgowania rejestru faktur. Linie płatności dla dostawców zostaną wygenerowane, gdy faktura zostanie zatwierdzona.

## <a name="limitation"></a>Ograniczenie

Dla oczekującej faktury dostawcy, jeśli harmonogram płatności znajduje się w nagłówku faktury, dostępna jest zaawansowana strona, która pozwala użytkownikom edytować linie płatności. (Na przykład, użytkownicy mogą edytować termin płatności i wartość dla każdej linii płatności). Linie płatności, które są generowane z dziennika faktur, będą miały wartość z harmonogramu płatności.

Ta funkcjonalność będzie dostępna dla **Dziennika faktur sprzedawcy** i **Faktur oczekujących** w przyszłym wydaniu.
