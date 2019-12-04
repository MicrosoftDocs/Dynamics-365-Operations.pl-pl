---
title: Przełączanie się między projektami dostawców
description: ''
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
ms.openlocfilehash: 4e97ff0b0e6195b5e3703e15a0bb0de7644ef8d1
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772371"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="e7c41-102">Przełączanie się między projektami dostawców</span><span class="sxs-lookup"><span data-stu-id="e7c41-102">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="e7c41-103">Przepływ danych dostawcy</span><span class="sxs-lookup"><span data-stu-id="e7c41-103">Vendor data flow</span></span> 

<span data-ttu-id="e7c41-104">Jeśli chcesz użyć innej aplikacji Dynamics 365 do tworzenia danych głównych dostawcy i chcesz wyodrębnić informacje o kliencie, możesz skorzystać z podstawowego schematu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="e7c41-104">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Podstawowy przepływ dostawcy](media/dual-write-switch-1.png)
 
<span data-ttu-id="e7c41-106">Jeśli chcesz użyć innych aplikacji Dynamics 365 do tworzenia danych głównych dostawcy i chcesz dalej korzystać z encji **Konto** do przechowywania informacji o dostawcy, możesz skorzystać z nowego rozszerzonego schematu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="e7c41-106">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="e7c41-107">W tym projekcie rozszerzone informacje o dostawcach, takie jak stan wstrzymania dostawcy i profil dostawcy, są przechowywane w jednostce **dostawcy** w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e7c41-107">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Rozszerzony przepływ dostawcy](media/dual-write-switch-2.png)
 
<span data-ttu-id="e7c41-109">Aby użyć rozszerzonego projektu dostawcy, należy wykonać poniższe kroki:</span><span class="sxs-lookup"><span data-stu-id="e7c41-109">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="e7c41-110">Pakiet rozwiązania **SupplyChainCommon** zawiera szablony procesów przepływu pracy przedstawione w poniższym obrazie.</span><span class="sxs-lookup"><span data-stu-id="e7c41-110">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e7c41-111">![Szablony procesu przepływu pracy](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="e7c41-111">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="e7c41-112">Tworzenie nowych procesów przepływu pracy przy użyciu szablonów procesu przepływu pracy:</span><span class="sxs-lookup"><span data-stu-id="e7c41-112">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="e7c41-113">Utwórz nowy proces przepływu pracy dla jednostki **dostawcy**, używając szablonu procesu przepływu pracy jednostki **Utwórz dostawców w jednostce kont** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7c41-113">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="e7c41-114">Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla jednostki **konta**.</span><span class="sxs-lookup"><span data-stu-id="e7c41-114">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e7c41-115">![Utwórz dostawców w jednostce konta](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="e7c41-115">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="e7c41-116">Utwórz nowy proces przepływu pracy dla jednostki **dostawcy**, używając szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców w jednostce kont** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7c41-116">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="e7c41-117">Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla jednostki **konta**.</span><span class="sxs-lookup"><span data-stu-id="e7c41-117">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e7c41-118">![Aktualizacja jednostki kont](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="e7c41-118">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="e7c41-119">Umożliwia tworzenie nowych procesów przepływu pracy na podstawie szablonów utworzonych w jednostce **konta**.</span><span class="sxs-lookup"><span data-stu-id="e7c41-119">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e7c41-120">![Utwórz dostawców w jednostce dostawców](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="e7c41-120">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="e7c41-121">![Aktualizuj jednostkę dostawcy](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="e7c41-121">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="e7c41-122">Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e7c41-122">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e7c41-123">![Konwertuj na przepływ pracy w tle](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="e7c41-123">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="e7c41-124">Umożliwia aktywowanie przepływów pracy utworzonych w jednostkach **konta** i **dostawcy** w celu rozpoczęcia używania Customer Engagement jednostki **konta** zakontraktowania z odbiorcą do przechowywania informacji o dostawcy.</span><span class="sxs-lookup"><span data-stu-id="e7c41-124">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the Customer Engagement **Account** entity for storing vendor information.</span></span> 
 
