---
title: Konfigurowanie podwójnego zapisu z usług Lifecycle Services
description: W tym temacie wyjaśniono, jak skonfigurować połączenie podwójnego zapisywania między nowym środowiskiem Finance and Operations a nowym środowiskiem Common Data Service za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c78752aa1544b12f61071fa06617af4ac2809233
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172999"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="c72de-103">Konfigurowanie podwójnego zapisu z usług Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="c72de-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="c72de-104">W tym temacie wyjaśniono, jak skonfigurować połączenie podwójnego zapisywania między nowym środowiskiem Finance and Operations a nowym środowiskiem Common Data Service za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c72de-104">This topic explains how to set up a dual-write connection between a new Finance and Operations environment and a new Common Data Service environment from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c72de-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="c72de-105">Prerequisites</span></span>

<span data-ttu-id="c72de-106">Aby skonfigurować połączenie podwójnego zapisywania, należy mieć uprawnienia administratora.</span><span class="sxs-lookup"><span data-stu-id="c72de-106">You must be an admin to set up a dual-write connection.</span></span>

+ <span data-ttu-id="c72de-107">Trzeba mieć dostęp do dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="c72de-107">You must have access to the tenant.</span></span>
+ <span data-ttu-id="c72de-108">Użytkownik musi być administratorem w obu środowiskach Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c72de-108">You must be an admin in both Finance and Operations environments and Common Data Service environments.</span></span>

## <a name="set-up-a-dual-write-connection"></a><span data-ttu-id="c72de-109">Skonfiguruj połączenie podwójnego zapisywania</span><span class="sxs-lookup"><span data-stu-id="c72de-109">Set up a dual-write connection</span></span>

<span data-ttu-id="c72de-110">Aby skonfigurować połączenie podwójnego zapisu, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="c72de-110">Follow these steps to set up the dual-write connection.</span></span>

1. <span data-ttu-id="c72de-111">W LCS przejdź do projektu.</span><span class="sxs-lookup"><span data-stu-id="c72de-111">In LCS, go to your project.</span></span>
2. <span data-ttu-id="c72de-112">Wybierz przycisk **Konfiguruj**, aby wdrożyć nowe środowisko.</span><span class="sxs-lookup"><span data-stu-id="c72de-112">Select **Configure** to deploy a new environment.</span></span>
3. <span data-ttu-id="c72de-113">Wybierz wersję.</span><span class="sxs-lookup"><span data-stu-id="c72de-113">Select the version.</span></span> 
4. <span data-ttu-id="c72de-114">Wybierz topologię.</span><span class="sxs-lookup"><span data-stu-id="c72de-114">Select the topology.</span></span> <span data-ttu-id="c72de-115">Jeśli dostępna jest tylko jedna topologia, jest ona wybierana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="c72de-115">If only one topology is available, it's automatically selected.</span></span>
5. <span data-ttu-id="c72de-116">Wykonaj pierwsze kroki w Kreatorze **ustawień wdrażania**.</span><span class="sxs-lookup"><span data-stu-id="c72de-116">Complete the first steps in the **Deployment settings** wizard.</span></span>
6. <span data-ttu-id="c72de-117">Na karcie **Common Data Service** wykonaj jeden z tych kroków:</span><span class="sxs-lookup"><span data-stu-id="c72de-117">On the **Common Data Service** tab, follow one of these steps:</span></span>

    - <span data-ttu-id="c72de-118">Jeśli już zainicjowano obsługę administracyjną środowiska Common Data Service dla dzierżawy, można ją wybrać.</span><span class="sxs-lookup"><span data-stu-id="c72de-118">If a Common Data Service environment is already provisioned for your tenant, you can select it.</span></span>

        1. <span data-ttu-id="c72de-119">Ustaw opcję **Konfiguruj Common Data Service** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c72de-119">Set the **Configure Common Data Service** option to **Yes**.</span></span>
        2. <span data-ttu-id="c72de-120">W polu **dostępne środowiska** Wybierz środowisko, które ma zostać zintegrowane z danymi Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c72de-120">In the **Available environments** field, select the environment to integrate with your Finance and Operations data.</span></span> <span data-ttu-id="c72de-121">Lista zawiera wszystkie środowiska, do których użytkownik ma uprawnienia administratora.</span><span class="sxs-lookup"><span data-stu-id="c72de-121">The list includes all environments where you have admin privileges.</span></span>
        3. <span data-ttu-id="c72de-122">Zaznacz pole wyboru **Wyrażam zgodę**, aby wskazać, że zgadzasz się na warunki.</span><span class="sxs-lookup"><span data-stu-id="c72de-122">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Karta Common Data Service, jeśli zainicjowano już środowisko Common Data Service dla dzierżawy](../dual-write/media/lcs_setup_1.png)

    - <span data-ttu-id="c72de-124">Jeśli dzierżawa nie ma jeszcze środowiska Common Data Service, zostanie zainicjowana obsługa nowego środowiska.</span><span class="sxs-lookup"><span data-stu-id="c72de-124">If your tenant doesn't already have a Common Data Service environment, a new environment will be provisioned.</span></span>

        1. <span data-ttu-id="c72de-125">Ustaw opcję **Konfiguruj Common Data Service** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c72de-125">Set the **Configure Common Data Service** option to **Yes**.</span></span>
        2. <span data-ttu-id="c72de-126">Wprowadź nazwę środowiska Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c72de-126">Enter a name for the Common Data Service environment.</span></span>
        3. <span data-ttu-id="c72de-127">Wybierz region, w którym ma zostać wdrożone środowisko.</span><span class="sxs-lookup"><span data-stu-id="c72de-127">Select the region to deploy the environment in.</span></span>
        4. <span data-ttu-id="c72de-128">Wybierz domyślny język i walutę dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="c72de-128">Select the default language and currency for the environment.</span></span>

            > [!NOTE]
            > <span data-ttu-id="c72de-129">Nie można zmienić języka i waluty w późniejszym terminie.</span><span class="sxs-lookup"><span data-stu-id="c72de-129">You can't change the language and currency later.</span></span>

        5. <span data-ttu-id="c72de-130">Zaznacz pole wyboru **Wyrażam zgodę**, aby wskazać, że zgadzasz się na warunki.</span><span class="sxs-lookup"><span data-stu-id="c72de-130">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Karta Common Data Service, gdy dzierżawca nie posiada jeszcze środowiska Common Data Service](../dual-write/media/lcs_setup_2.png)

