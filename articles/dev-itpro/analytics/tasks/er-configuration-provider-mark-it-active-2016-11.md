--- 
title: Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego na potrzeby raportowania elektronicznego (ER)
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: 2dfa04f280249884af2a237807fb283059444a6c
ms.contentlocale: pl-pl
ms.lasthandoff: 11/02/2017

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="1cb0b-103">Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="1cb0b-103">Create a configuration provider and mark it as active for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1cb0b-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="1cb0b-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="1cb0b-105">Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="1cb0b-106">W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="1cb0b-107">Tworzenie dostawcy</span><span class="sxs-lookup"><span data-stu-id="1cb0b-107">Create a provider</span></span>
1. <span data-ttu-id="1cb0b-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="1cb0b-109">Kliknij opcję Dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="1cb0b-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-110">Click New.</span></span>
    * <span data-ttu-id="1cb0b-111">Rekord dostawcy ma unikatową nazwę i adres URL.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="1cb0b-112">Przejrzyj zawartość tej strony i pomiń procedurę, jeśli rekord firmy Litware, Inc. (http://www.litware.com) już istnieje.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="1cb0b-113">W polu Nazwa wpisz „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="1cb0b-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="1cb0b-115">W polu Adres internetowy wpisz „http://www.litware.com”.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * <span data-ttu-id="1cb0b-116">http://www.litware.com</span><span class="sxs-lookup"><span data-stu-id="1cb0b-116">http://www.litware.com</span></span>  
6. <span data-ttu-id="1cb0b-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-117">Click Save.</span></span>
7. <span data-ttu-id="1cb0b-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-118">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="1cb0b-119">Ustawianie jako aktywnego dostawcy</span><span class="sxs-lookup"><span data-stu-id="1cb0b-119">Select as an active provider</span></span>
1. <span data-ttu-id="1cb0b-120">Zaznacz dostawcę Litware, Inc.  </span><span class="sxs-lookup"><span data-stu-id="1cb0b-120">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="1cb0b-121">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="1cb0b-121">Click Set active.</span></span>


