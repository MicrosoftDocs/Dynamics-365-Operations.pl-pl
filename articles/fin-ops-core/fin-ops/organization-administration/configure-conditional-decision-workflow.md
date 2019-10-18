---
title: Konfigurowanie decyzji warunkowych w przepływie pracy
description: Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 278773a5ad8be35f9b6dcd1ec0d0a35e32222bb1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179499"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a><span data-ttu-id="b793a-103">Konfigurowanie decyzji warunkowych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="b793a-103">Configure conditional decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b793a-104">Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="b793a-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="b793a-105">Decyzja warunkowa to punkt, w którym przepływ pracy rozdziela się na dwie gałęzie.</span><span class="sxs-lookup"><span data-stu-id="b793a-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="b793a-106">Aby skonfigurować decyzję warunkową, w edytorze przepływu pracy kliknij decyzję warunkową prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta formularz **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="b793a-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="b793a-107">Nazywanie decyzji</span><span class="sxs-lookup"><span data-stu-id="b793a-107">Name a decision</span></span>

<span data-ttu-id="b793a-108">Wykonaj następujące kroki, aby nazwać decyzję warunkową.</span><span class="sxs-lookup"><span data-stu-id="b793a-108">Follow these steps to enter a name for a conditional decision.</span></span>

1. <span data-ttu-id="b793a-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="b793a-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b793a-110">W polu **Nazwa** wprowadź unikatową nazwę decyzji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="b793a-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="b793a-111"> Konfigurowanie warunków</span><span class="sxs-lookup"><span data-stu-id="b793a-111">Set conditions</span></span>

<span data-ttu-id="b793a-112">System decyduje, której gałęzi użyć, oceniając przesłany dokument, aby ustalić, czy spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="b793a-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>

1. <span data-ttu-id="b793a-113">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="b793a-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b793a-114">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="b793a-114">Click **Add condition**.</span></span>
3. <span data-ttu-id="b793a-115">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="b793a-115">Enter a condition.</span></span>
4. <span data-ttu-id="b793a-116">Wprowadź dodatkowe warunki, jeśli są wymagane.</span><span class="sxs-lookup"><span data-stu-id="b793a-116">Enter additional conditions, if they are required.</span></span>
5. <span data-ttu-id="b793a-117">Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="b793a-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="b793a-118">Kliknij opcję **Testuj**, a zostanie otwarty formularz **Warunek testowy przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="b793a-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="b793a-119">Wybierz rekord w obszarze **Sprawdź poprawność warunku** formularza.</span><span class="sxs-lookup"><span data-stu-id="b793a-119">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="b793a-120">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="b793a-120">Click **Test**.</span></span> <span data-ttu-id="b793a-121">System oszacuje rekord i określi, czy rekord spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="b793a-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="b793a-122">Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do formularza **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="b793a-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>
