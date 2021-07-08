---
title: Usługa Regulatory Configuration Service (RCS) — usuwanie środowiska RCS
description: Ten temat wyjaśnia, jak administrator systemu Regulatory Configuration Service (RCS) może usunąć środowisko RCS i związane z nim dane.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 637962cf63bfd8c2330726f33545f939ec91d58d
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295825"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a><span data-ttu-id="ebbfa-103">Usługa Regulatory Configuration Service (RCS) — usuwanie środowiska RCS</span><span class="sxs-lookup"><span data-stu-id="ebbfa-103">Regulatory Configuration Service (RCS) - Delete an RCS environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ebbfa-104">Ten temat wyjaśnia, jak administrator systemu Regulatory Configuration Service (RCS) może usunąć środowisko RCS i związane z nim dane.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-104">This topic explains how a Regulatory Configuration Service (RCS) system administrator can delete an RCS environment and related data.</span></span>

<span data-ttu-id="ebbfa-105">Przed wykonaniem procedury opisanej w tym temacie muszą być spełnione następujące warunki wstępne:</span><span class="sxs-lookup"><span data-stu-id="ebbfa-105">Before you can complete the procedure in this topic, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ebbfa-106">Musisz mieć przypisaną rolę **Administrator systemu** dla środowiska RCS.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-106">You must have the **System Admin** role assigned to you for the RCS environment.</span></span>
- <span data-ttu-id="ebbfa-107">Rola **System Admin** musi mieć przypisaną rolę **RCSDeleteEnvironmentDuty**.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-107">The **System Admin** role must have the **RCSDeleteEnvironmentDuty** role assigned to it.</span></span>

## <a name="delete-an-rcs-environment"></a><span data-ttu-id="ebbfa-108">Usuwanie środowiska RCS</span><span class="sxs-lookup"><span data-stu-id="ebbfa-108">Delete an RCS environment</span></span>

1. <span data-ttu-id="ebbfa-109">Otwórz RCS wybierz kafelek roboczy **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-109">Open RCS, and select the **Electronic reporting** workspace tile.</span></span>
2. <span data-ttu-id="ebbfa-110">W sekcji **Łącza pokrewne** wybierz opcję **Usuń środowisko z RCS**.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-110">In the **Related links** section, select **Delete RCS environment**.</span></span>

    ![Usuń łącze do środowiska RCS w sekcji Powiązane łącza](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. <span data-ttu-id="ebbfa-112">W oknie dialogowym, które się pojawi, przejrzyj komunikaty o zakresie usuwania środowiska.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-112">In the dialog box that appears, review the messages about the scope of environment deletion.</span></span>

    ![Komunikaty w oknie dialogowym Usuń środowisko RCS](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="ebbfa-114">Nie można wycofać usunięcia środowiska RCS.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-114">Deletion of an RCS environment can't be reversed.</span></span>
    >
    > <span data-ttu-id="ebbfa-115">Operacja usuwa wybrane środowisko RCS i wszelkie powiązane z nim dane, w tym cechy i konfiguracje, które są przechowywane w repozytorium globalnym.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-115">The operation deletes the selected RCS environment and any related data, including features and configurations that are stored in the Global repository.</span></span> <span data-ttu-id="ebbfa-116">Cechy i konfiguracje, które są współdzielone z innymi organizacjami, zostaną usunięte, jeśli nie mają żadnych zależności.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-116">Features and configurations that are shared with other organizations will be unshared and deleted if they have no dependencies.</span></span> <span data-ttu-id="ebbfa-117">Funkcje i konfiguracje, które posiadają zależności zostaną oznaczone jako wycofane z użycia.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-117">Features and configurations that have dependencies will be marked as discontinued.</span></span>

4. <span data-ttu-id="ebbfa-118">W polu, które się pojawi, wpisz globalnie unikalny identyfikator (GUID) środowiska RCS, by potwierdzić, że chcesz je usunąć.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-118">In the field that is provided, enter the globally unique identifier (GUID) of the RCS environment to confirm that you want to delete it.</span></span> <span data-ttu-id="ebbfa-119">Identyfikator GUID środowiska jest dołączany do wiadomości o usunięciu.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-119">The environment's GUID is included in the deletion message.</span></span>
5. <span data-ttu-id="ebbfa-120">Wybierz **Usuń środowisko**.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-120">Select **Delete environment**.</span></span>
    
<span data-ttu-id="ebbfa-121">Twoje środowisko RCS i wszelkie związane z nim dane są teraz usuwane.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-121">Your RCS environment and any related data are now deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebbfa-122">Po usunięciu środowiska RCS, nie ma sposobu na odzyskanie danych.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-122">After you delete an RCS environment, there is no way to recover the data.</span></span> <span data-ttu-id="ebbfa-123">Nowe środowisko RCS może być utworzone w każdym dostępnym regionie RCS.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-123">A new RCS environment can be created in any available RCS region.</span></span>
