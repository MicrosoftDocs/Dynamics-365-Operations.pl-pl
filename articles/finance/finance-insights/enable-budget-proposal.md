---
title: Włączanie propozycji budżetowych (wersja zapoznawcza)
description: W tym temacie wyjaśniono, jak włączyć funkcję propozycji budżetu w Finance Insights.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: cc7b06ee40553a254a939babc30e6f5c99f85507c1a3db4e916f480560cf8835
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768946"
---
# <a name="enable-budget-proposals-preview"></a>Włączanie propozycji budżetowych (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak włączyć funkcję propozycji budżetu w Finance Insights.

1. Użyj informacji ze strony środowiska w Microsoft Dynamics Lifecycle Services (LCS), aby połączyć się z podstawowym wystąpieniem usługi Azure SQL dla tego środowiska. Uruchom następujące polecenie Transact-SQL (T-SQL), aby włączyć loty dla środowiska piaskownicy. (Aby można było połączyć się zdalnie z serwerem obiektów aplikacji \[AOS\], może być konieczne włączenie dostępu do adresu IP w LCS.)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Pomiń ten krok, jeśli używasz wersji 10.0.20 lub nowszej albo jeśli używasz stanowiska Service Fabric. Zespół Finance Insights powinien już włączyć ten lot. Jeśli nie widzisz funkcji w obszarze roboczym **Zarządzanie funkcjami** lub wystąpią problemy podczas jej włączania, wyślij wiadomość e-mail na adres <fiap@microsoft.com>.

2. Otwórz obszar roboczy **Zarządzanie funkcjami** i wykonaj następujące kroki:

    1. Wybierz **Sprawdź, czy są aktualizacje**.
    2. Wyszukaj **Propozycja budżetu** i włącz tę funkcję.

3. Przejdź do **Budżetowanie \> Ustawienia \> Budżetowanie podstawowe \> Propozycja budżetu (wersja zapoznawcza)** i wybierz **Włącz funkcję**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
