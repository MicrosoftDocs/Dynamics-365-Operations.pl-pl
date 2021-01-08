---
title: Instalowanie dodatku Analiza Internetu rzeczy (IoT) w usługach LCS
description: W tym temacie objaśniono, jak zainstalować dodatek analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad8b33633646f27bc368dc4bbedc1eb64c150a9f
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435535"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="fdec4-103">Instalowanie dodatku Analiza Internetu rzeczy (IoT) w usługach LCS</span><span class="sxs-lookup"><span data-stu-id="fdec4-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fdec4-104">W tym temacie objaśniono, jak zainstalować dodatek analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="fdec4-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="fdec4-105">Należy zauważyć, że dodatki nie mogą być instalowane w środowisku demonstracyjnym/próbnym.</span><span class="sxs-lookup"><span data-stu-id="fdec4-105">Note that add-ins cannot be installed on a demo/trial environment.</span></span> <span data-ttu-id="fdec4-106">Aby można było zainstalować dodatek, trzeba [utworzyć zasoby platformy Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="fdec4-106">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="fdec4-107">Konfigurowanie środowiska usług LSC</span><span class="sxs-lookup"><span data-stu-id="fdec4-107">Set up the LCS environment</span></span>

1. <span data-ttu-id="fdec4-108">Otwórz usługi LCS i przejdź do swojego środowiska Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fdec4-108">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="fdec4-109">Przewiń w dół do sekcji **Dodatki środowiska**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-109">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="fdec4-110">Wybierz pozycję **Zainstaluj nowy dodatek**, aby wyświetlić listę dodatków, które zostały włączone dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="fdec4-110">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="fdec4-111">W oknie dialogowym **Wybieranie dodatku do zainstalowania** wybierz pozycję **Analiza Internetu rzeczy (IoT)**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-111">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="fdec4-112">W oknie dialogowym **konfigurowania dodatku** podaj szczegóły dotyczące centrum IoT i pamięci podręcznej Redis.</span><span class="sxs-lookup"><span data-stu-id="fdec4-112">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="fdec4-113">Wymagane wartości można znaleźć w magazynie kluczy utworzonym podczas [tworzenia zasobów platformy Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="fdec4-113">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="fdec4-114">**Identyfikator dzierżawy** — w witrynie Azure Portal przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **identyfikatora katalogu**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-114">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="fdec4-115">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-115">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="fdec4-116">**Identyfikator URI magazynu kluczy punktów końcowych zgodnych z centrum zdarzeń IoT** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **nazwy DNS**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-116">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="fdec4-117">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-117">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="fdec4-118">**Nazwa klucza tajnego punktu końcowego zgodnego z centrum zdarzeń IoT** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Klucze tajne** i skopiuj nazwę klucza tajnego, w którym są przechowywane parametry połączenia centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="fdec4-118">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="fdec4-119">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-119">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="fdec4-120">**Identyfikator URI magazynu kluczy pamięci podręcznej Redis** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **nazwy DNS**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-120">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="fdec4-121">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-121">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="fdec4-122">**Nazwa klucza tajnego punktu końcowego pamięci podręcznej Redis** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Klucze tajne** i skopiuj nazwę klucza tajnego, w którym jest przechowywana pamięć podręczna Redis.</span><span class="sxs-lookup"><span data-stu-id="fdec4-122">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="fdec4-123">Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-123">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="fdec4-124">Zaznacz pole wyboru, aby zaakceptować warunki i postanowienia.</span><span class="sxs-lookup"><span data-stu-id="fdec4-124">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="fdec4-125">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-125">Select **Install**.</span></span>
8. <span data-ttu-id="fdec4-126">Zostanie wyświetlone okno komunikatu z informacją o tym, że „Dodatek został pomyślnie wyzwolony w celu instalacji”.</span><span class="sxs-lookup"><span data-stu-id="fdec4-126">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="fdec4-127">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-127">Select **OK**.</span></span>

<span data-ttu-id="fdec4-128">Konfiguracja usługi LCS jest teraz zakończona.</span><span class="sxs-lookup"><span data-stu-id="fdec4-128">LCS setup is now completed.</span></span> <span data-ttu-id="fdec4-129">Następnym krokiem jest [skonfigurowanie scenariuszy](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="fdec4-129">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="fdec4-130">Odinstalowywanie dodatku</span><span class="sxs-lookup"><span data-stu-id="fdec4-130">Uninstall the add-in</span></span>

1. <span data-ttu-id="fdec4-131">[Wyłącz scenariusze](iot-scenario-setup.md#disable-a-scenario) w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fdec4-131">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#disable-a-scenario).</span></span>
2. <span data-ttu-id="fdec4-132">W usługach LCS przejdź do szczegółów środowiska Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fdec4-132">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="fdec4-133">Przewiń w dół do sekcji **Dodatki środowiska**.</span><span class="sxs-lookup"><span data-stu-id="fdec4-133">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="fdec4-134">Wybierz pozycję **Odinstaluj** dla dodatku analizy Internetu rzeczy (IoT).</span><span class="sxs-lookup"><span data-stu-id="fdec4-134">Select **Uninstall** for the IoT Intelligence add-in.</span></span>
