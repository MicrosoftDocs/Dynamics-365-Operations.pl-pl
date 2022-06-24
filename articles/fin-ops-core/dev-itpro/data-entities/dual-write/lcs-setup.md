---
title: Konfigurowanie podwójnego zapisu z usług Lifecycle Services
description: W tym artykule opisano sposób skonfigurowania połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 05/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 5cccba580d23c3a0e9aed62f76a305926a58585f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879812"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Konfigurowanie podwójnego zapisu z usług Lifecycle Services

[!include [banner](../../includes/banner.md)]



W tym artykule opisano sposób włączenia połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Wymagania wstępne

Klienci muszą przeprowadzić integrację z Power Platform w sposób opisany w poniższych tematach:

- Jeśli nie używasz jeszcze Microsoft Power Platform, a chcesz rozszerzyć swoje środowiska rozwiązania Finance and Operations o możliwości platformy, zobacz [Integracja z Power Platform — włącz podczas wdrażania środowiska](../../power-platform/enable-power-platform-integration.md#enable-during-deploy).
- Jeśli masz już środowiska Dataverse i Power Platform i chcesz je połączyć ze środowiskami rozwiązania Finance and Operations, zobacz [Integracja z Power Platform — włącz po wdrożeniu środowiska](../../power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="set-up-dual-write-for-new-or-existing-dataverse-environments"></a>Skonfiguruj podwójny zapis dla nowych lub istniejących środowisk Dataverse

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

## <a name="linking-mismatch"></a>Niezgodność łączenia

Możliwe, że twoje środowisko podwójnego zapisu jest połączone z instancją Dataverse, a LCS nie jest ustawiony na integrację z Power Platform. Ten błąd w łączeniu może spowodować nieoczekiwane zachowanie. Zaleca się, aby szczegóły środowiska LCS odpowiadały temu, z którym jesteś połączony w systemie podwójnego zapisu, tak aby to samo połączenie mogło być używane przez zdarzenia biznesowe, tabele wirtualne i dodatki.

Jeśli Twoje środowisko ma niedopasowane łączenie, Na stronie szczegółów środowiska LCS pokazuje ostrzeżenie, które przypomina poniższy przykład „Microsoft wykrył, że Twoje środowisko jest połączone poprzez podwójny zapis do innego miejsca docelowego niż określone w integracji Power Platform, co nie jest zalecane”.

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="niedopasowane łącze integracyjne Power Platform.":::

Jeśli otrzymasz to ostrzeżenie, wypróbuj jedno z poniższych rozwiązań:

- Jeśli twoje środowisko LCS nigdy nie było skonfigurowane do integracji z Power Platform, możesz połączyć się z instancją Dataverse, która jest skonfigurowana w trybie podwójnego zapisu, postępując zgodnie z instrukcjami zawartymi w tym artykule.
- Jeśli Twoje środowisko LCS jest już skonfigurowane do integracji z Power Platform, powinieneś odłączyć dual-write i ponownie połączyć je z tym określonym przez LCS za pomocą [Scenariusza: Resetowanie lub zmiana linkowania](relink-environments.md#scenario-reset-or-change-linking).

W przeszłości dostępna była opcja ręcznego zgłoszenia do supportu, ale było to zanim pojawiła się opcja 1 powyżej.  Microsoft nie obsługuje już ręcznych próśb o relinkowanie za pośrednictwem biletów pomocy.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
