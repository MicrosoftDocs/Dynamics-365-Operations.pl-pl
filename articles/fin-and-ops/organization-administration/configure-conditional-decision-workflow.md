---
title: "Konfigurowanie decyzji warunkowej w przepływie pracy"
description: "Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 597a6a254dcd623f9e7c59a0309eeedee1b5adee
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="configure-a-conditional-decision-in-a-workflow"></a><span data-ttu-id="8ab94-103">Konfigurowanie decyzji warunkowej w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="8ab94-103">Configure a conditional decision in a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8ab94-104">Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="8ab94-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="8ab94-105">Decyzja warunkowa to punkt, w którym przepływ pracy rozdziela się na dwie gałęzie.</span><span class="sxs-lookup"><span data-stu-id="8ab94-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="8ab94-106">Aby skonfigurować decyzję warunkową, w edytorze przepływu pracy kliknij decyzję warunkową prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta formularz **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="8ab94-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="8ab94-107">Nazywanie decyzji</span><span class="sxs-lookup"><span data-stu-id="8ab94-107">Name a decision</span></span>
<span data-ttu-id="8ab94-108">Wykonaj następujące kroki, aby nazwać decyzję warunkową.</span><span class="sxs-lookup"><span data-stu-id="8ab94-108">Follow these steps to enter a name for a conditional decision.</span></span>
1.  <span data-ttu-id="8ab94-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="8ab94-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="8ab94-110">W polu **Nazwa** wprowadź unikatową nazwę decyzji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="8ab94-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="8ab94-111"> Konfigurowanie warunków</span><span class="sxs-lookup"><span data-stu-id="8ab94-111">Set conditions</span></span>
<span data-ttu-id="8ab94-112">System decyduje, której gałęzi użyć, oceniając przesłany dokument, aby ustalić, czy spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="8ab94-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>
1.  <span data-ttu-id="8ab94-113">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="8ab94-113">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="8ab94-114">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="8ab94-114">Click **Add condition**.</span></span>
3.  <span data-ttu-id="8ab94-115">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="8ab94-115">Enter a condition.</span></span>
4.  <span data-ttu-id="8ab94-116">Wprowadź dodatkowe warunki, jeśli są wymagane.</span><span class="sxs-lookup"><span data-stu-id="8ab94-116">Enter additional conditions, if they are required.</span></span>
5.  <span data-ttu-id="8ab94-117">Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="8ab94-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>
    1.  <span data-ttu-id="8ab94-118">Kliknij opcję **Testuj**, a zostanie otwarty formularz **Warunek testowy przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="8ab94-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2.  <span data-ttu-id="8ab94-119">Wybierz rekord w obszarze **Sprawdź poprawność warunku** formularza.</span><span class="sxs-lookup"><span data-stu-id="8ab94-119">Select a record in the **Validate condition** area of the form.</span></span>
    3.  <span data-ttu-id="8ab94-120">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="8ab94-120">Click **Test**.</span></span> <span data-ttu-id="8ab94-121">System oszacuje rekord i określi, czy rekord spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="8ab94-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4.  <span data-ttu-id="8ab94-122">Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do formularza **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="8ab94-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>






