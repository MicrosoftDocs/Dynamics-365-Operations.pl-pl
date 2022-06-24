---
title: Tworzenie kalendarza zespołu
description: W programie Dynamics 365 Human Resources można wyświetlać i tworzyć kalendarze zespołu.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6dffcb265030922e5134cfab1310027be43d87ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904167"
---
# <a name="view-team-and-company-calendars"></a>Wyświetlanie kalendarzy zespołów i firm

>[!Important]
>Funkcjonalność opisana w tym artykule jest obecnie dostępna dla klientów samodzielnej wersji Dynamics 365 Human Resources. Część lub całość tej funkcjonalności będzie dostępna w ramach przyszłego wydania infrastruktury Finance po wydaniu wersji Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W programie Dynamics 365 Human Resources można wyświetlać kalendarze zespołów i firmy. W kalendarzach zespołów są wyświetlani tylko bezpośredni podwładni zdefiniowani w hierarchii liniowej.

## <a name="view-your-team-calendar-as-an-employee"></a>Wyświetlanie kalendarza zespołu jako pracownik etatowy

- W obszarze roboczym **Samoobsługa pracownika etatowego** wybierz opcję **Kalendarz nieobecności zespołu** w obszarze **Podsumowanie**.

## <a name="view-your-team-calendar-as-a-manager"></a>Wyświetlanie kalendarza zespołu jako menedżer

1. W obszarze roboczym **Samoobsługa pracownika etatowego** wybierz opcję **Mój zespół**.

2. Wybierz kolejno opcje **Urlopy i nieobecności** oraz **Wyświetl kalendarz nieobecności menedżera**.

Menedżerowie mogą również uzyskać dostęp do kalendarza zespołowego z **Czas oczekiwania na nierealizację żądania dla mojego zespołu**, **Zatwierdzony czas wolny** i **Żądania czasu wolnego**. 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>Wyświetl kalendarz menedżera nieobecności jako menedżer nieobecności

> [!NOTE]
> Aby wyświetlić kalendarz menedżera nieobecności, należy najpierw włączyć funkcję **Menedżer nieobecności (wersja zapoznawcza)**, aby zarządzać funkcjami zarządzania urlopami w zarządzaniu funkcjami. Aby uzyskać informacje na temat włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

Użytkownicy pełniący rolę menedżera nieobecności mogą przeglądać prośby o urlop w swoim kalendarzu. Wykonaj poniższe czynności, aby uzyskać dostęp do kalendarza urlopów.

1. W obszarze roboczym **Samoobsługa pracownika** wybierz opcję **Menedżer urlopów**, a następnie **Kalendarz menedżera nieobecności**.

2. W polu **Data** wpisz żądane daty.

3. W razie potrzeby zaktualizuj opcje widoku.

Kalendarz menedżera nieobecności zawiera wszystkie rekordy pracowników, którzy podlegają menedżerowi nieobecności w hierarchii urlopów.

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

Konfiguracja kalendarza w **parametrach urlopu i nieobecności** określa dostępne opcje widoku.

Kalendarze można również filtrować według kierowników lub działów. Przypisanie stanowiska głównego określa pracowników, którzy są wyświetlani po ustawieniu tych filtrów. 

> [!IMPORTANT]
> Funkcję **widoku urlopów między firmami** można włączyć w zarządzaniu funkcjami. Następnie musisz włączyć funkcję na stronie **Udostępnianych parametrach zasobów ludzkich**, aby wyświetlać filtr podmiotu prawnego w kalendarzach. Aby uzyskać więcej informacji, zobacz [Konfigurowanie parametrów urlopu i nieobecności](hr-leave-and-absence-parameters.md).
> 
> Kalendarz można filtrować według firm. Aby wyświetlić wszystkich pracowników, niezależnie od firmy, wyczyść pole filtru, a następnie wybierz **Enter**. 

Aby uzyskać informacje na temat ustawień kalendarza, zobacz [Konfigurowanie parametrów kalendarza](hr-leave-and-absence-parameters.md?configure-calendar-parameters).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
