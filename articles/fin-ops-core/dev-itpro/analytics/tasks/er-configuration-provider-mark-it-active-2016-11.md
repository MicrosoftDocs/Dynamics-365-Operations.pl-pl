---
title: Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych
description: W tym temacie wyjaśniono, w jaki sposób użytkownik przypisany do roli Administratora Systemu lub Programisty Elektronicznego Raportowania może utworzyć dostawcę konfiguracji dla Elektronicznego Raportowania (ER).
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2c092414f058a27cde963b1e8befd41ab3d1e3c
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249211"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="41e54-103">Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych</span><span class="sxs-lookup"><span data-stu-id="41e54-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="41e54-104">W tym temacie wyjaśniono, w jaki sposób użytkownik przypisany do roli Administratora Systemu lub Programisty Elektronicznego Raportowania może utworzyć dostawcę konfiguracji dla Elektronicznego Raportowania (ER).</span><span class="sxs-lookup"><span data-stu-id="41e54-104">This topic explains how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="41e54-105">Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="41e54-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="41e54-106">W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.</span><span class="sxs-lookup"><span data-stu-id="41e54-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>

## <a name="create-a-provider"></a><span data-ttu-id="41e54-107">Tworzenie dostawcy</span><span class="sxs-lookup"><span data-stu-id="41e54-107">Create a provider</span></span>
1. <span data-ttu-id="41e54-108">Otwórz **okienko nawigacji** w górnym lewym rogu i wybierz **Administracja organizacji**.</span><span class="sxs-lookup"><span data-stu-id="41e54-108">Go to the **navigation pane** in the upper left corner and select **Organization administration**.</span></span>
2. <span data-ttu-id="41e54-109">Otwórz **Miejsca pracy > Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="41e54-109">Go to **Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="41e54-110">Otwórz **Powiązane linki > Dostawcy konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="41e54-110">Go to **Related links > Configuration providers**.</span></span>
4. <span data-ttu-id="41e54-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="41e54-111">Select **New**.</span></span>
    - <span data-ttu-id="41e54-112">Rekord dostawcy ma unikatową nazwę i adres URL.</span><span class="sxs-lookup"><span data-stu-id="41e54-112">A provider record has a unique name and URL.</span></span> <span data-ttu-id="41e54-113">Przejrzyj zawartość tej strony i pomiń procedurę, jeśli rekord firmy Litware, Inc. (https://www.litware.com) już istnieje.</span><span class="sxs-lookup"><span data-stu-id="41e54-113">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
5. <span data-ttu-id="41e54-114">W polu Nazwa wpisz `Litware, Inc.`.</span><span class="sxs-lookup"><span data-stu-id="41e54-114">In the Name field, type `Litware, Inc.`.</span></span>
6. <span data-ttu-id="41e54-115">W polu adres internetowy wpisz `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="41e54-115">In the Internet address field, type `https://www.litware.com`.</span></span>
7. <span data-ttu-id="41e54-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="41e54-116">Select **Save**.</span></span>
8. <span data-ttu-id="41e54-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="41e54-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="41e54-118">Ustawianie jako aktywnego dostawcy</span><span class="sxs-lookup"><span data-stu-id="41e54-118">Select as an active provider</span></span>
1. <span data-ttu-id="41e54-119">Zaznacz dostawcę Litware, Inc.  </span><span class="sxs-lookup"><span data-stu-id="41e54-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="41e54-120">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="41e54-120">Select **Set active**.</span></span>

![Strona obszaru roboczego raportowania elektronicznego](../media/GER-Task-ActiveProvider-1.png)
