---
title: Pola wagi w wierszach ładunku nie pasują do pól wagi w ładunku
description: Pola wagi w wierszach ładunku nie pasują do pól wagi w ładunku
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924358"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a><span data-ttu-id="1eca4-103">Pola wagi w wierszach ładunku nie pasują do pól wagi w ładunku</span><span class="sxs-lookup"><span data-stu-id="1eca4-103">The weight fields on load lines don't match the weight fields on the load</span></span>

<span data-ttu-id="1eca4-104">Kody błędu: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span><span class="sxs-lookup"><span data-stu-id="1eca4-104">Error codes: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span></span>

## <a name="symptoms"></a><span data-ttu-id="1eca4-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="1eca4-105">Symptoms</span></span>

<span data-ttu-id="1eca4-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="1eca4-106">The system shows the following error message:</span></span>

> <span data-ttu-id="1eca4-107">Pola wagi w wierszach ładunku nie pasują do pól wagi w ładunku %1.</span><span class="sxs-lookup"><span data-stu-id="1eca4-107">The weight fields on load lines do not match the weight fields on load %1.</span></span> <span data-ttu-id="1eca4-108">Uruchom proces Sprawdzenie spójności wagi ładunku magazynu w celu ponownego przeliczenia pól wagi.</span><span class="sxs-lookup"><span data-stu-id="1eca4-108">Run the Warehouse load weight consistency check to recalculate the weight fields.</span></span>

## <a name="cause"></a><span data-ttu-id="1eca4-109">Powód</span><span class="sxs-lookup"><span data-stu-id="1eca4-109">Cause</span></span>

<span data-ttu-id="1eca4-110">Pola **Waga netto** i **Tara** w wierszu ładunku mają wartość *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="1eca4-110">The **Net weight** and **Tara weight** fields are set to *0* (zero) on the load line.</span></span> <span data-ttu-id="1eca4-111">Jednak w polach wagi nie są ustawiane wartości *0* jako miary wagi produktu.</span><span class="sxs-lookup"><span data-stu-id="1eca4-111">However, the weight fields aren't set to *0* for the weight measurements on the product.</span></span> <span data-ttu-id="1eca4-112">Jeśli pola wagi nie są ustawione w wierszu ładunku, korekty ilości w wierszu ładunku mogą powodować niepoprawne obliczenie wagi w ładunku.</span><span class="sxs-lookup"><span data-stu-id="1eca4-112">When weight fields aren't set on the load line, any corrections of the quantity on the load line might cause incorrect weight calculation on the load.</span></span> <span data-ttu-id="1eca4-113">Ten problem może wystąpić, jeśli wagi produktu zostały zmienione od czasu utworzenia wiersza ładunku.</span><span class="sxs-lookup"><span data-stu-id="1eca4-113">This issue might occur if the weights on the product have been changed since the load line was created.</span></span>

## <a name="resolution"></a><span data-ttu-id="1eca4-114">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="1eca4-114">Resolution</span></span>

<span data-ttu-id="1eca4-115">Domyślnie podczas tworzenia wiersza ładunku są w nim wstawiane pola wagi z produktu.</span><span class="sxs-lookup"><span data-stu-id="1eca4-115">By default, when a load line is created, the weight fields from the product are entered on it.</span></span> <span data-ttu-id="1eca4-116">Jeśli waga wynosi zero, można ją ponownie przeliczyć za pomocą funkcji *Sprawdzenia spójności wagi ładunku magazynu*.</span><span class="sxs-lookup"><span data-stu-id="1eca4-116">If the weight is zero, you can recalculate it by using the *Warehouse load weight consistency check* functionality.</span></span>

