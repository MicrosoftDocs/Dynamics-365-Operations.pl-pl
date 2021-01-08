---
title: Odpowiedzialni konserwatorzy
description: W tym temacie wyjaśniono, jak konfigurować odpowiedzialnych konserwatorów w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 113ee2b45c569c7dae3609f1027e31c4e5e5c54a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435333"
---
# <a name="responsible-maintenance-workers"></a><span data-ttu-id="4b3e3-103">Odpowiedzialni konserwatorzy</span><span class="sxs-lookup"><span data-stu-id="4b3e3-103">Responsible maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="4b3e3-104">Odpowiedzialni konserwatorzy mogą być powiązani z typami składników majątku, składnikami majątku, lokalizacjami czynności konserwacyjnych, kategoriami typów zadań konserwacji, typami zadań konserwacji, wariantami typów zadań konserwacji oraz profesjami.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-104">Responsible maintenance workers can be related to asset types, assets, functional locations, maintenance job type categories, maintenance job types, maintenance job type variants, and trades.</span></span> <span data-ttu-id="4b3e3-105">Mogą oni być używane na zleceniach pracy i żądaniach konserwacyjnych w celu wskazania preferencji odnośnie do konserwatorów, którzy powinni być odpowiedzialni za zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-105">They can be used on work orders and maintenance requests to indicate a preference about the maintenance workers who should be responsible for a work order.</span></span> <span data-ttu-id="4b3e3-106">(Jednak konserwatorzy nie są koniecznie tymi samymi pracownikami, którzy mają zamiar wykonać zlecenie pracy). Użycie tej funkcji jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-106">(However, those maintenance workers aren't necessarily the same workers who are scheduled to carry out the work order.) Use of this functionality is optional.</span></span> <span data-ttu-id="4b3e3-107">Można na przykład wybrać w ten sposób odpowiedzialnych konserwatorów lub grupy pracowników do konkretnych typów pracy lub obszarów pracy.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-107">For example, it can be used to select responsible workers or worker groups for specific work types or work areas.</span></span>

<span data-ttu-id="4b3e3-108">Podczas cyklu życia zlecenia pracy lub cyklu realizacji żądania konserwacji odpowiedzialni konserwatorzy mogą być zmieniani lub aktualizowani.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-108">During a work order lifecycle or a maintenance request lifecycle, responsible maintenance workers can be changed or updated.</span></span> <span data-ttu-id="4b3e3-109">Taka zmiana lub aktualizacja może być związana na przykład ze zmianą stanu cyklu życia żądania konserwacji lub cyklu życia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-109">This change or update might be related to, for example, a change in the maintenance request lifecycle state or the work order lifecycle state.</span></span>

<span data-ttu-id="4b3e3-110">Ustawienia na stronie **Odpowiedzialni konserwatorzy** *nie* są używane podczas planowania zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-110">The setup on the **Responsible maintenance workers** page is *not* used during work order scheduling.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3e3-111">W module Zarządzanie środkami trwałymi można również konfigurować *preferowanych* konserwatorów, którzy mogą być przydzielani do zleceń pracy w planowaniu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-111">In Asset Management, you can also set up *preferred* maintenance workers who might be allocated to work orders during work order scheduling.</span></span>

<span data-ttu-id="4b3e3-112">Aby można było skonfigurować odpowiedzialnych konserwatorów, należy skonfigurować pracowników oraz grupy konserwatorów, które powinny być dostępne do wybrania.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-112">Before you can set up responsible maintenance workers, you must set up the workers and maintenance worker groups that should be available for selection.</span></span> <span data-ttu-id="4b3e3-113">Aby uzyskać informacje na temat konfiguracji pracowników i grup konserwatorów, zobacz temat [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="4b3e3-113">For information about how to set up workers and maintenance worker groups, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-responsible-maintenance-workers"></a><span data-ttu-id="4b3e3-114">Ustawienia odpowiedzialnych konserwatorów</span><span class="sxs-lookup"><span data-stu-id="4b3e3-114">Set up responsible maintenance workers</span></span>

