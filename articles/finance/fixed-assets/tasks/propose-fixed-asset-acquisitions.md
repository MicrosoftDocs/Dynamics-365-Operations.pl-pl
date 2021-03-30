---
title: Proponowanie nabycia środka trwałego
description: W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 426a5e42c1fc26958ab37eddd915334f8b0e19cc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205035"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="8af23-103">Proponowanie nabycia środka trwałego</span><span class="sxs-lookup"><span data-stu-id="8af23-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8af23-104">W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="8af23-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="8af23-105">Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="8af23-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="8af23-106">Aby nabyć środek trwały za pośrednictwem arkusza propozycji środków trwałych, należy najpierw utworzyć rekord środka trwałego, a następnie zdefiniować cenę nabycia w księdze składników majątku.</span><span class="sxs-lookup"><span data-stu-id="8af23-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

1. <span data-ttu-id="8af23-107">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="8af23-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="8af23-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="8af23-108">Select **New**.</span></span>
3. <span data-ttu-id="8af23-109">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8af23-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="8af23-110">W okienku akcji wybierz **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="8af23-110">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="8af23-111">Wybierz **Propozycje**.</span><span class="sxs-lookup"><span data-stu-id="8af23-111">Select **Proposals**.</span></span>
6. <span data-ttu-id="8af23-112">Wybierz **Propozycja nabycia**.</span><span class="sxs-lookup"><span data-stu-id="8af23-112">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="8af23-113">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="8af23-113">Select **Filter**.</span></span> <span data-ttu-id="8af23-114">Wybierz **Resetuj**, aby wyczyścić poprzednie wartości.</span><span class="sxs-lookup"><span data-stu-id="8af23-114">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="8af23-115">Zaznacz wiersz **Numer środka trwałego**.</span><span class="sxs-lookup"><span data-stu-id="8af23-115">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="8af23-116">W polu **Kryteria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8af23-116">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="8af23-117">Skonfiguruj pozostałe kryteria środków trwałych, które chcesz nabyć za pomocą tej propozycji.</span><span class="sxs-lookup"><span data-stu-id="8af23-117">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="8af23-118">Wybierz dwa razy **OK**, aby wyjść z okienka.</span><span class="sxs-lookup"><span data-stu-id="8af23-118">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="8af23-119">Sprawdź utworzone wiersze transakcji.</span><span class="sxs-lookup"><span data-stu-id="8af23-119">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="8af23-120">W propozycji nabycia zostaną uwzględnione tylko środki trwałe, które w księdze mają ustawioną datę nabycia i cenę nabycia.</span><span class="sxs-lookup"><span data-stu-id="8af23-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="8af23-121">Na stronie wybierz kartę **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="8af23-121">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="8af23-122">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="8af23-122">Select **Post**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]