7. <span data-ttu-id="c72de-132">Wykonaj pozostałe kroki w Kreatorze **ustawień wdrażania**.</span><span class="sxs-lookup"><span data-stu-id="c72de-132">Complete the remaining steps in the **Deployment settings** wizard.</span></span>
8. <span data-ttu-id="c72de-133">Gdy środowisko ma stan **wdrożone**, Otwórz stronę szczegóły środowiska.</span><span class="sxs-lookup"><span data-stu-id="c72de-133">After the environment has a status of **Deployed**, open the environment details page.</span></span> <span data-ttu-id="c72de-134">W sekcji **informacje o środowisku Common Data Service** są wyświetlane nazwy połączonych środowisk Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c72de-134">The **Common Data Service environment information** section shows the names of the Finance and Operations environment and the Common Data Service environment that are linked.</span></span>

    ![Sekcja informacji o środowisku Common Data Service](../dual-write/media/lcs_setup_3.png)

9. <span data-ttu-id="c72de-136">Administrator środowiska Finance and Operations musi zalogować się do usługi LCS i wybrać opcję **Połącz z CDS dla aplikacji**, by zakończyć połączenie.</span><span class="sxs-lookup"><span data-stu-id="c72de-136">An admin of the Finance and Operations environment must sign in to LCS and select **Link to CDS for Apps** to complete the link.</span></span> <span data-ttu-id="c72de-137">Na stronie Szczegóły środowiska są wyświetlane informacje kontaktowe administratora.</span><span class="sxs-lookup"><span data-stu-id="c72de-137">The environment details page shows the admin's contact information.</span></span>

    <span data-ttu-id="c72de-138">Po zakończeniu połączenia stan jest aktualizowany do **Pomyślnie zakończone łączenie środowisk**.</span><span class="sxs-lookup"><span data-stu-id="c72de-138">After the link is completed, the status is updated to **Environment linking successfully completed**.</span></span>

10. <span data-ttu-id="c72de-139">Aby otworzyć obszar roboczy **integracji danych** w środowisku Finance and Operations i kontrolować dostępne szablony, wybierz **Połącz z CDS dla aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="c72de-139">To open the **Data integration** workspace in the Finance and Operations environment and control the templates that are available, select **Link to CDS for Apps**.</span></span>

    ![Przycisk Połącz z CDS dla aplikacji w sekcji informacji o środowisku Common Data Service](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> <span data-ttu-id="c72de-141">Nie można odłączyć środowisk za pomocą usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="c72de-141">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="c72de-142">Aby rozłączyć środowisko, Otwórz obszar roboczy **integracji danych** w środowisku Finance and Operations, a następnie wybierz opcję **Rozłącz**.</span><span class="sxs-lookup"><span data-stu-id="c72de-142">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>
