---
title: Włączanie propozycji budżetowych (wersja zapoznawcza)
description: W tym temacie wyjaśniono, jak włączyć funkcję propozycji budżetu w Finance Insights.
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
ms.openlocfilehash: d8443c4e3e6f3d3a90acedc7c05b2846d6b68369
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646212"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="37c2a-103">Włączanie propozycji budżetowych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="37c2a-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="37c2a-104">W tym temacie wyjaśniono, jak włączyć funkcję propozycji budżetu w Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="37c2a-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="37c2a-105">Użyj informacji ze strony środowiska w Microsoft Dynamics Lifecycle Services (LCS), aby połączyć się z podstawowym wystąpieniem usługi Azure SQL dla tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="37c2a-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="37c2a-106">Uruchom następujące polecenie Transact-SQL (T-SQL), aby włączyć loty dla środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="37c2a-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="37c2a-107">(Aby można było połączyć się zdalnie z serwerem obiektów aplikacji \[AOS\], może być konieczne włączenie dostępu do adresu IP w LCS.)</span><span class="sxs-lookup"><span data-stu-id="37c2a-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="37c2a-108">Jeśli wdrożenie systemu Microsoft Dynamics 365 Finance jest wdrożeniem Service Fabric, można pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="37c2a-108">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="37c2a-109">Zespół Finance Insights powinien już włączyć ten lot.</span><span class="sxs-lookup"><span data-stu-id="37c2a-109">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="37c2a-110">Jeśli nie widzisz funkcji w obszarze roboczym **Zarządzanie funkcjami** lub wystąpią problemy podczas jej włączania, wyślij wiadomość e-mail do [zespołu wersji zapoznawczej aplikacji Finance Insights](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="37c2a-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, send email to the [Finance Insights App Preview team](mailto:fiap@microsoft.com).</span></span>

2. <span data-ttu-id="37c2a-111">Otwórz obszar roboczy **Zarządzanie funkcjami** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="37c2a-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="37c2a-112">Wybierz **Sprawdź, czy są aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="37c2a-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="37c2a-113">Wyszukaj **Propozycja budżetu** i włącz tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="37c2a-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="37c2a-114">Przejdź do **Budżetowanie \> Ustawienia \> Budżetowanie podstawowe \> Propozycja budżetu (wersja zapoznawcza)** i wybierz **Włącz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="37c2a-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="37c2a-115">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="37c2a-115">Privacy notice</span></span>
<span data-ttu-id="37c2a-116">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="37c2a-116">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
