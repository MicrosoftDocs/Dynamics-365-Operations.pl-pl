---
title: Poziomy usług składnika majątku
description: W tym temacie wyjaśniono poziomy usług składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6dad0cb480f69eac84df5ea9a67f2adb94e2f52c
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811816"
---
# <a name="asset-service-levels"></a><span data-ttu-id="08c02-103">Poziomy usług składnika majątku</span><span class="sxs-lookup"><span data-stu-id="08c02-103">Asset service levels</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="08c02-104">W tym temacie wyjaśniono poziomy usług składników majątku w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="08c02-104">This topic explains asset service levels in Asset Management.</span></span> <span data-ttu-id="08c02-105">Poziomy usługi składników majątku są związane ze składnikami majątku i są przenoszone do żądań konserwacji i zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="08c02-105">Asset service levels are related to assets, and are transferred to maintenance requests and work orders.</span></span> <span data-ttu-id="08c02-106">Są one używane do obliczania priorytetu zleceń pracy podczas planowania zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="08c02-106">They are used to calculate the priority of work orders during work order scheduling.</span></span> <span data-ttu-id="08c02-107">Poziomy usług składników majątku można zmienić, jeśli wymagane są zmiany.</span><span class="sxs-lookup"><span data-stu-id="08c02-107">Asset service levels can be changed, if changes are required.</span></span>

<span data-ttu-id="08c02-108">Aby uzyskać więcej informacji na temat konfiguracji, która jest powiązana z obliczaniem oceny wyników dla planowania zlecenia pracy, zobacz temat [Parametry modułu Zarządzania składnikami majątku](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="08c02-108">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span> <span data-ttu-id="08c02-109">Trzeba skonfigurować co najmniej jeden rekord domyślny dla poziomu usługi składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="08c02-109">You must set up at least one default record for the asset service level.</span></span> <span data-ttu-id="08c02-110">Ten rekord domyślny jest używany, jeśli nie znaleziono innego dopasowania podczas planowania zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="08c02-110">This default record is used if no other match is found during work order scheduling.</span></span>

<span data-ttu-id="08c02-111">**Przykład 1:** domyślny poziom usługi, który jest używany, jeśli nie znaleziono innego dopasowania.</span><span class="sxs-lookup"><span data-stu-id="08c02-111">**Example 1:** The default service level that is used if no other match is found.</span></span> <span data-ttu-id="08c02-112">W tym rekordzie można wybrać tylko poziom usługi.</span><span class="sxs-lookup"><span data-stu-id="08c02-112">In this record, you select only a service level.</span></span>

<span data-ttu-id="08c02-113">**Przykład 2:** wysoki poziom usług używany do planowania zadań dla silnika ciężarówki Volvo.</span><span class="sxs-lookup"><span data-stu-id="08c02-113">**Example 2:** A high service level that is used to schedule jobs for a Volvo truck engine.</span></span> <span data-ttu-id="08c02-114">W tym rekordzie należy wybrać odpowiedni typ składnika majątku (np. **silnik ciężarówki**), producenta (**Volvo**) oraz poziom usługi.</span><span class="sxs-lookup"><span data-stu-id="08c02-114">In this record, you select a relevant asset type (such as **Truck Engine**), a manufacturer (**Volvo**), and a service level.</span></span>

## <a name="set-up-asset-service-levels"></a><span data-ttu-id="08c02-115">Konfigurowanie poziomów usługi składnika majątku</span><span class="sxs-lookup"><span data-stu-id="08c02-115">Set up asset service levels</span></span>

1. <span data-ttu-id="08c02-116">Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Poziomy usługi składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="08c02-116">Select **Asset management** \> **Setup** \> **Asset service levels**.</span></span>
2. <span data-ttu-id="08c02-117">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="08c02-117">Select **New** to create a record.</span></span>
3. <span data-ttu-id="08c02-118">W zależności od poziomu szczegółowości wymaganego dla poziomu usługi składnika majątku dokonaj odpowiednich wyborów w polach **Lokalizacja czynności konserwacyjnych**, **Typ składnika majątku**, **Producent**, **Model**, **Składnik majątku**, **Typ zlecenia pracy** oraz **Poziom usługi**.</span><span class="sxs-lookup"><span data-stu-id="08c02-118">Depending on the detail level that is required for the asset service level, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Work order type**, and **Service level** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="08c02-119">Gdy poziom usługi aktywów jest używany w odniesieniu do żądań konserwacji i zleceń pracy, zarządzanie składnikami majątku przechodzi przez wszystkie rekordy poziomu usługi składnika majątku, aby sprawdzić, czy możliwe dopasowanie.</span><span class="sxs-lookup"><span data-stu-id="08c02-119">When the asset service level is used for maintenance requests and work orders, Asset Management goes through all asset service level records to check for a possible match.</span></span> <span data-ttu-id="08c02-120">W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową.</span><span class="sxs-lookup"><span data-stu-id="08c02-120">It always checks the most specific combination first.</span></span> <span data-ttu-id="08c02-121">Innymi słowy, moduł Zarządzanie składnikami majątku najpierw sprawdza dopasowanie dla pola **Typ zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="08c02-121">In other words, Asset Management first checks for a match for the **Work order type** field.</span></span> <span data-ttu-id="08c02-122">Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Składnik majątku** itd.</span><span class="sxs-lookup"><span data-stu-id="08c02-122">If no match is found, it checks for a match for the **Asset** field, and so on.</span></span> <span data-ttu-id="08c02-123">Jak widać w układzie strony **Poziomy usług składnika majątku** to zachowanie oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej pod kątem dopasowania.</span><span class="sxs-lookup"><span data-stu-id="08c02-123">As you can see in the layout of the **Asset service levels** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="08c02-124">Jeśli nie uda się znaleźć dopasowania, jest używany rekord domyślny, który nie ma zaznaczeń w tych polach.</span><span class="sxs-lookup"><span data-stu-id="08c02-124">If no match is found, the default record that has no selections in those fields is used.</span></span>

4. <span data-ttu-id="08c02-125">W polu **Poziom usługi** wybierz numer wskazujący poziom usługi (priorytet).</span><span class="sxs-lookup"><span data-stu-id="08c02-125">In the **Service level** field, select a number that indicates the service level (priority).</span></span>


> [!NOTE]
> <span data-ttu-id="08c02-126">Jeśli zmienisz rekord poziomu usługi składnika majątku na stronie **Poziomy usługi składnika majątku** już po jego użyciu w zleceniu pracy, poziom usługi na żądaniach konserwacji i zleceniach pracy nie jest odpowiednio aktualizowany.</span><span class="sxs-lookup"><span data-stu-id="08c02-126">If you change an asset service level record on the **Asset service levels** page after you've already used it on a work order, the service level on maintenance requests and work orders isn't updated accordingly.</span></span>
