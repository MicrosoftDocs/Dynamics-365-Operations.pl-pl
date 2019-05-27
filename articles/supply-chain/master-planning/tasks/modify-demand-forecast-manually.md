---
title: Ręczne modyfikowanie prognozy popytu
description: W tej procedurze pokazano sposób modyfikowania prognozy dla towaru.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 063554c98b8a6261ebe69073f214a8e45850c623
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560743"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="0acd3-103">Ręczne modyfikowanie prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="0acd3-103">Modify a demand forecast manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0acd3-104">W tej procedurze pokazano sposób modyfikowania prognozy dla towaru.</span><span class="sxs-lookup"><span data-stu-id="0acd3-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="0acd3-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="0acd3-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0acd3-106">To nagranie jest przeznaczone dla planisty produkcji.</span><span class="sxs-lookup"><span data-stu-id="0acd3-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="0acd3-107">Modyfikowanie prognozy na towar</span><span class="sxs-lookup"><span data-stu-id="0acd3-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="0acd3-108">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="0acd3-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="0acd3-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0acd3-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0acd3-110">Wybierz towar, dla którego chcesz zmodyfikować prognozę.</span><span class="sxs-lookup"><span data-stu-id="0acd3-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="0acd3-111">Można na przykład wybrać towar D0001.</span><span class="sxs-lookup"><span data-stu-id="0acd3-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="0acd3-112">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="0acd3-112">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="0acd3-113">Kliknij opcję Prognoza popytu.</span><span class="sxs-lookup"><span data-stu-id="0acd3-113">Click Demand forecast.</span></span>
5. <span data-ttu-id="0acd3-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0acd3-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0acd3-115">Jeśli nie ma żadnych wierszy prognozy, należy utworzyć nowy wiersz przez</span><span class="sxs-lookup"><span data-stu-id="0acd3-115">If there are no forecast lines, create a new line by  .</span></span> <span data-ttu-id="0acd3-116">kliknięcie przycisku Nowy na pasku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0acd3-116">clicking New on the app bar.</span></span>  
6. <span data-ttu-id="0acd3-117">W polu Ilość sprzedaży wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="0acd3-117">In the Sales quantity field, enter a number.</span></span>
    * <span data-ttu-id="0acd3-118">Ta liczba reprezentuje prognozowaną ilość towaru.</span><span class="sxs-lookup"><span data-stu-id="0acd3-118">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="0acd3-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0acd3-119">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="0acd3-120">Modyfikowanie prognozy w programie Excel</span><span class="sxs-lookup"><span data-stu-id="0acd3-120">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="0acd3-121">Kliknij przycisk Otwórz w Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="0acd3-121">Click Open in Microsoft Office.</span></span>
2. <span data-ttu-id="0acd3-122">Kliknij opcję Edytuj prognozę popytu w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="0acd3-122">Click Edit Demand forecast in Excel.</span></span>
    * <span data-ttu-id="0acd3-123">W programie Excel można dodawać, usuwać i edytować wiersze prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="0acd3-123">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="0acd3-124">Jeśli nie widzisz danych w programie Excel, musisz się zalogować do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z włączoną opcją „Nie wylogowuj mnie” i zaufać aplikacji połączenia danych.</span><span class="sxs-lookup"><span data-stu-id="0acd3-124">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  

