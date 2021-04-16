---
title: Proponowanie nabycia środka trwałego
description: W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d529cd53b41827a78b282afd4d2c69d2f2db555e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817179"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="dc2fb-103">Proponowanie nabycia środka trwałego</span><span class="sxs-lookup"><span data-stu-id="dc2fb-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dc2fb-104">W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="dc2fb-105">Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="dc2fb-106">Aby nabyć środek trwały za pośrednictwem arkusza propozycji środków trwałych, należy najpierw utworzyć rekord środka trwałego, a następnie zdefiniować cenę nabycia w księdze składników majątku.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

## <a name="create-an-asset-acquisition-proposal"></a><span data-ttu-id="dc2fb-107">Tworzenie propozycji nabycia składnika majątku</span><span class="sxs-lookup"><span data-stu-id="dc2fb-107">Create an asset acquisition proposal</span></span>

<span data-ttu-id="dc2fb-108">Aby utworzyć propozycję nabycia składnika majątku, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-108">Complete the following steps to create an asset acquisition proposal.</span></span> 

1. <span data-ttu-id="dc2fb-109">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-109">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="dc2fb-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-110">Select **New**.</span></span>
3. <span data-ttu-id="dc2fb-111">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="dc2fb-112">W okienku akcji wybierz **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-112">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="dc2fb-113">Wybierz **Propozycje**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-113">Select **Proposals**.</span></span>
6. <span data-ttu-id="dc2fb-114">Wybierz **Propozycja nabycia**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-114">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="dc2fb-115">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-115">Select **Filter**.</span></span> <span data-ttu-id="dc2fb-116">Wybierz **Resetuj**, aby wyczyścić poprzednie wartości.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-116">Select **Reset** to clear previous values.</span></span>
8. <span data-ttu-id="dc2fb-117">Zaznacz wiersz **Numer środka trwałego**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-117">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="dc2fb-118">W polu **Kryteria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-118">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="dc2fb-119">Skonfiguruj pozostałe kryteria środków trwałych, które chcesz nabyć za pomocą tej propozycji.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-119">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="dc2fb-120">Wybierz dwa razy **OK**, aby wyjść z okienka.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-120">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="dc2fb-121">Sprawdź, czy są utworzone wiersze transakcji.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-121">Verify that the transaction lines are created.</span></span>  
- <span data-ttu-id="dc2fb-122">W propozycji nabycia zostaną uwzględnione tylko środki trwałe, które w księdze mają ustawioną datę nabycia i cenę nabycia.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-122">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="dc2fb-123">Na stronie wybierz kartę **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-123">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="dc2fb-124">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-124">Select **Post**.</span></span>

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a><span data-ttu-id="dc2fb-125">Uwzględnij domyślne wymiary finansowe w propozycji nabycia</span><span class="sxs-lookup"><span data-stu-id="dc2fb-125">Include default financial dimensions in an acquisition proposal</span></span>

<span data-ttu-id="dc2fb-126">Transakcję nabycia można utworzyć za pomocą dodatków programu Excel, przechodząc do pozycji **Składniki majątku > Wpisy w arkuszu > Arkusz składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-126">The acquisition transaction can be created using Excel add-ins, by going to **Fixed assets > Journal entries > Fixed asset journal**.</span></span> <span data-ttu-id="dc2fb-127">Utwórz nowy arkusz i przenieś do sekcji **Wiersze** na stronie, wybierz ikonę programu Excel, a następnie wybierz wiersz arkusza składników majątku.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-127">Create a new journal and move to the **Lines** section on the page and select the Excel icon, and then select a Fixed asset journal line.</span></span> <span data-ttu-id="dc2fb-128">System utworzy i otworzy szablon programu Excel reprezentujący wiersze arkusza.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-128">The system will create and open an Excel template representing journal lines.</span></span> <span data-ttu-id="dc2fb-129">Można dodać dane do wierszy arkusza, które dodajesz do szablonu, a następnie opublikować je z powrotem w systemie.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-129">You can add data for the journal lines you're adding into the template, and then publish that information back into the system.</span></span> 

<span data-ttu-id="dc2fb-130">Jeśli dla wybranej księgi składników majątku zostały ustawione wymiary domyślne oraz odpowiednie składniki majątku wprowadzone w szablonie programu Excel, domyślne wymiary finansowe będą wywoływane z danych główne księgi składników majątku, gdy arkusz zostanie opublikowany w programie Excel w systemie.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-130">If default dimensions have been set up for the selected asset book and the corresponding fixed assets that were entered in the Excel template, the default financial dimensions will be called from the asset book master data when the journal is published from the Excel to the system.</span></span> <span data-ttu-id="dc2fb-131">Aby podczas publikowania arkusza składników majątku w dodatku programu Excel automatycznie uwzględniać wymiary finansowe w księdze składników majątku, należy wcześniej skonfigurować wymiary domyślne.</span><span class="sxs-lookup"><span data-stu-id="dc2fb-131">To include financial dimensions on an asset book automatically while publishing the fixed asset journal from the Excel add-in, the default dimensions must be set up in advance.</span></span>  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
