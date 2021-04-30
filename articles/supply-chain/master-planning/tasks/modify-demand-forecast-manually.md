---
title: Ręczne modyfikowanie prognozy popytu
description: W tym temacie opisano, jak zmodyfikować prognozę dla towaru
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889031"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="c0b51-103">Ręczne modyfikowanie prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="c0b51-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c0b51-104">W tej procedurze pokazano sposób modyfikowania prognozy dla towaru.</span><span class="sxs-lookup"><span data-stu-id="c0b51-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="c0b51-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c0b51-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c0b51-106">Ta procedura jest przeznaczona dla planisty produkcji.</span><span class="sxs-lookup"><span data-stu-id="c0b51-106">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="c0b51-107">Modyfikowanie prognozy na wybrany towar</span><span class="sxs-lookup"><span data-stu-id="c0b51-107">Modify the forecast for a selected item</span></span>

<span data-ttu-id="c0b51-108">Aby zmodyfikować prognozę dla wybranego elementu:</span><span class="sxs-lookup"><span data-stu-id="c0b51-108">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="c0b51-109">Przejdź do **Moduły \> Zarządzanie informacjami o produkcie \> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="c0b51-109">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="c0b51-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c0b51-110">In the list, find and select the desired record.</span></span> <span data-ttu-id="c0b51-111">Wybierz towar, dla którego chcesz zmodyfikować prognozę.</span><span class="sxs-lookup"><span data-stu-id="c0b51-111">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="c0b51-112">W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Prognoza popytu**.</span><span class="sxs-lookup"><span data-stu-id="c0b51-112">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="c0b51-113">Na liście zaznacz wiersz.</span><span class="sxs-lookup"><span data-stu-id="c0b51-113">In the list, select a row.</span></span> <span data-ttu-id="c0b51-114">Jeśli nie ma żadnych wierszy prognozy, utwórz nowy wiersz przez wybranie przycisku **Nowy** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="c0b51-114">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="c0b51-115">W polu **Ilość sprzedaży** wprowadź liczbę dodatnią.</span><span class="sxs-lookup"><span data-stu-id="c0b51-115">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="c0b51-116">Ta liczba reprezentuje prognozowaną ilość towaru.</span><span class="sxs-lookup"><span data-stu-id="c0b51-116">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="c0b51-117">W przypadku wprowadzenia liczby ujemnej wyświetlany jest błąd.</span><span class="sxs-lookup"><span data-stu-id="c0b51-117">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="c0b51-118">W razie potrzeby wypełnij pola.</span><span class="sxs-lookup"><span data-stu-id="c0b51-118">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="c0b51-119">W okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c0b51-119">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a><span data-ttu-id="c0b51-120">Modyfikowanie prognozy dla jednego lub większej liczby towarów Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="c0b51-120">Modify the forecast for one or more items Microsoft Excel</span></span>

<span data-ttu-id="c0b51-121">Aby zmodyfikować prognozę dla jednego lub więcej towarów Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="c0b51-121">To modify the forecast for one or more items Microsoft Excel:</span></span>

1. <span data-ttu-id="c0b51-122">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="c0b51-122">Do one of the following:</span></span>
    - <span data-ttu-id="c0b51-123">Otwórz stronę **Prognozy popytu** dla dowolnej pozycji (niezależnie od tego, która z nich) została opisana w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="c0b51-123">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="c0b51-124">Wybierz kolejno opcje **Planowanie główne \> Prognozowanie \> Ręczne wprowadzanie prognozy \> Wiersze prognozy popytu**.</span><span class="sxs-lookup"><span data-stu-id="c0b51-124">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="c0b51-125">W okienku akcji wybierz **Otwórz w Microsoft Office \> Wpisy prognozy popytu**.</span><span class="sxs-lookup"><span data-stu-id="c0b51-125">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="c0b51-126">Wybierz lokalizację pobierania, zapisz, a następnie otwórz pobrany plik w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="c0b51-126">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="c0b51-127">Jeśli zostanie wyświetlane ostrzeżenie, wybierz opcję **Włącz edytowanie**.</span><span class="sxs-lookup"><span data-stu-id="c0b51-127">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="c0b51-128">W programie Excel zaloguj się do Supply Chain Management przy użyciu okienka zadań Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="c0b51-128">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="c0b51-129">Musisz się zalogować, gdy włączona jest opcja **Nie wylogowuj mnie** i musisz ufać aplikacji do połączeń z danymi.</span><span class="sxs-lookup"><span data-stu-id="c0b51-129">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="c0b51-130">W arkuszu programu Excel są teraz wszystkie wiersze bieżącej prognozy popytu dla firmy.</span><span class="sxs-lookup"><span data-stu-id="c0b51-130">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="c0b51-131">W razie potrzeby dodawaj, usuwaj i edytuj wiersze prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="c0b51-131">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="c0b51-132">Wybierz opcję **Publikuj** w okienku zadań Microsoft Dynamics, aby przekazać zmiany z powrotem do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c0b51-132">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
