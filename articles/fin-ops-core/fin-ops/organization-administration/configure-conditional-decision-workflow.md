---
title: Konfigurowanie decyzji warunkowych w przepływie pracy
description: Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed53eeb26e1b4b1df1647739ce1d115c7dd169f8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747938"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a><span data-ttu-id="f3d0d-103">Konfigurowanie decyzji warunkowych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="f3d0d-103">Configure conditional decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3d0d-104">Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="f3d0d-105">Decyzja warunkowa to punkt, w którym przepływ pracy rozdziela się na dwie gałęzie.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="f3d0d-106">Aby skonfigurować decyzję warunkową, w edytorze przepływu pracy kliknij decyzję warunkową prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta formularz **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="f3d0d-107">Nazywanie decyzji</span><span class="sxs-lookup"><span data-stu-id="f3d0d-107">Name a decision</span></span>

<span data-ttu-id="f3d0d-108">Wykonaj następujące kroki, aby nazwać decyzję warunkową.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-108">Follow these steps to enter a name for a conditional decision.</span></span>

1. <span data-ttu-id="f3d0d-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f3d0d-110">W polu **Nazwa** wprowadź unikatową nazwę decyzji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="f3d0d-111"> Konfigurowanie warunków</span><span class="sxs-lookup"><span data-stu-id="f3d0d-111">Set conditions</span></span>

<span data-ttu-id="f3d0d-112">System decyduje, której gałęzi użyć, oceniając przesłany dokument, aby ustalić, czy spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>

1. <span data-ttu-id="f3d0d-113">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f3d0d-114">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-114">Click **Add condition**.</span></span>
3. <span data-ttu-id="f3d0d-115">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-115">Enter a condition.</span></span>
4. <span data-ttu-id="f3d0d-116">Wprowadź dodatkowe warunki, jeśli są wymagane.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-116">Enter additional conditions, if they are required.</span></span>
5. <span data-ttu-id="f3d0d-117">Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="f3d0d-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="f3d0d-118">Kliknij opcję **Testuj**, a zostanie otwarty formularz **Warunek testowy przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="f3d0d-119">Wybierz rekord w obszarze **Sprawdź poprawność warunku** formularza.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-119">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="f3d0d-120">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-120">Click **Test**.</span></span> <span data-ttu-id="f3d0d-121">System oszacuje rekord i określi, czy rekord spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="f3d0d-122">Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do formularza **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]