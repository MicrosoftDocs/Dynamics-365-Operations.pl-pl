---
title: Utwórz projekt integracji danych
description: W tym temacie wyjaśniono, jak utworzyć projekt integracji danych.
author: ShivamPandey-msft
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 50f435f9d461667a1908baa529d73766085c183a
ms.sourcegitcommit: 6526acd0300d9c5800d3d7675d54e23090d031df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/10/2022
ms.locfileid: "8107294"
---
# <a name="create-a-data-integration-project"></a>Utwórz projekt integracji danych

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak utworzyć projekt integracji danych.

1. Zaloguj się do programu Microsoft Dynamics 365 Finance.
2. Przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz **Jednostki danych**. Poczekaj, aż wszystkie jednostki danych zostaną odświeżone przed przejściem do następnego kroku.
3. Otwórz [portal Power Apps ](https://make.powerapps.com/)i wykonaj następujące kroki:

    1. Wybierz odpowiednie środowisko.
    2. W okienku nawigacji po lewej stronie wybierz **Dataverse \> Połączenia**.
    3. Połącz z odpowiednimi wystąpieniami następujących elementów:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Otwórz [środowiska Power Apps ](https://admin.powerapps.com/environments)i wykonaj następujące kroki:

    1. Wybierz **Integracja danych**.
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

        - Wyniki analizy płatności klientów (CDS do Fin and Ops 10.0.17+)
        - Wyniki szeregów czasowych przepływów pieniężnych (CDS do Fin and Ops)
        - Wyniki szeregów czasowych budżetu (CDS do Fin and Ops)

    2. Ustaw odpowiednie planowanie dla każdego projektu.

> [!NOTE]
> Jeśli w Dataverse nie są wyświetlane wymagane jednostki, przejdź do **Kredyt i windykacje** > **ustawienia** > **Finance Insights** > **Parametry Finance Insights**, włącz funkcję **przewidywania płatności od odbiorców** i kliknij przycisk **Utwórz model przewidywania**. Po zakończeniu wdrażania modelu AI zostaną wdrożone encje Dataverse potrzebne do utworzenia integracji.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
