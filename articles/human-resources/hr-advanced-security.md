---
title: Ograniczanie dostępu do pracowników według osoby prawnej
description: W tym artykule opisano, jak skonfigurować dostęp pracownika według firmy.
author: twheeloc
ms.date: 11/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadd2c34d31bbd259255596c06a8e7517f7a774b
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780396"
---
# <a name="restrict-access-to-workers-by-legal-entity"></a>Ograniczanie dostępu do pracowników według osoby prawnej

W tym artykule opisano, jak skonfigurować dostęp pracownika według firmy.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Pracownicy są zatrudnieni w firmach. Oto kilka przykładów:

- Aaron Con jest zatrudniony w firmie USSI.
- Ahmed Barnett jest zatrudniony w firmie USMF.
- Alicia Tesber jest zatrudniona w firmach GLSI i USMF.

W zależności od roli użytkownika w firmie może być wymagane dostęp do wyświetlania wszystkich pracowników w różnych firmach. Alternatywnie może być konieczne ograniczenie użytkownika, aby mógł wyświetlać tylko pracowników w firmie, do której ma dostęp. Aby określić, którzy pracownicy mogą być wyświetlani przez użytkownika, wybierz opcję **Ogranicz dostęp do parametru** informacji o pracowniku na stronie **Udostępniane parametry zasobów ludzkich**.

Na przykład użytkownik ma dostęp do strony **Pracownik** i ma dostęp tylko do firmy USMF. W takim przypadku użytkownik może wyświetlić następujące informacje dotyczące pracowników z poprzedniej listy:

- Jeśli funkcja ograniczania dostępu do informacji o pracownikach nie jest włączona, użytkownik może przeglądać informacje dotyczące Aarona, Ahmeda i Alicii.
- Jeśli ta funkcja jest włączona, użytkownik może przeglądać informacje tylko dla Alicii i Ahmeda, ponieważ są oni również zatrudnieni w firmie USMF.

Wyświetlane informacje różnią się w zależności od wybranej aplikacji.

## <a name="dynamics-365-human-resources-stand-alone"></a>Samodzielny Dynamics 365 Human Resources

Jeśli funkcja ograniczania dostępu do informacji o pracownikach jest włączona, użytkownik z ograniczonym dostępem zobaczy pustą wartość na niektórych listach zawierających nazwisko pracownika.

Na przykład użytkownik, który ma dostęp tylko do firmy USMF, napotka następujące zachowanie:

- Na liście **Aktywne stanowiska** kolumna **Pracownik** będzie pusta dla stanowiska Aarona, ponieważ użytkownik nie ma dostępu do pracowników w firmie USSI.
- Jeśli użytkownik będzie przejść do szczegółów w imieniu pracownika, pojawi się pusta strona **Pracownik**.

## <a name="dynamics-365-human-resources-on-finance-infrastructure"></a>Dynamics 365 Human Resources na infrastrukturze Finance

Jeśli funkcja ograniczania dostępu do informacji o pracownikach jest włączona, użytkownik z ograniczonym dostępem zobaczy nazwisko pracownika na niektórych listach.

Na przykład użytkownik, który ma dostęp tylko do firmy USMF, napotka następujące zachowanie:

- Na liście **stanowisk aktywnych** w kolumnie **Pracownik** będzie wyświetlane imię i nazwisko Ma. Jeśli użytkownik umieść wskaźnik myszy na nazwisku pracownika, zostaną wyświetlone tylko imię i nazwisko.
- Jeśli użytkownik będzie przejść do szczegółów w imieniu pracownika, pojawi się pusta strona **Pracownik**.

> [!TIP]
> Jeśli korzystasz z infrastruktury Dynamics 365 Human resources on Finance i chcesz, aby użytkownicy z ograniczonym dostępem widzieli puste wartości dla nazw pracowników, możesz dodać uprawnienie bezpieczeństwa **Ogranicz dostęp do pracowników** do ról użytkowników na stronie **Konfiguracji zabezpieczeń**.

Po włączeniu tej funkcji należy wykonać kilka dodatkowych czynności, aby ustawić uprawnienia dla każdego użytkownika, którego widok musi być ograniczony.

1. Na stronie **Użytkownicy** wybierz użytkownika.
2. Umożliwia wybór roli użytkownika. Opcja **Przypisz organizacje** staje się dostępna.
3. Wybierz **Przypisz organizacje**.
4. Na nowej stronie wybierz **Przyznaj dostęp indywidualnie określonym organizacjom**, a następnie wybierz organizacje, do których użytkownik powinien mieć dostęp.
5. Powtórz kroki od 2 do 4 dla każdej innej roli użytkownika, w tym dla roli użytkownika systemu.

> [!NOTE]
> Firmy, do których użytkownik ma dostęp, muszą się dopasować do wszystkich ról użytkownika.
