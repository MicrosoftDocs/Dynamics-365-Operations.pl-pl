---
title: Włączanie prognozowania przepływów pieniężnych (wersja zapoznawcza)
description: W tym temacie wyjaśniono, jak włączyć funkcję prognozowania przepływów pieniężnych w Finance Insights.
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
ms.openlocfilehash: 321c716c10b136769ea3a48a3b60a8a717798338
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646236"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="f08b7-103">Włączanie prognozowania przepływów pieniężnych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f08b7-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="f08b7-104">W tym temacie wyjaśniono, jak włączyć funkcję prognozowania przepływów pieniężnych w Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="f08b7-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="f08b7-105">Aby skorzystać z prognoz płatności w przepływie pieniężnym, należy skonfigurować funkcję przewidywania płatności odbiorcy w sposób opisany w temacie [Włączanie prognoz płatności odbiorcy](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="f08b7-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="f08b7-106">Użyj informacji ze strony środowiska w Microsoft Dynamics Lifecycle Services (LCS), aby połączyć się z podstawowym wystąpieniem usługi Azure SQL dla tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="f08b7-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="f08b7-107">Uruchom następujące polecenie Transact-SQL (T-SQL), aby włączyć loty dla środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="f08b7-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="f08b7-108">(Aby można było połączyć się zdalnie z serwerem obiektów aplikacji \[AOS\], może być konieczne włączenie dostępu do adresu IP w LCS.)</span><span class="sxs-lookup"><span data-stu-id="f08b7-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="f08b7-109">Jeśli wdrożenie systemu Microsoft Dynamics 365 Finance jest wdrożeniem Service Fabric, można pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="f08b7-109">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="f08b7-110">Zespół Finance Insights powinien już włączyć ten lot.</span><span class="sxs-lookup"><span data-stu-id="f08b7-110">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="f08b7-111">Jeśli nie widzisz funkcji w obszarze roboczym **Zarządzanie funkcjami** lub wystąpią problemy podczas jej włączania, wyślij wiadomość e-mail na adres <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="f08b7-111">If you don't see the features in the **Feature management** workspace, or if experience issues when you try to turn them on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="f08b7-112">Otwórz obszar roboczy **Zarządzanie funkcjami** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="f08b7-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="f08b7-113">Wybierz **Sprawdź, czy są aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="f08b7-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="f08b7-114">Włącz następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="f08b7-114">Turn on the following features:</span></span>

        - <span data-ttu-id="f08b7-115">Nowa kontrolka siatki</span><span class="sxs-lookup"><span data-stu-id="f08b7-115">New grid control</span></span>
        - <span data-ttu-id="f08b7-116">Grupowanie w siatkach (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f08b7-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="f08b7-117">Prognozy płatności odbiorcy (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f08b7-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="f08b7-118">Prognozy przepływów pieniężnych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f08b7-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="f08b7-119">Przejdź do **Zarządzanie gotówką i bankami \> Ustawienia prognozy przepływów pieniężnych**, a następnie dodaj konta płynności, które powinny zostać uwzględnione w prognozach.</span><span class="sxs-lookup"><span data-stu-id="f08b7-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f08b7-120">Jeśli konta płynności nie są skonfigurowane, nie można wygenerować przepływu pieniężnego.</span><span class="sxs-lookup"><span data-stu-id="f08b7-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="f08b7-121">Przejdź do **Zarządzanie gotówką i bankami \> Ustawienia \> Finance Insights (wersja zapoznawcza) \> Prognozy przepływów pieniężnych (wersja zapoznawcza)**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="f08b7-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="f08b7-122">Na karcie **Prognoza przepływów pieniężnych** wybierz opcję **Włącz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="f08b7-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="f08b7-123">Wybierz opcję **Utwórz model przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="f08b7-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="f08b7-124">Więcej informacji na temat funkcji prognozowania przepływów pieniężnych znajdziesz: [Prognozy przepływów pieniężnych](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="f08b7-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="f08b7-125">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="f08b7-125">Privacy notice</span></span>

<span data-ttu-id="f08b7-126">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="f08b7-126">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
