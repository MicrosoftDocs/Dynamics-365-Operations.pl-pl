---
title: Konfigurowanie podwójnego zapisu z usług Lifecycle Services
description: W tym temacie opisano sposób skonfigurowania połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 08/03/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 825d6a4b3462077d0f4b3f4275792ea0fe5152df
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063679"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Konfigurowanie podwójnego zapisu z usług Lifecycle Services

[!include [banner](../../includes/banner.md)]



W tym temacie opisano sposób włączenia połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Wymagania wstępne

Integrację Power Platform należy zakończyć w sposób opisany w poniższych tematach:

+ [Integracja Power Platform — włącz podczas wdrażania środowiska](../../power-platform/enable-power-platform-integration.md#enable-during-deploy)
+ [Integracja Power Platform — włącz po wdrożeniu środowiska](../../power-platform/enable-power-platform-integration.md#enable-after-deploy)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Wskazówki dotyczące konfigurowania podwójnego zapisu w środowiskach Dataverse

Aby skonfigurować podwójny zapis ze strony **Szczegóły środowiska** usługi LCS, należy wykonać następujące kroki:

1. Na stronie **Szczegóły środowiska** rozwiń sekcję **Integracja Power Platform**.

2. Wybierz przycisk **Aplikacji podwójnego zapisu**.

    ![Integracja z programem Power Platform.](media/powerplat_integration_step2.png)

3. Przejrzyj warunki, a następnie zaznacz pole wyboru **Konfiguruj**.

4. Wybierz przycisk **OK**, aby kontynuować.

5. Postęp można monitorować, okresowo odświeżając stronę szczegółów środowiska. Konfiguracja zwykle trwa 30 minut lub dłużej.  

6. Po zakończeniu konfigurowania pojawi się komunikat informujący o pomyślnym zakończeniu procesu lub niepowodzeniu jego wykonania. Jeśli konfiguracja nie powiodła się, wyświetlany jest powiązany komunikat o błędzie. Przed przejściem do następnego kroku należy poprawić wszystkie błędy.

7. Wybierz **Łącze do środowiska Power Platform**, aby utworzyć łącze między Dataverse a bazami danych bieżącego środowiska. Ta konfiguracja zwykle trwa 5 minut lub mniej.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Łącze do środowiska Power Platform.":::

8. Po zakończeniu łączenia jest wyświetlane hiperłącze. Użyj łącza, aby zalogować się do obszaru administracji podwójnego zapisu w środowisku Finanse i Działania. Istnieje możliwość skonfigurowania mapowań encji.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Wskazówki dotyczące konfigurowania podwójnego zapisu dla istniejącego środowiska Dataverse

Aby skonfigurować podwójny zapis dla istniejącego środowiska Dataverse, musisz utworzyć [zgłoszenie](../../lifecycle-services/lcs-support.md) do pomocy technicznej firmy Microsoft. Zgłoszenie musi zawierać następujące informacje:

+ Twój identyfikator środowiska Finanse i Działania.
+ Twoja nazwa środowiska z usługi Lifecycle Services.
+ Identyfikator organizacji Dataverse lub identyfikator środowiska Power Platform z centrum administracyjnego Power Platform. W zgłoszeniu poproś, aby identyfikator był wystąpieniem używanym do integracji Power Platform.

> [!NOTE]
> Nie można odłączyć środowisk za pomocą usługi LCS. Aby rozłączyć środowisko, Otwórz obszar roboczy **integracji danych** w środowisku Finanse i Działania, a następnie wybierz opcję **Rozłącz**.

## <a name="linking-mismatch"></a>Niezgodność łączenia

Jest możliwe, że środowisko LCS jest połączone z jednym wystąpieniem Dataverse, podczas gdy środowisko podwójnego zapisu jest połączone z innym wystąpieniem Dataverse. Ta niezgodność łączenia może spowodować nieoczekiwane zachowanie i może skończyć się wysyłaniem danych do niewłaściwego środowiska. Zalecane środowisko do użycia dla podwójnego zapisu jest tym, który jest tworzone w ramach integracji Power Platform. Długoterminowo będzie to jedyny sposób, aby ustanowić połączenie między środowiskami.

Jeśli Twoje środowisko ma niedopasowane łączenie, LCS wyświetla ostrzeżenie na stronie szczegółów środowiska podobne do „Microsoft wykrył, że Twoje środowisko jest połączone poprzez podwójny zapis do innego miejsca docelowego niż określone w integracji Power Platform, co nie jest zalecane”:

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="niedopasowane łącze integracyjne Power Platform.":::

Jeśli wystąpi ten błąd, dostępne są dwie opcje, w zależności od potrzeb:

+ [Odłącz i ponownie połącz środowiska podwójnego zapisu (Resetowanie lub zmienianie łączenia)](relink-environments.md#scenario-reset-or-change-linking) zgodnie z informacjami na stronie szczegółów środowiska LCS. Jest to idealna opcja, ponieważ można go uruchomić bez pomocy technicznej firmy Microsoft.  
+ Jeśli chcesz zachować łącze w podwójnym zapisie, możesz poprosić o pomoc pomocy technicznej firmy Microsoft, aby zmienić integrację Power Platform, aby użyć istniejącego środowiska Dataverse, jak udokumentowano w poprzedniej sekcji.  

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
