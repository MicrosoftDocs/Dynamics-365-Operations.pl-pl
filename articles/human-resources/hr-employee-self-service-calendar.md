---
title: Tworzenie kalendarza zespołu
description: W programie Dynamics 365 Human Resources można wyświetlać i tworzyć kalendarze zespołu.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 07c7f1303238fe61d70be26ec5a198f1ac489090
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790771"
---
# <a name="view-team-and-company-calendars"></a>Wyświetlanie kalendarzy zespołów i firm

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W programie Dynamics 365 Human Resources można wyświetlać kalendarze zespołów i firmy. W kalendarzach zespołów są wyświetlani tylko bezpośredni podwładni zdefiniowani w hierarchii liniowej.

## <a name="view-your-team-calendar-as-an-employee"></a>Wyświetlanie kalendarza zespołu jako pracownik etatowy

1. W obszarze roboczym **Samoobsługa pracownika etatowego** wybierz opcję **Kalendarz nieobecności zespołu** w obszarze **Podsumowanie**.

## <a name="view-your-team-calendar-as-a-manager"></a>Wyświetlanie kalendarza zespołu jako menedżer

1. W obszarze roboczym **Samoobsługa pracownika etatowego** wybierz opcję **Mój zespół**.

2. Wybierz kolejno opcje **Urlopy i nieobecności** oraz **Wyświetl kalendarz nieobecności menedżera**.

Menedżerowie mogą również uzyskać dostęp do kalendarza zespołowego z **Czas oczekiwania na nierealizację żądania dla mojego zespołu**, **Zatwierdzony czas wolny** i **Żądania czasu wolnego**. 

## <a name="view-a-company-calendar"></a>Wyświetlanie kalendarza firmy

Osoby, które mają role w module Human Resources, mogą wyświetlać kalendarze firmy. W kalendarzach firmy są wyświetlane wszyscy pracownicy. Domyślnie w kalendarzu jest wyświetlana data dzisiejsza plus 28 dni, ale można zmienić zakres dat. Kalendarz można również filtrować według kryterium **Nazwa**, **Numer pracownika** i **Typ urlopu**.

1. W obszarze roboczym **Urlopy i nieobecności** wybierz opcję **Łącza**.

2. Wybierz opcję **Kalendarz urlopów i nieobecności**.

Role w Human resources mogą również uzyskiwać dostępdo kalendarza firmowego z **Wnioski o urlopy i nieobecności**, **Zatwierdzony czas wolny** i **Żądania czasu wolnego**. 

Kalendarze zawierają teraz dodatkowe filtry i opcje. Wszystkie kalendarze zawierają opcje widoku dla:

- Wniosków zatwierdzonych
- Oczekujące wnioski
- Pracowników z wnioskami urlopowymi
- Pracowników bez wniosków urlopowych
- Urodzin pracowników
- Wnioski dotyczące czasu wolnego 
- Wnioski o nieobecność

Konfiguracja kalendarza w parametrach urlopu i nieobecności określa dostępne opcje widoku.

Kalendarze można również filtrować według kierowników lub działów. Przypisanie stanowiska głównego określa pracowników, którzy są wyświetlani po ustawieniu tych filtrów. 

>[!IMPORTANT]
>Funkcja wyświetlania urlopów i nieobecności w różnych firmach jest obecnie dostępna w wersji zapoznawczej. Należy ją włączyć w środowisku **piaskownicy**. Aby uzyskać więcej informacji na temat włączania funkcji w wersji zapoznawczej, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).<br><br>
>Następnie należy włączyć funkcję w **Udostępnianych parametrach zasobów ludzkich**, aby wyświetlić filtr firmy w kalendarzach. Aby uzyskać więcej informacji, zobacz [Konfigurowanie parametrów urlopu i nieobecności](hr-leave-and-absence-parameters.md).<br><br>
>Kalendarz można filtrować według firm. Aby wyświetlić wszystkich pracowników niezależnie od firmy, należy wyczyścić pole filtru i nacisnąć Enter. 

Aby uzyskać informacje na temat ustawień kalendarza, zobacz [Konfigurowanie parametrów kalendarza](hr-leave-and-absence-parameters.md?configure-calendar-parameters).



[!INCLUDE[footer-include](../includes/footer-banner.md)]