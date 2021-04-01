---
title: Ręczne modyfikowanie prognozy popytu
description: W tej procedurze pokazano sposób modyfikowania prognozy dla towaru.
author: ShylaThompson
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 31c057d686edc97a11027f156b9c14ff453294ec
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240396"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="79fdd-103">Ręczne modyfikowanie prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="79fdd-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="79fdd-104">W tej procedurze pokazano sposób modyfikowania prognozy dla towaru.</span><span class="sxs-lookup"><span data-stu-id="79fdd-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="79fdd-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="79fdd-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="79fdd-106">To nagranie jest przeznaczone dla planisty produkcji.</span><span class="sxs-lookup"><span data-stu-id="79fdd-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="79fdd-107">Modyfikowanie prognozy na towar</span><span class="sxs-lookup"><span data-stu-id="79fdd-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="79fdd-108">W **Okienku nawigacji** przejdź do opcji **Moduły > Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="79fdd-108">In the **Navigation pane**, go to **Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="79fdd-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="79fdd-109">In the list, find and select the desired record.</span></span> <span data-ttu-id="79fdd-110">Wybierz towar, dla którego chcesz zmodyfikować prognozę.</span><span class="sxs-lookup"><span data-stu-id="79fdd-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="79fdd-111">Można na przykład wybrać towar D0001.</span><span class="sxs-lookup"><span data-stu-id="79fdd-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="79fdd-112">W **okienku akcji** kliknij pozycję **Plan**.</span><span class="sxs-lookup"><span data-stu-id="79fdd-112">On the **Action Pane**, click **Plan**.</span></span>
4. <span data-ttu-id="79fdd-113">Kliknij opcję **Prognoza popytu**.</span><span class="sxs-lookup"><span data-stu-id="79fdd-113">Click **Demand forecast**.</span></span>
5. <span data-ttu-id="79fdd-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="79fdd-114">In the list, mark the selected row.</span></span> <span data-ttu-id="79fdd-115">Jeśli nie ma żadnych wierszy prognozy, utwórz nowy wiersz przez kliknięcie przycisku Nowy na pasku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="79fdd-115">If there are no forecast lines, create a new line by clicking New on the app bar.</span></span>  
6. <span data-ttu-id="79fdd-116">W polu **Ilość sprzedaży** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="79fdd-116">In the **Sales quantity** field, enter a number.</span></span> <span data-ttu-id="79fdd-117">Ta liczba reprezentuje prognozowaną ilość towaru.</span><span class="sxs-lookup"><span data-stu-id="79fdd-117">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="79fdd-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="79fdd-118">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="79fdd-119">Modyfikowanie prognozy w programie Excel</span><span class="sxs-lookup"><span data-stu-id="79fdd-119">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="79fdd-120">Kliknij przycisk **Otwórz** w Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="79fdd-120">Click **Open** in Microsoft Office.</span></span>
2. <span data-ttu-id="79fdd-121">Kliknij opcję **Edytuj prognozę popytu** w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="79fdd-121">Click **Edit Demand forecast** in Excel.</span></span> <span data-ttu-id="79fdd-122">W programie Excel można dodawać, usuwać i edytować wiersze prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="79fdd-122">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="79fdd-123">Jeśli nie widzisz danych w programie Excel, musisz mieć włączoną opcję „Nie wylogowuj mnie” i zaufać aplikacji połączenia danych.</span><span class="sxs-lookup"><span data-stu-id="79fdd-123">If you are not able to see the data in Excel, you need to sign in with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]