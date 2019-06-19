---
title: Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4b1cd7a02cdf4c650af50199f4425eb53cef0a8
ms.sourcegitcommit: 574d4dda83dcab94728a3d35fc53ee7e2b90feb0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/22/2019
ms.locfileid: "1595402"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="af8a0-103">Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych</span><span class="sxs-lookup"><span data-stu-id="af8a0-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="af8a0-104">W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="af8a0-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="af8a0-105">Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="af8a0-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="af8a0-106">W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="af8a0-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="af8a0-107">Tworzenie dostawcy</span><span class="sxs-lookup"><span data-stu-id="af8a0-107">Create a provider</span></span>
1. <span data-ttu-id="af8a0-108">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="af8a0-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="af8a0-109">Kliknij opcję Dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="af8a0-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="af8a0-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="af8a0-110">Click New.</span></span>
    * <span data-ttu-id="af8a0-111">Rekord dostawcy ma unikatową nazwę i adres URL.</span><span class="sxs-lookup"><span data-stu-id="af8a0-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="af8a0-112">Przejrzyj zawartość tej strony i pomiń procedurę, jeśli rekord firmy Litware, Inc. (https://www.litware.com) już istnieje.</span><span class="sxs-lookup"><span data-stu-id="af8a0-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="af8a0-113">W polu Nazwa wpisz „Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="af8a0-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="af8a0-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="af8a0-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="af8a0-115">W polu Adres internetowy wpisz wartość „https://www.litware.com”.</span><span class="sxs-lookup"><span data-stu-id="af8a0-115">In the Internet address field, type 'https://www.litware.com'.</span></span>
    * https://www.litware.com  
6. <span data-ttu-id="af8a0-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="af8a0-116">Click Save.</span></span>
7. <span data-ttu-id="af8a0-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="af8a0-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="af8a0-118">Ustawianie jako aktywnego dostawcy</span><span class="sxs-lookup"><span data-stu-id="af8a0-118">Select as an active provider</span></span>
1. <span data-ttu-id="af8a0-119">Zaznacz dostawcę Litware, Inc.  </span><span class="sxs-lookup"><span data-stu-id="af8a0-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="af8a0-120">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="af8a0-120">Click Set active.</span></span>

