---
title: Ustawianie etapów zlecenia serwisowego
description: Można ustawić etapy zlecenia serwisowego.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30f6a6afa6ab91bed41bb19b8312dc7e25bd2478
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551726"
---
# <a name="set-up-service-order-stages"></a><span data-ttu-id="cd75f-103">Ustawianie etapów zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="cd75f-103">Set up service order stages</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="cd75f-104">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Zlecenia serwisowe** \> **Etapy serwisu**.</span><span class="sxs-lookup"><span data-stu-id="cd75f-104">Click **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="cd75f-105">Naciśnij kombinację klawiszy CTRL+N, aby utworzyć nowy rekord.</span><span class="sxs-lookup"><span data-stu-id="cd75f-105">Press CTRL+N to create a new record.</span></span>

3.  <span data-ttu-id="cd75f-106">W polach **Etap serwisu** i **Opis** wprowadź identyfikator i opis etapu serwisu.</span><span class="sxs-lookup"><span data-stu-id="cd75f-106">In the **Service stage** and **Description** fields, specify a service stage ID and description.</span></span>

4.  <span data-ttu-id="cd75f-107">Wybierz odpowiednie parametry etapu.</span><span class="sxs-lookup"><span data-stu-id="cd75f-107">Select the appropriate parameters for the stage.</span></span>

5.  <span data-ttu-id="cd75f-108">Wybierz etap nadrzędny dla bieżącego etapu lub pozostaw pole **Nadrzędne** puste, jeśli ten etap jest etapem początkowym w konfiguracji etapów.</span><span class="sxs-lookup"><span data-stu-id="cd75f-108">Select the parent stage for the current stage or leave the **Parent** field blank if the stage is the initial stage in the stage setup.</span></span>


> [!NOTE]
> <P><span data-ttu-id="cd75f-109">Po zapisaniu etapu nie można zmodyfikować pola <STRONG>Nadrzędne</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cd75f-109">You cannot modify the <STRONG>Parent</STRONG> field after you save the stage.</span></span> <span data-ttu-id="cd75f-110">Zamiast tego należy usunąć rekord i utworzyć go ponownie, dokonując innego wyboru w polu <STRONG>Nadrzędne</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cd75f-110">Instead, you can delete the record and create the record again with a different selection in the <STRONG>Parent</STRONG> field.</span></span></P>
> <P><span data-ttu-id="cd75f-111">Ponadto można utworzyć tylko jeden etap z pustym polem <STRONG>Nadrzędne</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cd75f-111">Also, you can only create one stage with a blank <STRONG>Parent</STRONG> field.</span></span> <span data-ttu-id="cd75f-112">Oznacza to, że jest dozwolony tylko jeden etap początkowy.</span><span class="sxs-lookup"><span data-stu-id="cd75f-112">That is, only one initial stage is permitted.</span></span></P>


  


