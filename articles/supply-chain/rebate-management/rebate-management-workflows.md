---
title: Przepływy pracy mające zastosowanie do umów z modułu Zarządzanie rabatami
description: W tym temacie opisano sposób skonfigurowania przepływu pracy umowy dotyczącej zarządzania rabatami, aby zatwierdzić i aktywować transakcje.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 16f1c56ecd69f4dc7bfd80e74d3f35147cc173d6
ms.sourcegitcommit: 890a0b3eb3c1f48d786b0789e5bb8641e0b8455e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5919826"
---
# <a name="rebate-management-deal-workflows"></a><span data-ttu-id="8f611-103">Przepływy pracy mające zastosowanie do umów z modułu Zarządzanie rabatami</span><span class="sxs-lookup"><span data-stu-id="8f611-103">Rebate management deal workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f611-104">Aby zatwierdzić transakcje rabatowe, w zarządzaniu rabatami jest używana ta sama platforma przepływu pracy co inne aplikacje Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8f611-104">To approve rebate deals, Rebate management uses the same workflow platform as other Finance and Operations apps.</span></span> <span data-ttu-id="8f611-105">Dwa procesy zadań są skojarzone z każdym przepływem pracy:</span><span class="sxs-lookup"><span data-stu-id="8f611-105">Two job processes are associated with every workflow:</span></span>

- <span data-ttu-id="8f611-106">Jeden element przepływu pracy aktywuje umowę, dzięki czemu użytkownik lub proces przepływu pracy może zatwierdzić transakcje.</span><span class="sxs-lookup"><span data-stu-id="8f611-106">One element of the workflow activates the deal so that the user or workflow process can approve the transactions.</span></span>
- <span data-ttu-id="8f611-107">Jeden element przepływu pracy zatwierdza umowę.</span><span class="sxs-lookup"><span data-stu-id="8f611-107">One element of the workflow approves the deal.</span></span>

<span data-ttu-id="8f611-108">Aby można było użyć umowy rabatowej, należy ją aktywnego w module **Zarządzanie rabatami**.</span><span class="sxs-lookup"><span data-stu-id="8f611-108">Before you can use a rebate deal, it must be active in the **Rebate management** module.</span></span> <span data-ttu-id="8f611-109">Aby aktywować umowę, należy najpierw utworzyć i skonfigurować *Przepływ pracy umowy w zarządzaniu rabatami*.</span><span class="sxs-lookup"><span data-stu-id="8f611-109">To activate a deal, you must first create and configure a *Rebate management deal workflow*.</span></span>

<span data-ttu-id="8f611-110">Po uaktywnieniu przepływu pracy w celu zarządzania rabatami użytkownicy nie mogą ręcznie zatwierdzać transakcji.</span><span class="sxs-lookup"><span data-stu-id="8f611-110">After a workflow is activated for Rebate management, users can't manually approve deals.</span></span> <span data-ttu-id="8f611-111">Przepływ pracy musi być zawsze używany.</span><span class="sxs-lookup"><span data-stu-id="8f611-111">The workflow must be always used.</span></span>

## <a name="create-and-manage-rebate-management-deal-workflows"></a><span data-ttu-id="8f611-112">Twórz przepływy pracy związane z zarządzaniem rabatami i zarządzaj nimi</span><span class="sxs-lookup"><span data-stu-id="8f611-112">Create and manage Rebate management deal workflows</span></span>

<span data-ttu-id="8f611-113">Aby pracować z przepływami pracy umów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia \> Przepływy pracy zarządzania rabatami**.</span><span class="sxs-lookup"><span data-stu-id="8f611-113">To work with your Rebate management deal workflows, go to **Rebate management \> Setup \> Rebate management workflows**.</span></span> <span data-ttu-id="8f611-114">W tym miejscu można w razie potrzeby wyświetlać, tworzyć i aktualizować przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="8f611-114">There, you can view, create, and update workflows as required.</span></span> <span data-ttu-id="8f611-115">W danym momencie może być aktywny tylko jeden przepływ pracy tego typu.</span><span class="sxs-lookup"><span data-stu-id="8f611-115">Only one workflow of this type can be active at a time.</span></span> <span data-ttu-id="8f611-116">Aby uzyskać więcej informacji na temat przepływów pracy, sposobu pracy ze stroną **Przepływy pracy zarządzania rabatami** oraz sposobu tworzenia przepływów pracy, zobacz [Omówienie systemu przepływu pracy](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) i powiązane tematy.</span><span class="sxs-lookup"><span data-stu-id="8f611-116">For more information about workflows, how to work with the **Rebate management workflows** page, and how to create workflows, see [Workflow system overview](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) and its related topics.</span></span>

## <a name="use-a-workflow-to-activate-a-deal"></a><span data-ttu-id="8f611-117">Aktywowanie umowy przy użyciu przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="8f611-117">Use a workflow to activate a deal</span></span>

<span data-ttu-id="8f611-118">Aby aktywować umowę za pomocą przepływu pracy, otwórz umowę (na przykład na stronie **Wszystkie umowy zarządzania rabatami**).</span><span class="sxs-lookup"><span data-stu-id="8f611-118">To activate a deal through a workflow, open the deal (for example, on the **All rebate management deals** page).</span></span> <span data-ttu-id="8f611-119">W okienku akcji wybierz **Przepływ pracy \> Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="8f611-119">Then, on the Action Pane, select **Workflow \> Submit**.</span></span> <span data-ttu-id="8f611-120">Po przetworzeniu i zatwierdzeniu nowej umowy za pomocą przepływu pracy będzie ona aktywna i gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="8f611-120">After the new deal has been processed and approved through the workflow, it will be active and ready to use.</span></span>

<span data-ttu-id="8f611-121">Po aktywowaniu umowy nie można zmienić jej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="8f611-121">After a deal has been activated, you can't change its setup.</span></span> <span data-ttu-id="8f611-122">Jeśli trzeba zmienić aktywną umowę, ją dezaktywować, a następnie utworzyć nową umowę.</span><span class="sxs-lookup"><span data-stu-id="8f611-122">If you must change an active deal, inactivate it, and then create a new deal.</span></span> <span data-ttu-id="8f611-123">Jeśli nowa umowa przypomina starą umowę, można ją utworzyć, kopiując starą umowę.</span><span class="sxs-lookup"><span data-stu-id="8f611-123">If the new deal will resemble the old deal, you can create it by copying the old deal.</span></span>
