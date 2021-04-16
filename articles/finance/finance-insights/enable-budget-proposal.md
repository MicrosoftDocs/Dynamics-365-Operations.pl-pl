---
title: Włączanie propozycji budżetowych (wersja zapoznawcza)
description: W tym temacie wyjaśniono, jak włączyć funkcję propozycji budżetu w Finance Insights.
author: ShivamPandey-msft
ms.date: 07/24/2020
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
ms.openlocfilehash: 7e90a1a2f2a8e7808f03ce9a6ee58c027bd48d8d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818711"
---
# <a name="enable-budget-proposals-preview"></a>Włączanie propozycji budżetowych (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak włączyć funkcję propozycji budżetu w Finance Insights.

1. Użyj informacji ze strony środowiska w Microsoft Dynamics Lifecycle Services (LCS), aby połączyć się z podstawowym wystąpieniem usługi Azure SQL dla tego środowiska. Uruchom następujące polecenie Transact-SQL (T-SQL), aby włączyć loty dla środowiska piaskownicy. (Aby można było połączyć się zdalnie z serwerem obiektów aplikacji \[AOS\], może być konieczne włączenie dostępu do adresu IP w LCS.)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Jeśli wdrożenie systemu Microsoft Dynamics 365 Finance jest wdrożeniem Service Fabric, można pominąć ten krok. Zespół Finance Insights powinien już włączyć ten lot. Jeśli nie widzisz funkcji w obszarze roboczym **Zarządzanie funkcjami** lub wystąpią problemy podczas jej włączania, wyślij wiadomość e-mail do [zespołu wersji zapoznawczej aplikacji Finance Insights](mailto:fiap@microsoft.com).

2. Otwórz obszar roboczy **Zarządzanie funkcjami** i wykonaj następujące kroki:

    1. Wybierz **Sprawdź, czy są aktualizacje**.
    2. Wyszukaj **Propozycja budżetu** i włącz tę funkcję.

3. Przejdź do **Budżetowanie \> Ustawienia \> Budżetowanie podstawowe \> Propozycja budżetu (wersja zapoznawcza)** i wybierz **Włącz funkcję**.

#### <a name="privacy-notice"></a>Klauzula prywatności
Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]