1. <span data-ttu-id="4b3e3-115">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Pracownicy** \> **Odpowiedzialni konserwatorzy**.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-115">Select **Asset management** \> **Setup** \> **Workers** \> **Responsible maintenance workers**.</span></span>
2. <span data-ttu-id="4b3e3-116">Wybierz **Nowy**, aby utworzyć rekord.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-116">Select **New** to create a record.</span></span>
3. <span data-ttu-id="4b3e3-117">Najpierw utwórz konfigurację odpowiedzialnego konserwatora lub grupy odpowiedzialnych konserwatorów, w której trzeba ustawić tylko pole **Grupa odpowiedzialnych konserwatorów** i/lub pole **Odpowiedzialny pracownik**.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-117">First create a default responsible maintenance worker or responsible maintenance worker group setup, where you set only the **Responsible maintenance worker group** field and/or the **Responsible worker** field.</span></span> <span data-ttu-id="4b3e3-118">Pozostaw pola zostaw puste.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-118">Leave the remaining fields blank.</span></span> <span data-ttu-id="4b3e3-119">Ta domyślna konfiguracja będzie używana podczas planowania zleceń pracy, jeśli żadna inna określona kombinacja nie pasuje do zawartości zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-119">This default setup will be used during work order scheduling if no other, more specific combination matches the contents of the work order.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b3e3-120">Podczas tworzenia żądania konserwacji, gdy odpowiedzialny konserwator lub grupa odpowiedzialnych konserwatorów są dostępne do wybrania na stronie **Wszystkie żądania konserwacji**, moduł Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy odpowiedzialnych konserwatorów, aby sprawdzić, czy są możliwe dopasowania.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-120">During creation of a maintenance request, when a responsible maintenance worker or responsible maintenance worker group is made available for selection on the **All maintenance requests** page, Asset Management goes through all responsible maintenance worker records to check for a possible match.</span></span> <span data-ttu-id="4b3e3-121">W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-121">It always checks the most specific combination first.</span></span> <span data-ttu-id="4b3e3-122">Innymi słowy, moduł Zarządzanie składnikami majątku najpierw sprawdza dopasowanie dla pola **Profesja**.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-122">In other words, Asset Management first checks for a match for the **Trade** field.</span></span> <span data-ttu-id="4b3e3-123">Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Wariant typu zadania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-123">If no match is found, it checks for a match for the **Maintenance job type variant** field.</span></span> <span data-ttu-id="4b3e3-124">Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Wariant typu zadania konserwacji** itd.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-124">If no match is found, it checks for a match for the **Maintenance job type** field, and so on.</span></span> <span data-ttu-id="4b3e3-125">Jak widać w układzie strony, to zachowanie to oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej w celu dopasowania (najpierw **Profesja**, następnie **Wariant typu zadania konserwacji**, następnie **Typ zadania konserwacji**, następnie **Kategoria typu zadania konserwacji**, następnie **Lokalizacja czynności konserwacyjnych**, następnie **Składnik majątku** i na końcu **Typ składnika majątku**).</span><span class="sxs-lookup"><span data-stu-id="4b3e3-125">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match (first **Trade**, then **Maintenance job type variant**, then **Maintenance job type**, then **Maintenance job type category**, then **Functional location**, then **Asset**, and finally **Asset type**).</span></span> <span data-ttu-id="4b3e3-126">Jeśli nie uda się znaleźć dopasowania, jest używany rekord domyślny, który nie ma zaznaczeń w tych siedmiu polach.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-126">If no match is found, the default record that has no selections in those seven fields is used.</span></span>

<span data-ttu-id="4b3e3-127">Na poniższej ilustracji pokazano przykład strony **Odpowiedzialni konserwatorzy**.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-127">The following illustration shows an example of the **Responsible maintenance workers** page.</span></span>

![Strona Odpowiedzialni konserwatorzy](media/08-setup-for-requests.png)
