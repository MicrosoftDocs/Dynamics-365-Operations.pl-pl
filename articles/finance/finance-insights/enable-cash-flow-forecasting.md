---
title: Włączanie prognozowania przepływów pieniężnych (wersja zapoznawcza)
description: W tym temacie wyjaśniono, jak włączyć funkcję prognozowania przepływów pieniężnych w Finance Insights.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.openlocfilehash: ba8acb2191291e2abed5cabf234c19fe09e6c8ff
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222565"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Włączanie prognozowania przepływów pieniężnych (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak włączyć funkcję prognozowania przepływów pieniężnych w Finance Insights.

> [!NOTE]
> Aby skorzystać z prognoz płatności w przepływie pieniężnym, należy skonfigurować funkcję przewidywania płatności odbiorcy w sposób opisany w temacie [Włączanie prognoz płatności odbiorcy](enable-cust-paymnt-prediction.md).

1. Użyj informacji ze strony środowiska w Microsoft Dynamics Lifecycle Services (LCS), aby połączyć się z podstawowym wystąpieniem usługi Azure SQL dla tego środowiska. Uruchom następujące polecenie Transact-SQL (T-SQL), aby włączyć loty dla środowiska piaskownicy. (Aby można było połączyć się zdalnie z serwerem obiektów aplikacji \[AOS\], może być konieczne włączenie dostępu do adresu IP w LCS.)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Pomiń ten krok, jeśli używasz wersji 10.0.20 lub nowszej albo jeśli używasz stanowiska Service Fabric. Zespół Finance Insights powinien już włączyć ten lot. Jeśli nie widzisz funkcji w obszarze roboczym **Zarządzanie funkcjami** lub wystąpią problemy podczas jej włączania, wyślij wiadomość e-mail na adres <fiap@microsoft.com>.
  
2. Otwórz obszar roboczy **Zarządzanie funkcjami** i wykonaj następujące kroki:

    1. Wybierz **Sprawdź, czy są aktualizacje**.
    2. Włącz następujące funkcje:

        - Nowa kontrolka siatki
        - Grupowanie w siatkach (wersja zapoznawcza) 
        - Prognozy płatności odbiorcy (wersja zapoznawcza)
        - Prognozy przepływów pieniężnych (wersja zapoznawcza)

3. Przejdź do **Zarządzanie gotówką i bankami \> Ustawienia prognozy przepływów pieniężnych**, a następnie dodaj konta płynności, które powinny zostać uwzględnione w prognozach.

    > [!NOTE]
    > Jeśli konta płynności nie są skonfigurowane, nie można wygenerować przepływu pieniężnego.

4. Przejdź do **Zarządzanie gotówką i bankami \> Ustawienia \> Finance Insights (wersja zapoznawcza) \> Prognozy przepływów pieniężnych (wersja zapoznawcza)**, a następnie wykonaj następujące kroki:

    1. Na karcie **Prognoza przepływów pieniężnych** wybierz opcję **Włącz funkcję**.
    2. Wybierz opcję **Utwórz model przewidywania**.

Więcej informacji na temat funkcji prognozowania przepływów pieniężnych znajdziesz: [Prognozy przepływów pieniężnych](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
