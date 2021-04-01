---
title: Typy żądania konserwacji
description: W tym temacie wyjaśniono, jak konfigurować typu żądań konserwacji w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e4f622cda62cad13a8146cbc26bc2e5f1a45222
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261196"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="7e7a6-103">Typy żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="7e7a6-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="7e7a6-104">Typy żądań konserwacji służą do klasyfikowania żądań konserwacji.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="7e7a6-105">Na przykład mogą istnieć typy żądań konserwacji, które są związane z konserwacją prewencyjną i naprawczą.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="7e7a6-106">Można również mieć specjalny typ żądania konserwacji służący do zarządzania naprawą składnikami majątku (naprawa w magazynie).</span><span class="sxs-lookup"><span data-stu-id="7e7a6-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="7e7a6-107">Typ żądania konserwacji określa przynależność do grupy stanów cyklu życia żądania konserwacji (model cyklu życia konserwacji).</span><span class="sxs-lookup"><span data-stu-id="7e7a6-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="7e7a6-108">Modele cyklu życia żądania konserwacji definiują stany cyklu życia, które można skonfigurować dla żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="7e7a6-109">(Przykłady stanów cyklu życia żądania konserwacji obejmują **Utworzony**, **Aktywny** i **Zakończony**).</span><span class="sxs-lookup"><span data-stu-id="7e7a6-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="7e7a6-110">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Typy żądań konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="7e7a6-111">Wybierz pozycję **Nowy**, aby utworzyć typ żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="7e7a6-112">W polu **Typ żądania konserwacji** wprowadź identyfikator typu żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="7e7a6-113">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="7e7a6-114">Na skróconej karcie **Ogólne** w polu **Model cyklu życia żądania konserwacji** wybierz model cyklu życia żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="7e7a6-115">W polu **Typ zlecenia pracy** wybierz typ zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="7e7a6-116">Gdy żądanie konserwacji jest konwertowane na zlecenie pracy, zlecenie pracy automatycznie otrzymuje typ zlecenia pracy powiązany z typem żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="7e7a6-117">Na poniższej ilustracji pokazano przykład strony **Typy żądań konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="7e7a6-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Strona Typy żądania konserwacji](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]