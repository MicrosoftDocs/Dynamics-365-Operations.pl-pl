---
title: Konfigurowanie podwójnego zapisu z usług Lifecycle Services
description: W tym temacie opisano sposób skonfigurowania połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103576"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Konfigurowanie podwójnego zapisu z usług Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano sposób włączenia połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Wymagania wstępne

Integrację Power Platform należy zakończyć w sposób opisany w poniższych tematach:

+ [Integracja Power Platform — włącz podczas wdrażania środowiska](../../power-platform/overview.md#enable-during-environment-deployment)
+ [Integracja Power Platform — włącz po wdrażaniu środowiska](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Wskazówki dotyczące konfigurowania podwójnego zapisu w środowiskach Dataverse

Aby skonfigurować podwójny zapis ze strony **Szczegóły środowiska** usługi LCS, należy wykonać następujące kroki:

1. Na stronie **Szczegóły środowiska** rozwiń sekcję **Integracja Power Platform**.

2. Wybierz przycisk **Aplikacji podwójnego zapisu**.

    ![Integracja z programem Power Platform](media/powerplat_integration_step2.png)

3. Przejrzyj warunki, a następnie zaznacz pole wyboru **Konfiguruj**.

4. Wybierz przycisk **OK**, aby kontynuować.

5. Postęp można monitorować, okresowo odświeżając stronę szczegółów środowiska. Konfiguracja zwykle trwa 30 minut lub dłużej.  

6. Po zakończeniu konfigurowania pojawi się komunikat informujący o pomyślnym zakończeniu procesu lub niepowodzeniu jego wykonania. Jeśli konfiguracja nie powiodła się, wyświetlany jest powiązany komunikat o błędzie. Przed przejściem do następnego kroku należy poprawić wszystkie błędy.

7. Wybierz **Łącze do środowiska Power Platform**, aby utworzyć łącze między Dataverse a bazami danych bieżącego środowiska. Ta konfiguracja zwykle trwa 5 minut lub mniej.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Łącze do środowiska Power Platform":::

8. Po zakończeniu łączenia jest wyświetlane hiperłącze. Użyj łącza, aby zalogować się do obszaru administracji podwójnego zapisu w środowisku Finance and Operations. Istnieje możliwość skonfigurowania mapowań encji.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Wskazówki dotyczące konfigurowania podwójnego zapisu dla istniejącego środowiska Dataverse

Aby skonfigurować podwójny zapis dla istniejącego środowiska Dataverse, musisz utworzyć [zgłoszenie](../../lifecycle-services/lcs-support.md) do pomocy technicznej firmy Microsoft. Zgłoszenie musi zawierać następujące informacje:

+ Identyfikator środowiska Finance and Operations.
+ Twoja nazwa środowiska z usługi Lifecycle Services.
+ Identyfikator organizacji Dataverse lub identyfikator środowiska Power Platform z centrum administracyjnego Power Platform. W zgłoszeniu poproś, aby identyfikator był wystąpieniem używanym do integracji Power Platform.

> [!NOTE]
> Nie można odłączyć środowisk za pomocą usługi LCS. Aby rozłączyć środowisko, Otwórz obszar roboczy **integracji danych** w środowisku Finance and Operations, a następnie wybierz opcję **Rozłącz**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
