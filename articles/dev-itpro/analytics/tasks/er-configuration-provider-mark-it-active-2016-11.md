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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9ed6f62318cd6806de1b4c9d6aa314c5f0a25500
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="402f0-103">Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego na potrzeby raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="402f0-103">Create a configuration provider and mark it as active for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="402f0-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="402f0-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="402f0-105">Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="402f0-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="402f0-106">W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="402f0-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="402f0-107">Tworzenie dostawcy</span><span class="sxs-lookup"><span data-stu-id="402f0-107">Create a provider</span></span>
1. <span data-ttu-id="402f0-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="402f0-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="402f0-109">Kliknij opcję Dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="402f0-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="402f0-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="402f0-110">Click New.</span></span>
    * <span data-ttu-id="402f0-111">Rekord dostawcy ma unikatową nazwę i adres URL.</span><span class="sxs-lookup"><span data-stu-id="402f0-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="402f0-112">Przejrzyj zawartość tej strony i pomiń procedurę, jeśli rekord firmy Litware, Inc. (`http://www.litware.com`) już istnieje.</span><span class="sxs-lookup"><span data-stu-id="402f0-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (`http://www.litware.com`) already exists.</span></span>  
4. <span data-ttu-id="402f0-113">W polu Nazwa wpisz „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="402f0-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="402f0-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="402f0-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="402f0-115">W polu Adres internetowy wpisz wartość `http://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="402f0-115">In the Internet address field, type `http://www.litware.com`.</span></span>
6. <span data-ttu-id="402f0-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="402f0-116">Click Save.</span></span>
7. <span data-ttu-id="402f0-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="402f0-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="402f0-118">Ustawianie jako aktywnego dostawcy</span><span class="sxs-lookup"><span data-stu-id="402f0-118">Select as an active provider</span></span>
1. <span data-ttu-id="402f0-119">Zaznacz dostawcę Litware, Inc.  </span><span class="sxs-lookup"><span data-stu-id="402f0-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="402f0-120">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="402f0-120">Click Set active.</span></span>


