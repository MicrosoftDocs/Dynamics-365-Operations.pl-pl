---
title: Instalowanie dodatku Analiza Internetu rzeczy (IoT) w usługach LCS
description: W tym temacie objaśniono, jak zainstalować dodatek analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 04333b3659f090b15cc0d0ee216f14dabc588883
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386549"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="b11ab-103">Instalowanie dodatku Analiza Internetu rzeczy (IoT) w usługach LCS</span><span class="sxs-lookup"><span data-stu-id="b11ab-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b11ab-104">W tym temacie objaśniono, jak zainstalować dodatek analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b11ab-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="b11ab-105">Aby można było zainstalować dodatek, trzeba [utworzyć zasoby platformy Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="b11ab-105">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="b11ab-106">Konfigurowanie środowiska usług LSC</span><span class="sxs-lookup"><span data-stu-id="b11ab-106">Set up the LCS environment</span></span>

1. <span data-ttu-id="b11ab-107">Otwórz usługi LCS i przejdź do swojego środowiska Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b11ab-107">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="b11ab-108">Przewiń w dół do sekcji **Dodatki środowiska**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-108">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="b11ab-109">Wybierz pozycję **Zainstaluj nowy dodatek**, aby wyświetlić listę dodatków, które zostały włączone dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="b11ab-109">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="b11ab-110">W oknie dialogowym **Wybieranie dodatku do zainstalowania** wybierz pozycję **Analiza Internetu rzeczy (IoT)**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-110">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="b11ab-111">W oknie dialogowym **konfigurowania dodatku** podaj szczegóły dotyczące centrum IoT i pamięci podręcznej Redis.</span><span class="sxs-lookup"><span data-stu-id="b11ab-111">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="b11ab-112">Wymagane wartości można znaleźć w magazynie kluczy utworzonym podczas [tworzenia zasobów platformy Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="b11ab-112">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="b11ab-113">**Identyfikator dzierżawy** — w witrynie Azure Portal przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **identyfikatora katalogu**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-113">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="b11ab-114">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-114">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="b11ab-115">**Identyfikator URI magazynu kluczy punktów końcowych zgodnych z centrum zdarzeń IoT** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **nazwy DNS**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-115">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="b11ab-116">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-116">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="b11ab-117">**Nazwa klucza tajnego punktu końcowego zgodnego z centrum zdarzeń IoT** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Klucze tajne** i skopiuj nazwę klucza tajnego, w którym są przechowywane parametry połączenia centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="b11ab-117">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="b11ab-118">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-118">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="b11ab-119">**Identyfikator URI magazynu kluczy pamięci podręcznej Redis** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **nazwy DNS**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-119">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="b11ab-120">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-120">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="b11ab-121">**Nazwa klucza tajnego punktu końcowego pamięci podręcznej Redis** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Klucze tajne** i skopiuj nazwę klucza tajnego, w którym jest przechowywana pamięć podręczna Redis.</span><span class="sxs-lookup"><span data-stu-id="b11ab-121">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="b11ab-122">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-122">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="b11ab-123">Zaznacz pole wyboru, aby zaakceptować warunki i postanowienia.</span><span class="sxs-lookup"><span data-stu-id="b11ab-123">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="b11ab-124">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-124">Select **Install**.</span></span>
8. <span data-ttu-id="b11ab-125">Zostanie wyświetlone okno komunikatu z informacją o tym, że „Dodatek został pomyślnie wyzwolony w celu instalacji”.</span><span class="sxs-lookup"><span data-stu-id="b11ab-125">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="b11ab-126">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-126">Select **OK**.</span></span>

<span data-ttu-id="b11ab-127">Konfiguracja usługi LCS jest teraz zakończona.</span><span class="sxs-lookup"><span data-stu-id="b11ab-127">LCS setup is now completed.</span></span> <span data-ttu-id="b11ab-128">Następnym krokiem jest [skonfigurowanie scenariuszy](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="b11ab-128">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="b11ab-129">Odinstalowywanie dodatku</span><span class="sxs-lookup"><span data-stu-id="b11ab-129">Uninstall the add-in</span></span>

1. <span data-ttu-id="b11ab-130">[Wyłącz scenariusze](iot-scenario-setup.md#how-to-disable-a-scenario) w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b11ab-130">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#how-to-disable-a-scenario).</span></span>
2. <span data-ttu-id="b11ab-131">W usługach LCS przejdź do szczegółów środowiska Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b11ab-131">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="b11ab-132">Przewiń w dół do sekcji **Dodatki środowiska**.</span><span class="sxs-lookup"><span data-stu-id="b11ab-132">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="b11ab-133">Wybierz pozycję **Odinstaluj**dla dodatku analizy Internetu rzeczy (IoT).</span><span class="sxs-lookup"><span data-stu-id="b11ab-133">Select **Uninstall** for the IoT Intelligence add-in.</span></span>
