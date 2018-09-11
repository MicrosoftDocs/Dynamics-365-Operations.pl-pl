--- 
title: "Wyświetl historię przepływu pracy"
description: "Te czynności umożliwiają wyświetlenie stanu dokumentu przesłanego do systemu przepływu pracy w celu przetworzenia i zatwierdzenia."
author: jasongre
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: bd0376879206c3b751cce820037ac1d39e120b4c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="view-workflow-history"></a><span data-ttu-id="c0436-103">Wyświetl historię przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="c0436-103">View workflow history</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c0436-104">Te czynności umożliwiają wyświetlenie stanu dokumentu przesłanego do systemu przepływu pracy w celu przetworzenia i zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="c0436-104">Use these steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="c0436-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c0436-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="c0436-106">Wybierz kolejno opcje Wspólne > Zapytania > Przepływ pracy > Historia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="c0436-106">Go to Common > Inquiries > Workflow > Workflow history.</span></span>
    * <span data-ttu-id="c0436-107">Ten formularz umożliwia wyświetlenie stanu dokumentu przesłanego do przepływu pracy w celu przetworzenia i zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="c0436-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    * <span data-ttu-id="c0436-108">Opcja Identyfikator wystąpienia to kod identyfikacyjny wystąpienia przepływu pracy, w ramach którego jest przetwarzany lub został przetworzony dokument.</span><span class="sxs-lookup"><span data-stu-id="c0436-108">The Instance ID is      the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="c0436-109">Opcja Stan to stan dokumentu w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="c0436-109">The Status is the workflow status of the document.</span></span>  
    * <span data-ttu-id="c0436-110">Opcja Identyfikator przepływu pracy to kod identyfikacyjny przepływu pracy, w ramach którego jest przetwarzany lub został przetworzony dokument.</span><span class="sxs-lookup"><span data-stu-id="c0436-110">The Workflow ID is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="c0436-111">Opcja Dokument to kod identyfikacyjny dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c0436-111">The Document is the identification code of the document.</span></span>  
    * <span data-ttu-id="c0436-112">Opcja Typ dokumentu to typ dokumentu przesłanego do przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="c0436-112">The Document type is the type of document that was submitted for processing.</span></span>  
    * <span data-ttu-id="c0436-113">Opcja Przepływ pracy to nazwa przepływu pracy, w ramach którego jest przetwarzany lub został przetworzony dokument.</span><span class="sxs-lookup"><span data-stu-id="c0436-113">The Workflow is the name of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="c0436-114">Opcja Wersja to numer wersji przepływu pracy, w ramach którego jest przetwarzany lub został przetworzony dokument.</span><span class="sxs-lookup"><span data-stu-id="c0436-114">The Version is the version number of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="c0436-115">Opcja Data i godzina utworzenia to data i godzina przesłania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c0436-115">The Created date and time is the date and time that the document was submitted.</span></span>  
    * <span data-ttu-id="c0436-116">Opcja Upłynęło czasu to ilość czasu, jaka upłynęła od przesłania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c0436-116">The Elapsed time is the time that has passed since the document was submitted.</span></span>  
    * <span data-ttu-id="c0436-117">Przycisk Wznów umożliwia wznowienie procesu przepływu pracy dla wybranego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c0436-117">The Resume button allows you to resume the workflow process for the selected document.</span></span>  
    * <span data-ttu-id="c0436-118">Przycisk Wycofaj umożliwia wycofywanie wybranego dokumentu, tak aby nie był przetwarzany.</span><span class="sxs-lookup"><span data-stu-id="c0436-118">The Recall button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="c0436-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c0436-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c0436-120">Upewnij się, że jest rozwinięta sekcja Elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="c0436-120">Make sure the Work items section is expanded.</span></span>    <span data-ttu-id="c0436-121">W tej sekcji można obejrzeć elementy pracy skojarzone z wybranym dokumentem.</span><span class="sxs-lookup"><span data-stu-id="c0436-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="c0436-122">Na przykład może być konieczne wykonanie zadania lub zatwierdzenie dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c0436-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    * <span data-ttu-id="c0436-123">Przycisk Przypisz ponownie powoduje otwarcie okna dialogowego, w którym można przepisać element pracy do innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c0436-123">The Reassign button will open a dialog box where you can reassign a work item to another user.</span></span>  
    * <span data-ttu-id="c0436-124">Upewnij się, że jest rozwinięta sekcja Szczegóły śledzenia.</span><span class="sxs-lookup"><span data-stu-id="c0436-124">Make sure the Tracking details section is expanded.</span></span>    <span data-ttu-id="c0436-125">W tej sekcji można obejrzeć historię przepływu pracy dla wybranego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c0436-125">In this section you can view the workflow history of the selected document.</span></span>  


