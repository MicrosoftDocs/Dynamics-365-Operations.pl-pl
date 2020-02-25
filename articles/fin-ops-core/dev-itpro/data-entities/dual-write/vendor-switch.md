---
title: Przełączanie się między projektami dostawcy
description: W tym temacie opisano sposób przełączania integracji danych dostawcy między aplikacjami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
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
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 587a9b98f28b11e303aff4b59e9726f220d956eb
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019953"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="ab37c-103">Przełączanie się między projektami dostawcy</span><span class="sxs-lookup"><span data-stu-id="ab37c-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="ab37c-104">Przepływ danych dostawcy</span><span class="sxs-lookup"><span data-stu-id="ab37c-104">Vendor data flow</span></span> 

<span data-ttu-id="ab37c-105">Jeśli chcesz użyć innej aplikacji Dynamics 365 do tworzenia danych głównych dostawcy i chcesz wyodrębnić informacje o kliencie, możesz skorzystać z podstawowego schematu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ab37c-105">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Podstawowy przepływ dostawcy](media/dual-write-vendor-data-flow.png)
 
<span data-ttu-id="ab37c-107">Jeśli chcesz użyć innych aplikacji Dynamics 365 do tworzenia danych głównych dostawcy i chcesz dalej korzystać z encji **Konto** do przechowywania informacji o dostawcy, możesz skorzystać z nowego rozszerzonego schematu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ab37c-107">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="ab37c-108">W tym projekcie rozszerzone informacje o dostawcach, takie jak stan wstrzymania dostawcy i profil dostawcy, są przechowywane w jednostce **dostawcy** w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ab37c-108">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Rozszerzony przepływ dostawcy](media/dual-write-vendor-detail.jpg)
 
<span data-ttu-id="ab37c-110">Aby użyć rozszerzonego projektu dostawcy, należy wykonać poniższe kroki:</span><span class="sxs-lookup"><span data-stu-id="ab37c-110">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="ab37c-111">Pakiet rozwiązania **SupplyChainCommon** zawiera szablony procesów przepływu pracy przedstawione w poniższym obrazie.</span><span class="sxs-lookup"><span data-stu-id="ab37c-111">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ab37c-112">![Szablony procesu przepływu pracy](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="ab37c-112">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="ab37c-113">Tworzenie nowych procesów przepływu pracy przy użyciu szablonów procesu przepływu pracy:</span><span class="sxs-lookup"><span data-stu-id="ab37c-113">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="ab37c-114">Utwórz nowy proces przepływu pracy dla jednostki **dostawcy**, używając szablonu procesu przepływu pracy jednostki **Utwórz dostawców w jednostce kont** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab37c-114">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="ab37c-115">Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla jednostki **konta**.</span><span class="sxs-lookup"><span data-stu-id="ab37c-115">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="ab37c-116">![Utwórz dostawców w jednostce konta](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="ab37c-116">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="ab37c-117">Utwórz nowy proces przepływu pracy dla jednostki **dostawcy**, używając szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców w jednostce kont** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab37c-117">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="ab37c-118">Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla jednostki **konta**.</span><span class="sxs-lookup"><span data-stu-id="ab37c-118">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="ab37c-119">![Aktualizacja jednostki kont](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="ab37c-119">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="ab37c-120">Umożliwia tworzenie nowych procesów przepływu pracy na podstawie szablonów utworzonych w jednostce **konta**.</span><span class="sxs-lookup"><span data-stu-id="ab37c-120">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="ab37c-121">![Utwórz dostawców w jednostce dostawców](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="ab37c-121">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="ab37c-122">![Aktualizuj jednostkę dostawcy](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="ab37c-122">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="ab37c-123">Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ab37c-123">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="ab37c-124">![Konwertuj na przepływ pracy w tle](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="ab37c-124">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="ab37c-125">Aktywuj przepływy pracy utworzone w jednostkach **konta** i **dostawcy** w celu rozpoczęcia używania jednostki **Konto** do przechowywania informacji o dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ab37c-125">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the **Account** entity for storing vendor information.</span></span> 
 
