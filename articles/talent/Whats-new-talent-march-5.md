---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (5 marca 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c7ee8f4cf14197d6bd4549741058fc5fe95ae55d
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026677"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-5-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (5 marca 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="extending-option-sets-in-attract"></a>Rozszerzanie zestawów opcji w Attract

W Attract jest wiele pól będących zestawami opcji w Common Data Service. Wprowadzono nowe możliwości rozszerzania zestawów opcji, począwszy od pola przyczyny **odrzucenia**, pola **Typ zatrudnienia** i pola **typu stażu pracy**.

> [!IMPORTANT]
> Dodawanie oferty pracy do funkcji LinkedIn wymaga stosowania pól **Typ zatrudnienia** i **typu stażu pracy** na stronie **Szczegóły stanowiska**. Domyślne wartości tych pól nie są obsługiwane przez LinkedIn i są wyświetlane, gdy oferta jest publikowana. Jeśli publikujesz ofertę pracy na LinkedIn i zmienisz istniejące zestawy wartości dla tych pól, oferta zostanie opublikowana, ale LinkedIn nie wyświetli wartości niestandardowych **Typ zatrudnienia** i **typu stażu pracy**.

## <a name="changes-in-onboarding"></a>Zmiany we wdrażaniu do pracy

### <a name="private-preview-for-onboard-teams"></a>Podgląd prywatny zespołów wdrażania do pracy
Teraz można łatwo udostępniać i współpracować w szablonach w całej organizacji. Aby uzyskać więcej informacji, zobacz [udostępnienia najlepszych praktyk w całej organizacji przy pomocy zespołów wdrażania do pracy](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).

### <a name="private-preview-for-assignee-placeholders"></a>Prywatny podgląd symboli zastępczych wykonawcy
Szablony można wzbogacać przez przypisanie działania do ról, a nie osobom. Role są następnie przypisywane do osób w momencie utworzenia przewodnika. Aby uzyskać więcej informacji, zobacz [tworzenie Przewodnika po administracji przez przypisanie działania do ról](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
**Kompilacja 8.1.2178**

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a>Konfigurowanie przepływu pracy do automatycznego zatwierdzania lub śledzenia przepływu pracy, gdy HR lub kierownik linii prześle albo zaktualizuje żądania czasu wolnego
Dodano nowe warunki przepływu pracy zezwalające na automatyczne zatwierdzanie żądań urlopów przesłanych przez kierownika lub dział HR. Jednym ze sposobów korzystania z tego automatycznego zatwierdzania dla przepływu pracy jest włączenie automatycznej akcji w zatwierdzaniu przepływu pracy.

Do dodanych warunków należą:

- Przesłane przez: używany do oceny identyfikatora systemowego użytkownika, który przesłał żądanie do przepływu pracy.
- Przesłane w imieniu — używany do oceny, czy wniosek o urlop został przesłany w imieniu pracownika skojarzonego z wnioskiem.
- Przesłane przez zasoby ludzkie — używany do oceny, czy użytkownik systemu, który przesłał wniosek do przepływu pracy jest rolą modułu Zasoby ludzkie.
- Przesłane przez menedżera — używany do oceny, czy użytkownik, który przesłał wniosek o urlop do przepływu pracy, jest menedżerem linii pracownika skojarzonego z wnioskiem.

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a>Włącz stałe wynagrodzenie dla przyszłych przypisań stanowisk
Jest to typowe dla pracowników, którzy dołączają do organizacji w przyszłości. Ta zmiana umożliwia definiowanie stałych wynagrodzeń dla pracowników z przyszłym przypisaniem stanowisk.

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a>Pola Pozycja listy płac są puste podczas edytowania stanowiska
Wraz z tą zmianą, podczas żądania zmiany istniejących stanowisk, pola listy zostaną domyślnie wypełnione obecnymi wartościami.

### <a name="other-miscellaneous-bug-fixes"></a>Inne dodatkowe poprawki błędów
Inne niewielkie poprawki są dołączone do tej wersji.

### <a name="upgrade-to-common-data-service"></a>Uaktualnianie do rozwiązania Common Data Service
Zbliżają się terminy uaktualniania do Common Data Service dla aplikacji. Zaloguj się do Centrum administracyjnego usługi PowerApps, aby określić, czy baza danych wymaga uaktualnienia. Aby uzyskać więcej informacji dotyczących terminów i niezbędne kroki w celu uaktualnienia, zobacz [uaktualnienia do Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="coming-soon"></a>Wkrótce

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Zaawansowane zabezpieczenia wynagrodzeń (stałe i zmienne)
W wielu organizacjach menedżerowie ds. wynagrodzeń i świadczeń mają dostęp tylko do określonych rekordów wynagrodzeń, takich jak rekordy dla kadry zarządzającej i pracowników regionalnych. W przypadku tej zmiany można zarządzać różnymi planami wynagrodzeń dla różnych grup pracowników w organizacji. Stałe i zmienne plany mogą mieć przypisane role zabezpieczeń, które będą określały dostęp do planów i danych pracowników związanych z planami, takich jak rekordy płac i premii. Tylko role z danym dostępem mogą przetwarzać wynagrodzenia dla tych pracowników.

###  <a name="platform-update-24-for-finance-and-operations"></a>Aktualizacja Platform update 24 dla Finance and Operations
Aby uzyskać dodatkowe szczegółowe informacje dotyczące 24. aktualizacji platformy dla Finance and Operations, zobacz [Nowości i zmiany w 24. aktualizacji platformy Finance and Operations (marzec 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).
