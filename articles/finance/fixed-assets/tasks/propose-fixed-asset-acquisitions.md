---
title: Proponowanie nabycia środka trwałego
description: W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e08177aad2db2438c2d5d4ddd294c1056b88167c
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142738"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="ba8b5-103">Proponowanie nabycia środka trwałego</span><span class="sxs-lookup"><span data-stu-id="ba8b5-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba8b5-104">W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="ba8b5-105">Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="ba8b5-106">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-106">In the Navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="ba8b5-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-107">Select **New**.</span></span>
3. <span data-ttu-id="ba8b5-108">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-108">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="ba8b5-109">W okienku akcji wybierz **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-109">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="ba8b5-110">Wybierz **Propozycje**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-110">Select **Proposals**.</span></span>
6. <span data-ttu-id="ba8b5-111">Wybierz **Propozycja nabycia**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-111">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="ba8b5-112">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-112">Select **Filter**.</span></span> <span data-ttu-id="ba8b5-113">Wybierz **Resetuj**, aby wyczyścić poprzednie wartości.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-113">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="ba8b5-114">Zaznacz wiersz **Numer środka trwałego**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-114">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="ba8b5-115">W polu **Kryteria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="ba8b5-116">Skonfiguruj pozostałe kryteria środków trwałych, które chcesz nabyć za pomocą tej propozycji.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="ba8b5-117">Wybierz dwa razy **OK**, aby wyjść z okienka.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-117">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="ba8b5-118">Sprawdź utworzone wiersze transakcji.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-118">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="ba8b5-119">W propozycji nabycia zostaną uwzględnione tylko środki trwałe, które w księdze mają ustawioną datę nabycia i cenę nabycia.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-119">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="ba8b5-120">Na stronie wybierz kartę **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-120">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="ba8b5-121">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="ba8b5-121">Select **Post**.</span></span>

