--- 
title: "Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych"
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 37957f224cb57fd9f6c5014740bcea124a99a03a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="5870e-103">Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych</span><span class="sxs-lookup"><span data-stu-id="5870e-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5870e-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="5870e-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="5870e-105">Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="5870e-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="5870e-106">W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="5870e-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="5870e-107">Tworzenie dostawcy</span><span class="sxs-lookup"><span data-stu-id="5870e-107">Create a provider</span></span>
1. <span data-ttu-id="5870e-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="5870e-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="5870e-109">Kliknij opcję Dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="5870e-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="5870e-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5870e-110">Click New.</span></span>
    * <span data-ttu-id="5870e-111">Rekord dostawcy ma unikatową nazwę i adres URL.</span><span class="sxs-lookup"><span data-stu-id="5870e-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="5870e-112">Przejrzyj zawartość tej strony i pomiń procedurę, jeśli rekord firmy Litware, Inc. (`http://www.litware.com`) już istnieje.</span><span class="sxs-lookup"><span data-stu-id="5870e-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (`http://www.litware.com`) already exists.</span></span>  
4. <span data-ttu-id="5870e-113">W polu Nazwa wpisz „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="5870e-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="5870e-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5870e-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="5870e-115">W polu Adres internetowy wpisz wartość `http://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="5870e-115">In the Internet address field, type `http://www.litware.com`.</span></span>
6. <span data-ttu-id="5870e-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5870e-116">Click Save.</span></span>
7. <span data-ttu-id="5870e-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5870e-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="5870e-118">Ustawianie jako aktywnego dostawcy</span><span class="sxs-lookup"><span data-stu-id="5870e-118">Select as an active provider</span></span>
1. <span data-ttu-id="5870e-119">Zaznacz dostawcę Litware, Inc.  </span><span class="sxs-lookup"><span data-stu-id="5870e-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="5870e-120">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="5870e-120">Click Set active.</span></span>


