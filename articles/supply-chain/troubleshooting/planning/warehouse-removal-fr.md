---
title: Nie można usunąć wymiaru Prognoza popytu w magazynie z wierszy prognozy
description: Nie można usunąć wymiaru Prognoza popytu w magazynie z wierszy prognozy.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026816"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a><span data-ttu-id="f2bee-103">Nie można usunąć wymiaru Prognoza popytu w magazynie z wierszy prognozy</span><span class="sxs-lookup"><span data-stu-id="f2bee-103">You can't remove the Warehouse demand forecast dimension from forecast lines</span></span>

<span data-ttu-id="f2bee-104">Numer artykułu z bazy wiedzy: 4614408</span><span class="sxs-lookup"><span data-stu-id="f2bee-104">KB number: 4614408</span></span>

## <a name="symptoms"></a><span data-ttu-id="f2bee-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="f2bee-105">Symptoms</span></span>

<span data-ttu-id="f2bee-106">Ten problem występuje, gdy wymiar **magazynowy** nie jest przypisany na karcie **Wymiary prognozy** na stronie **parametrów prognozowania popytu**.</span><span class="sxs-lookup"><span data-stu-id="f2bee-106">This issue occurs when the **Warehouse** dimension isn't assigned on the **Forecast dimensions** tab of the **Demand forecasting parameter** page.</span></span> <span data-ttu-id="f2bee-107">Mimo tego kolumna **Magazyn** jest wyświetlana na stronie **Prognoza popytu** (**Planowanie główne \> Prognozowanie \> Element prognozy ręcznej \> Linie prognozy popytu**).</span><span class="sxs-lookup"><span data-stu-id="f2bee-107">Nevertheless, the **Warehouse** column is shown on the **Demand forecast** page (**Master planning \> Forecasting \> Manual forecast entity \> Demand forecast lines**).</span></span>

## <a name="resolution"></a><span data-ttu-id="f2bee-108">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="f2bee-108">Resolution</span></span>

<span data-ttu-id="f2bee-109">Ustawienia na karcie **Wymiary prognozy** na stronie **Parametr prognozowania popytu** nie wpływają na stronę **Prognoza popytu**.</span><span class="sxs-lookup"><span data-stu-id="f2bee-109">The settings on the **Forecast dimensions** tab of the **Demand forecasting parameter** page don't affect the **Demand forecast** page.</span></span> <span data-ttu-id="f2bee-110">Sterują one prognozą bazową, która jest generowana i wyświetlana w skorygowanej prognozie popytu.</span><span class="sxs-lookup"><span data-stu-id="f2bee-110">They control the baseline forecast that is generated and shown in the adjusted demand forecast.</span></span> <span data-ttu-id="f2bee-111">Nie kontrolują jednak wymiarów wymaganych dla „rzeczywistej” prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="f2bee-111">However, they don't control the dimensions that are required for the "real" demand forecast.</span></span> <span data-ttu-id="f2bee-112">Autoryzując rekordy, które są widoczne na stronie **Skorygowana prognoza popytu**, można je przekonwertować na „rzeczywiste” wpisy prognozy dla modelu prognozy.</span><span class="sxs-lookup"><span data-stu-id="f2bee-112">By authorizing the records that are shown on the **Adjusted demand forecast** page, you can convert them to "real" forecast entries for a forecast model.</span></span> <span data-ttu-id="f2bee-113">Następnie można używać tego modelu do planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="f2bee-113">That model can then be used for master planning.</span></span>

<span data-ttu-id="f2bee-114">Na stronie **Prognoza popytu** wymiary prognozy rzeczywistej wyświetlane w wierszach prognozy popytu są częścią wymiarów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="f2bee-114">On the **Demand forecast** page, the dimensions for the "real" forecast that are shown on the demand forecast lines are part of the inventory dimensions.</span></span> <span data-ttu-id="f2bee-115">(To zachowanie przypomina zachowanie wierszy zamówienia sprzedaży) Jeśli system nie jest ustawiony do używania **magazynu** jako obowiązkowego wymiaru magazynowego, stronę można dostosować w celu ukrycia kolumny.</span><span class="sxs-lookup"><span data-stu-id="f2bee-115">(This behavior resembles the behavior for sales order lines.) If your system isn't set up to use **Warehouse** as a mandatory inventory dimension, you can customize the page to hide the column.</span></span>
