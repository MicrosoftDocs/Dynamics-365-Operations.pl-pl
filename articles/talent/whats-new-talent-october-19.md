---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (16 października 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7da597a682006cddb44ff9354813b07c15c1a449
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "305841"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-19-2018"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (19 października 2018 r.)

[!include[banner](includes/banner.md)]

**Kompilacja 8.1.1067**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.

## <a name="allow-managers-to-update-time-off-requests"></a>Zezwalanie menedżerom na aktualizowanie wniosków o czas wolny

Wnioski pracowników o czas wolny mogą wymagać aktualizacji po zatwierdzeniu za pośrednictwem przepływu pracy. W wielu przypadkach menedżer dokonuje tych aktualizacji w imieniu pracownika. Ta nowa funkcja umożliwia menedżerom aktualizowanie lub anulowanie wniosków o czas wolny w imieniu podległych pracowników. Ta funkcja jest kontrolowana przez parametr **Praca w imieniu**, który można ustawić na stronie **Parametry zasobów ludzkich**. 
 
## <a name="allow-hr-to-update-time-off-requests"></a>Zezwalanie działowi kadr na aktualizowanie wniosków o czas wolny

Wnioski pracowników o czas wolny mogą wymagać aktualizacji przez dział kadr, mimo iż wcześniej zostały zatwierdzone przy użyciu przepływu pracy. Ta funkcja umożliwia użytkownikom z działu kadr aktualizowanie wniosków o czas wolny. Funkcja jest włączana w obszarze roboczym **Osoby** oraz na stronie **Pracownik** za pomocą nowej opcji o nazwie **Wyświetl czas wolny**. Na tych stronach użytkownicy z działu kadr mogą przeglądać wnioski i aktualizować operacje przyznania czasu wolnego, podobnie jak mogą to robić menedżerowie.

Dostęp do tej funkcjonalności jest kontrolowany przez następujący obowiązek zabezpieczeń:
- Obowiązek: Obsługa procesów urlopów i nieobecności specyficznych dla pracownika.
- Uprawnienie: Obsługa wniosków o urlopy i nieobecności dla wszystkich pracowników.

## <a name="other-changes"></a>Inne zmiany
Następujące aktualizacje zostały wprowadzone w tej wersji:
- Zmieniono czynności zatrudniania pracownika, tak aby nie „zawieszał się” w stanie **Przepływ pracy zakończony**.
- Teraz można utworzyć rekord zatrudnienia bez daty rozpoczęcia zatrudnienia.
- W aplikacji Dynamics 365 for Talent data rejestracji na szkolenie wyświetlane w oknie Samoobsługa pracownika etatowego teraz jest korygowana o strefę czasową.
- Pliki programu Excel można importować wielokrotnie za pomocą jednostki **Pracownik etatowy** bez powodowania błędów.

## <a name="known-issue"></a>Znany problem

- **Problem**: Podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. 
- **Obejście:** Przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte. Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone. (Ten problem zostanie rozwiązany w następnej aktualizacji platformy).
