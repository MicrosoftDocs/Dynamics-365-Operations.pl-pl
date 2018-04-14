--- 
title: Tworzenie klasy roboczej
description: "W tej procedurze pokazano sposób konfigurowania klasy pracy."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 11e506c41eb5e8d5bd28db8e6d5ca51ff9e72a62
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-work-class"></a><span data-ttu-id="db4fa-103">Tworzenie klasy roboczej</span><span class="sxs-lookup"><span data-stu-id="db4fa-103">Create a work class</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db4fa-104">W tej procedurze pokazano sposób konfigurowania klasy pracy.</span><span class="sxs-lookup"><span data-stu-id="db4fa-104">This procedure shows you how to set up a work class.</span></span> <span data-ttu-id="db4fa-105">Klas pracy są używane do kierowania i/lub ograniczania typów wierszy zlecenia, które pracownik magazynu może przetwarzać na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="db4fa-105">Work classes are used to direct and/or limit the type of work order lines that a warehouse worker can process on a mobile device.</span></span> <span data-ttu-id="db4fa-106">Wiersze, które pracownik może przetwarzać, zależą od klas pracy w elementach menu urządzenia przenośnego, do których pracownik magazynu ma dostęp, oraz od klasy pracy określonej w wierszach pracy.</span><span class="sxs-lookup"><span data-stu-id="db4fa-106">The lines that a worker can process are determined from the work classes on the mobile device menu items that the warehouse worker has access to and the work class that’s specified on the work lines.</span></span> <span data-ttu-id="db4fa-107">Klas pracy mogą służyć także do sprawdzania poprawności lokalizacji odłożenia dla wiersza zlecenia.</span><span class="sxs-lookup"><span data-stu-id="db4fa-107">Work classes can also be used to validate the put location for a work order line.</span></span> <span data-ttu-id="db4fa-108">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="db4fa-108">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="db4fa-109">Ta procedura jest przeznaczona dla kierownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="db4fa-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="db4fa-110">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Klasy robocze.</span><span class="sxs-lookup"><span data-stu-id="db4fa-110">Go to Warehouse management > Setup > Work > Work classes.</span></span>
2. <span data-ttu-id="db4fa-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="db4fa-111">Click New.</span></span>
3. <span data-ttu-id="db4fa-112">W polu Identyfikator klasy roboczej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="db4fa-112">In the Work class ID field, type a value.</span></span>
4. <span data-ttu-id="db4fa-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="db4fa-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db4fa-114">W polu Typ zlecenia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="db4fa-114">In the Work order type field, select an option.</span></span>
6. <span data-ttu-id="db4fa-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="db4fa-115">Click New.</span></span>
7. <span data-ttu-id="db4fa-116">W polu Typ lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="db4fa-116">In the Location type field, type a value.</span></span>
    * <span data-ttu-id="db4fa-117">Jeśli wybrano typ lokalizacji, tworzy to ograniczenie dotyczące tego, gdzie można odkładać towary po pobraniu.</span><span class="sxs-lookup"><span data-stu-id="db4fa-117">If you select a location type, this sets a restriction on where items can be put after they’ve been picked.</span></span> <span data-ttu-id="db4fa-118">To ustawienie jest używane, gdy dyrektywa lokalizacji próbuje rozpoznać lokalizację lub gdy pracownik magazynu ręcznie podaje lokalizację w elemencie menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="db4fa-118">This setting is used when a location directive tries to resolve the location, or if a warehouse worker manually provides the location for the mobile device menu item.</span></span>  
8. <span data-ttu-id="db4fa-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="db4fa-119">Close the page.</span></span>


