---
title: Kontrola wyrywkowa towaru zarządzania jakością
description: W tym temacie opisano sposób konfigurowania kontroli wyrywkowej towaru.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022235"
---
# <a name="quality-management-item-sampling"></a><span data-ttu-id="a53f4-103">Kontrola wyrywkowa towaru zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="a53f4-103">Quality management item sampling</span></span>

<span data-ttu-id="a53f4-104">Kontrola wyrywkowa towaru jest używana jako część skojarzenia jakości.</span><span class="sxs-lookup"><span data-stu-id="a53f4-104">Item sampling is used as part of a quality association.</span></span> <span data-ttu-id="a53f4-105">Określa ona ilość bieżących zapasów fizycznych, które muszą zostać sprawdzone.</span><span class="sxs-lookup"><span data-stu-id="a53f4-105">It defines the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="a53f4-106">Kontrola wyrywkowa może dotyczyć stałej ilości lub części określonej procentowo lub pełnego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a53f4-106">Sampling can be based on fixed quantities, a percentage, or a full license plate.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="a53f4-107">Konfigurowanie wyrywkowej kontroli towarów</span><span class="sxs-lookup"><span data-stu-id="a53f4-107">Set up item sampling</span></span>

<span data-ttu-id="a53f4-108">Wykonaj następujące czynności, aby skonfigurować kontrolę wyrywkową towarów.</span><span class="sxs-lookup"><span data-stu-id="a53f4-108">Follow these steps to set up item sampling.</span></span>

1. <span data-ttu-id="a53f4-109">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Kontrola wyrywkowa towarów**.</span><span class="sxs-lookup"><span data-stu-id="a53f4-109">Go to **Inventory management \> Setup \> Quality control \> Item sampling**.</span></span>
1. <span data-ttu-id="a53f4-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a53f4-110">Select **New**.</span></span>
1. <span data-ttu-id="a53f4-111">W polu **Kontrola wyrywkowa towarów** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a53f4-111">In the **Item sampling** field, enter a value.</span></span>
1. <span data-ttu-id="a53f4-112">W polu **Opis** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a53f4-112">In the **Description** field, enter a value.</span></span>
1. <span data-ttu-id="a53f4-113">W polu **Wartość** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a53f4-113">In the **Value** field, enter a number.</span></span> <span data-ttu-id="a53f4-114">Ta wartość odnosi się do wartości specyfikacji ilości wybranej w sąsiednim polu.</span><span class="sxs-lookup"><span data-stu-id="a53f4-114">This value is related to the quantity specification value that is selected in the adjacent field.</span></span>
1. <span data-ttu-id="a53f4-115">W sekcji **Proces** zaznacz pole wyboru **Pełne blokowanie**, jeśli w przypadku niezaliczonych testów ma być zablokowana cała ilość w wierszu zamówienia lub partii.</span><span class="sxs-lookup"><span data-stu-id="a53f4-115">In the **Process** section, select the **Full blocking** check box if the whole lot or order line quantity should be blocked if a test is failed.</span></span> <span data-ttu-id="a53f4-116">Jeśli to pole wyboru nie jest zaznaczone, w przypadku niezaliczonych testów tylko towary w zleceniu kontroli jakości zostaną zablokowane.</span><span class="sxs-lookup"><span data-stu-id="a53f4-116">If this check box is cleared, only the items in the quality order will be blocked if a test is failed.</span></span>
1. <span data-ttu-id="a53f4-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a53f4-117">Select **Save**.</span></span>
1. <span data-ttu-id="a53f4-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a53f4-118">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="a53f4-119">Funkcja *Zarządzania jakością dla procesów magazynowych* dodaje nowe możliwości wyrywkowej kontroli towaru.</span><span class="sxs-lookup"><span data-stu-id="a53f4-119">The *Quality management for warehouse processes* feature provides additional item sampling capabilities.</span></span> <span data-ttu-id="a53f4-120">Dodaje pojęcie *Zakres kontroli wyrywkowej towarów* i umożliwia zdefiniowanie pełnego numeru identyfikacyjnego jako specyfikacji ilości.</span><span class="sxs-lookup"><span data-stu-id="a53f4-120">It adds the concept of *item sampling scope* and lets you define a full license plate as the quantity specification.</span></span> <span data-ttu-id="a53f4-121">Jeśli ta funkcja została włączona, zobacz temat [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="a53f4-121">If you've turned on this feature, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
