---
title: Tworzenie projektu integratora danych (wersja zapoznawcza)
description: W tym temacie opisano sposób tworzenia projektu integratora danych.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: fb17d5e82709a34ff088774d9e9034adb714b58c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646260"
---
# <a name="create-a-data-integrator-project-preview"></a>Tworzenie projektu integratora danych (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano sposób tworzenia projektu integratora danych.

1. Zaloguj się do programu Microsoft Dynamics 365 Finance.
2. Przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz **Jednostki danych**. Poczekaj, aż wszystkie jednostki danych zostaną odświeżone przed przejściem do następnego kroku.
3. Otwórz [portal Power Apps ](https://make.powerapps.com/)i wykonaj następujące kroki:

    1. Wybierz odpowiednie środowisko.
    2. W okienku nawigacji po lewej stronie wybierz **Dane \> Połączenia**.
    3. Połącz z odpowiednimi wystąpieniami następujących elementów:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Otwórz [środowiska Power Apps ](https://admin.powerapps.com/environments)i wykonaj następujące kroki:

    1. Wybierz **Integrator danych**.
    2. Wybierz **Zestaw połączeń**.
    3. Wybierz **Nowy zestaw połączeń**.
    4. Wprowadź nazwę połączenia.
    5. Wybierz odpowiednie połączenia dla następujących elementów:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. Wybierz odpowiednie mapowanie organizacji.
    7. Wybierz opcję **Utwórz**.

5. Otwórz [środowiska Power Apps ](https://admin.powerapps.com/environments)i wykonaj następujące kroki:  

    1. Utwórz projekty integracji danych dla następujących szablonów przy użyciu utworzonego właśnie zestawu połączeń:

        - Wyniki wglądu w płatności od odbiorców (CDS do Fin and Ops)
        - Wyniki szeregów czasowych przepływów pieniężnych (CDS do Fin and Ops)
        - Wyniki szeregów czasowych budżetu (CDS do Fin and Ops)

    2. Ustaw odpowiednie planowanie dla każdego projektu.

> [!NOTE]
> Jeśli w CDS nie są wyświetlane wymagane jednostki, przejdź do **Kredyt i windykacje > ustawienia > Finance Insights > Parametry Finance Insights**, włącz funkcję przewidywania płatności od odbiorców i kliknij przycisk **Utwórz model przewidywania**. Po ukończeniu wdrażania modelu AI (powodzenie lub niepowodzenie) jednostki CDS potrzebne do utworzenia integracji zostaną wdrożone w CDS.

## <a name="privacy-notice"></a>Klauzula prywatności

Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]