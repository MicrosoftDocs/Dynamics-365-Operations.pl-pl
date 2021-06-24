---
title: Włączanie propozycji budżetowych (wersja zapoznawcza)
description: W tym temacie wyjaśniono, jak włączyć funkcję propozycji budżetu w Finance Insights.
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
ms.openlocfilehash: 948a3e051e5964c5c773cefd90c8587cf833a450
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222541"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="51101-103">Włączanie propozycji budżetowych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="51101-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="51101-104">W tym temacie wyjaśniono, jak włączyć funkcję propozycji budżetu w Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="51101-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="51101-105">Użyj informacji ze strony środowiska w Microsoft Dynamics Lifecycle Services (LCS), aby połączyć się z podstawowym wystąpieniem usługi Azure SQL dla tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="51101-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="51101-106">Uruchom następujące polecenie Transact-SQL (T-SQL), aby włączyć loty dla środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="51101-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="51101-107">(Aby można było połączyć się zdalnie z serwerem obiektów aplikacji \[AOS\], może być konieczne włączenie dostępu do adresu IP w LCS.)</span><span class="sxs-lookup"><span data-stu-id="51101-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="51101-108">Pomiń ten krok, jeśli używasz wersji 10.0.20 lub nowszej albo jeśli używasz stanowiska Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="51101-108">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="51101-109">Zespół Finance Insights powinien już włączyć ten lot.</span><span class="sxs-lookup"><span data-stu-id="51101-109">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="51101-110">Jeśli nie widzisz funkcji w obszarze roboczym **Zarządzanie funkcjami** lub wystąpią problemy podczas jej włączania, wyślij wiadomość e-mail na adres <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="51101-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="51101-111">Otwórz obszar roboczy **Zarządzanie funkcjami** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="51101-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="51101-112">Wybierz **Sprawdź, czy są aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="51101-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="51101-113">Wyszukaj **Propozycja budżetu** i włącz tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="51101-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="51101-114">Przejdź do **Budżetowanie \> Ustawienia \> Budżetowanie podstawowe \> Propozycja budżetu (wersja zapoznawcza)** i wybierz **Włącz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="51101-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