1. <span data-ttu-id="1eca4-117">Przejdź do okna **Administracja systemu \> Okresowe zadania \> Baza danych \> Sprawdzania spójności**.</span><span class="sxs-lookup"><span data-stu-id="1eca4-117">Go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="1eca4-118">W oknie dialogowym **Sprawdzanie spójności** ustaw pole **Moduł** na *Zarządzanie magazynem*.</span><span class="sxs-lookup"><span data-stu-id="1eca4-118">In the **Consistency check** dialog box, set the **Module** field to *Warehouse management*.</span></span>
1. <span data-ttu-id="1eca4-119">Ustaw pole **Sprawdź/napraw** na *Naprawić błąd*.</span><span class="sxs-lookup"><span data-stu-id="1eca4-119">Set the **Check/Fix** field to *Fix error*.</span></span>
1. <span data-ttu-id="1eca4-120">Na liście pól wyboru zaznacz pole wyboru **Sprawdzenie spójności wagi ładunku magazynu** i upewnij się, że podświetlony zostanie tylko wiersz tego pola wyboru.</span><span class="sxs-lookup"><span data-stu-id="1eca4-120">In the checkbox list, select the **Warehouse load weight consistency check** checkbox, and make sure that only the row for this checkbox is highlighted.</span></span>
1. <span data-ttu-id="1eca4-121">Na początku listy pól wyboru naciśnij przycisk wielokropka (**...**), a następnie wybierz opcję **Okno dialogowe** w menu.</span><span class="sxs-lookup"><span data-stu-id="1eca4-121">At the top of the checkbox list, select the ellipsis button (**...**), and then select **Dialog** on the menu.</span></span>
1. <span data-ttu-id="1eca4-122">W oknie dialogowym **Sprawdzenie spójności wagi ładunku magazynu** skonfiguruj następujące pola, aby określić kryteria, dla których ma być uruchamiane sprawdzanie spójności:</span><span class="sxs-lookup"><span data-stu-id="1eca4-122">In the **Warehouse load weight consistency check** dialog box, set the following fields to specify the criteria that the consistency check should run for:</span></span>

    - <span data-ttu-id="1eca4-123">**Identyfikator ładunku:** określ identyfikator ładunku.</span><span class="sxs-lookup"><span data-stu-id="1eca4-123">**Load ID:** Specify a load ID.</span></span> <span data-ttu-id="1eca4-124">Aby sprawdzać wszystkie identyfikatory ładunku, należy pozostawić to pole puste.</span><span class="sxs-lookup"><span data-stu-id="1eca4-124">Leave this blank to check all load IDs.</span></span>
    - <span data-ttu-id="1eca4-125">**Numer towaru:** umożliwia określenie numeru towaru.</span><span class="sxs-lookup"><span data-stu-id="1eca4-125">**Item number:** Specify an item number.</span></span> <span data-ttu-id="1eca4-126">Aby sprawdzać wszystkie towary, należy pozostawić to pole puste.</span><span class="sxs-lookup"><span data-stu-id="1eca4-126">Leave this blank to check all items.</span></span>
    - <span data-ttu-id="1eca4-127">**Zawsze ponownie oblicz wagę ładunków:** ustaw tę opcję na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="1eca4-127">**Always recalculate weight on loads:** Set this option to *Yes*.</span></span>
    - <span data-ttu-id="1eca4-128">**Zezwalaj na zastępowanie wagi w wierszach ładunku:** ustaw tę opcję na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="1eca4-128">**Allow overwrite of weight on load lines:** Set this option to *Yes*.</span></span>

1. <span data-ttu-id="1eca4-129">Naciśnij przycisk **OK**, aby zamknąć okno dialogowe **Sprawdzenie spójności wagi ładunku magazynu**.</span><span class="sxs-lookup"><span data-stu-id="1eca4-129">Select **OK** to close the **Warehouse load weight consistency check** dialog box.</span></span>
1. <span data-ttu-id="1eca4-130">Naciśnij przycisk wielokropka, a następnie wybierz polecenie **Wykonaj** w menu.</span><span class="sxs-lookup"><span data-stu-id="1eca4-130">Select the ellipsis button, and then select **Execute** on the menu.</span></span>

<span data-ttu-id="1eca4-131">Waga zostanie przeliczona na podstawie podanych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="1eca4-131">The weight is recalculated based on the criteria that you specified.</span></span> <span data-ttu-id="1eca4-132">Wybierz łącze **Szczegóły komunikatu**, aby wyświetlić wynik sprawdzania spójności.</span><span class="sxs-lookup"><span data-stu-id="1eca4-132">Select the **Message details** link to view the result of the consistency check.</span></span>
