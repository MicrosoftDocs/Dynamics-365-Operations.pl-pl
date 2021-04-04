---
title: Ustawianie etapów zlecenia serwisowego
description: Można ustawić etapy zlecenia serwisowego.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9774d5f4e97d3f768366ba552e5928929bacf508
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470936"
---
# <a name="set-up-service-order-stages"></a><span data-ttu-id="57552-103">Ustawianie etapów zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="57552-103">Set up service order stages</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="57552-104">Przejdź do **Zarządzanie serwisem** \> **Ustawienia** \> **Zlecenia serwisowe** \> **Etapy serwisu**.</span><span class="sxs-lookup"><span data-stu-id="57552-104">Go to **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="57552-105">Wybierz pozycję **Nowy**, aby utworzyć nowy zapis.</span><span class="sxs-lookup"><span data-stu-id="57552-105">Select **New** to create a new record.</span></span>

3.  <span data-ttu-id="57552-106">W polach **Etap serwisu** i **Opis** wprowadź identyfikator i opis etapu serwisu.</span><span class="sxs-lookup"><span data-stu-id="57552-106">In the **Service stage** and **Description** fields, specify a service stage ID and description.</span></span>

4.  <span data-ttu-id="57552-107">Wybierz odpowiednie parametry etapu.</span><span class="sxs-lookup"><span data-stu-id="57552-107">Select the appropriate parameters for the stage.</span></span>

5.  <span data-ttu-id="57552-108">Wybierz etap nadrzędny dla bieżącego etapu lub pozostaw pole **Nadrzędne** puste, jeśli ten etap jest etapem początkowym w konfiguracji etapów.</span><span class="sxs-lookup"><span data-stu-id="57552-108">Select the parent stage for the current stage or leave the **Parent** field blank if the stage is the initial stage in the stage setup.</span></span>


> [!NOTE]
> <P><span data-ttu-id="57552-109">Po zapisaniu etapu nie można zmodyfikować pola <STRONG>Nadrzędne</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="57552-109">You cannot modify the <STRONG>Parent</STRONG> field after you save the stage.</span></span> <span data-ttu-id="57552-110">Zamiast tego należy usunąć rekord i utworzyć go ponownie, dokonując innego wyboru w polu <STRONG>Nadrzędne</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="57552-110">Instead, you can delete the record and create the record again with a different selection in the <STRONG>Parent</STRONG> field.</span></span></P>
> <P><span data-ttu-id="57552-111">Ponadto można utworzyć tylko jeden etap z pustym polem <STRONG>Nadrzędne</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="57552-111">Also, you can only create one stage with a blank <STRONG>Parent</STRONG> field.</span></span> <span data-ttu-id="57552-112">Oznacza to, że jest dozwolony tylko jeden etap początkowy.</span><span class="sxs-lookup"><span data-stu-id="57552-112">That is, only one initial stage is permitted.</span></span></P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]