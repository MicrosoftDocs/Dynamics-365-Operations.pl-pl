---
title: Typy zleceń pracy
description: W tym temacie opisano typy zlecenia pracy w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6bdc9d226d8e1aa6960cac38b95b0245e46ee1ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825597"
---
# <a name="work-order-types"></a><span data-ttu-id="33ee9-103">Typy zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="33ee9-103">Work order types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="33ee9-104">Typy zleceń pracy służą do klasyfikowania zleceń.</span><span class="sxs-lookup"><span data-stu-id="33ee9-104">Work order types are used to categorize work orders.</span></span> <span data-ttu-id="33ee9-105">Na przykład mogą istnieć typy zleceń pracy, które są związane z konserwacją prewencyjną lub naprawczą.</span><span class="sxs-lookup"><span data-stu-id="33ee9-105">For example, you might have work orders that are related to preventive maintenance or corrective maintenance.</span></span>

<span data-ttu-id="33ee9-106">Typ zlecenia pracy definiuje przynależność do modelu cyklu życia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="33ee9-106">A work order type defines an affiliation with a work order lifecycle model.</span></span> <span data-ttu-id="33ee9-107">Model cyklu życia zlecenia pracy określa Stany cyklu życia zlecenia pracy, które można ustawiać w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="33ee9-107">A work order lifecycle model defines the work order lifecycle states that can be set on a work order.</span></span> <span data-ttu-id="33ee9-108">(Przykłady stanów cyklu życia zlecenia pracy **Utworzone**, **W trakcie przetwarzania** i **Zakończone**).</span><span class="sxs-lookup"><span data-stu-id="33ee9-108">(Examples of work order lifecycle states include **Created**, **In Process**, and **Finished**.)</span></span>

<span data-ttu-id="33ee9-109">Aby uzyskać więcej informacji na temat stanów cyklu życia zlecenia pracy i etapów projektu należy zapoznać się z [Stany cyklu życia zlecenia pracy](work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="33ee9-109">For more information about work order lifecycle states and project stages, see [Work order lifecycle states](work-order-lifecycle-states.md).</span></span>

1. <span data-ttu-id="33ee9-110">Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Typy zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="33ee9-110">Select **Asset management** \> **Setup** \> **Work orders** \> **Work order types**.</span></span>
2. <span data-ttu-id="33ee9-111">Wybierz pozycję **Nowy**, aby utworzyć nowy typ zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="33ee9-111">Select **New** to create a work order type.</span></span>
3. <span data-ttu-id="33ee9-112">W polu **Typ zlecenia pracy** wprowadź identyfikator typu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="33ee9-112">In the **Work order type** field, enter an ID for the work order type.</span></span>
4. <span data-ttu-id="33ee9-113">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="33ee9-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="33ee9-114">W polu **Model cyklu życia zlecenia pracy** wybierz model cyklu.</span><span class="sxs-lookup"><span data-stu-id="33ee9-114">In the **Work order lifecycle model** field, select a lifecycle model.</span></span>
5. <span data-ttu-id="33ee9-115">Ustawienie opcji **Jeden konserwator** na **Tak**, jeśli wszystkie zadania zlecenia pracy powiązane z danym typem zlecenia pracy powinny zostać zaplanowane do tego samego konserwatora.</span><span class="sxs-lookup"><span data-stu-id="33ee9-115">Set the **One maintenance worker** option to **Yes** if all work order jobs that are related to a work order of this type should be scheduled to the same maintenance worker.</span></span>
6. <span data-ttu-id="33ee9-116">W polu **Typ kosztu** wybierz odpowiednio **Korygujący**, **Zapobiegawczy** lub **Inwestycyjny**.</span><span class="sxs-lookup"><span data-stu-id="33ee9-116">In the **Cost type** field, select **Corrective**, **Preventive**, or **Investment**, as appropriate.</span></span> <span data-ttu-id="33ee9-117">Wszystkie zadania zlecenia pracy w zleceniu pracy muszą mieć ten sam typ kosztu.</span><span class="sxs-lookup"><span data-stu-id="33ee9-117">All work order jobs on a work order must have the same cost type.</span></span>
7. <span data-ttu-id="33ee9-118">W sekcji **Obowiązkowe** ustaw odpowiednie opcje na **Tak**, aby określić, które informacje związane z błędami lub przerwami konserwacyjnymi są dodawane do zlecenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="33ee9-118">In the **Mandatory** section, set the relevant options to **Yes** to specify which fault-related or maintenance downtime–related information is added to a work order of this type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33ee9-119">Opcje dostępne w sekcji **Obowiązkowe** są powiązane z opcjami na karcie skróconej **Weryfikuj** na stronie **Stany cyklu życia zlecenia pracy** (**Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Stany cyklu życia**).</span><span class="sxs-lookup"><span data-stu-id="33ee9-119">The options in the **Mandatory** section are related to the options on the **Validate** FastTab of the **Work order lifecycle states** page (**Asset management** \> **Setup** \> **Work orders** \> **Lifecycle states**).</span></span>

8. <span data-ttu-id="33ee9-120">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="33ee9-120">Select **Save**.</span></span>

![Typy zleceń pracy](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]