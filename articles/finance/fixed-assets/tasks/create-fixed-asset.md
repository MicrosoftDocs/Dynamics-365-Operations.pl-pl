---
title: Tworzenie środka trwałego
description: W tym temacie opisano sposób tworzenia nowego rekordu środka trwałego na stronie listy środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b7d65a047251fa036242fb456725bc8cba957b9
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000250"
---
# <a name="create-a-fixed-asset"></a><span data-ttu-id="5a099-103">Tworzenie środka trwałego</span><span class="sxs-lookup"><span data-stu-id="5a099-103">Create a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5a099-104">W tym temacie opisano sposób tworzenia nowego rekordu środka trwałego na stronie listy **Środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="5a099-104">This topic explains how to create a new fixed asset record from the **Fixed asset** list page.</span></span>

<span data-ttu-id="5a099-105">System przypisuje numer środka trwałego na podstawie sekwencji numerów przypisanej do grupy środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="5a099-105">The system assigns the asset number, based on the number sequence that is assigned to the fixed asset group.</span></span> <span data-ttu-id="5a099-106">Jeśli do importowania środków trwałych za pomocą dodatku Microsoft Excel używany jest szablon środków trwałych lub zostanie użyte inne zadanie importowania, system automatycznie utworzy rekordy środków trwałych i zwiększy numer środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="5a099-106">If you use the fixed asset template to import assets via the Microsoft Excel add-in, or if you use another import job, the system automatically creates fixed asset records and increments the asset number.</span></span>

<span data-ttu-id="5a099-107">Aby ręcznie utworzyć rekord środka trwałego, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5a099-107">To manually create an asset record, follow these steps.</span></span>

1. <span data-ttu-id="5a099-108">Otwórz **Okienko nawigacji \> Moduły \> Środki trwałe \> Środki trwałe \> Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="5a099-108">Go to **Navigation pane \> Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="5a099-109">W **Okienku akcji** wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5a099-109">On the **Action pane** , select **New**.</span></span>
3. <span data-ttu-id="5a099-110">W polu **Grupa środków trwałych** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5a099-110">In **the Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="5a099-111">Wartość w polu **Numer** będzie ustawiana domyślnie, jeśli włączono **funkcję Automatyczna numeracja środków trwałych** w oknie **Parametry środków trwałych** oraz włączono funkcję **Grupa środków trwałych**.</span><span class="sxs-lookup"><span data-stu-id="5a099-111">The **Number** field will default if you have enabled **Autonumber fixed assets functionality** in the **Fixed assets parameters** and the **Fixed asset group**.</span></span> <span data-ttu-id="5a099-112">Jeśli nie, samodzielnie wprowadź unikatowy numer identyfikujący środek trwały.</span><span class="sxs-lookup"><span data-stu-id="5a099-112">If not, you must enter a unique number to identify the fixed asset.</span></span>
4. <span data-ttu-id="5a099-113">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="5a099-113">In the **Name** field, enter a value.</span></span> <span data-ttu-id="5a099-114">Wprowadź dodatkowe informacje, jakich firma potrzebuje o tym składniku aktywów.</span><span class="sxs-lookup"><span data-stu-id="5a099-114">Enter the additional information that your business needs for this asset.</span></span>
5. <span data-ttu-id="5a099-115">W **Okienku akcji** wybierz pozycję **Księgi**.</span><span class="sxs-lookup"><span data-stu-id="5a099-115">On the **Action pane** , select **Books**.</span></span>
6. <span data-ttu-id="5a099-116">W polu **Data nabycia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="5a099-116">In the **Acquisition date** field, enter a date.</span></span>
7. <span data-ttu-id="5a099-117">W polu **Cena nabycia** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="5a099-117">In the **Acquisition price** field, enter a number.</span></span>

    - <span data-ttu-id="5a099-118">Wprowadź dodatkowe informacje, jakich firma potrzebuje o tej księdze.</span><span class="sxs-lookup"><span data-stu-id="5a099-118">Enter the additional information that your business needs for this book.</span></span>
    - <span data-ttu-id="5a099-119">Wprowadź dodatkowe informacje, jakich firma potrzebuje o pozostałych księgach.</span><span class="sxs-lookup"><span data-stu-id="5a099-119">Enter the additional information that your business needs for the remaining books.</span></span>

8. <span data-ttu-id="5a099-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5a099-120">Close the page.</span></span>

<span data-ttu-id="5a099-121">Środki trwałe można również zaimportować za pomocą dodatku programu Excel lub uruchamiając zadanie importu z obszaru roboczego **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="5a099-121">You can also import fixed assets by using the Excel add-in or by running an import job from the **Data management** workspace.</span></span> <span data-ttu-id="5a099-122">Przed uruchomieniem importu należy wprowadzić wartości wymaganych pól w szablonie.</span><span class="sxs-lookup"><span data-stu-id="5a099-122">Before you run the import, enter the values for required fields in the template.</span></span>

<span data-ttu-id="5a099-123">Jeśli nie zdefiniowano numeru środka trwałego w szablonie dodatku programu Excel lub w module Zarządzanie danymi, system utworzy numer środka trwałego dla każdego importowanego środka trwałego i automatycznie zwiększy sekwencję numerów dla każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="5a099-123">If you didn't define the fixed asset number in the template of the Excel add-in, or in Data management, the system creates a fixed asset number for each imported asset and automatically increments the number sequence for each.</span></span> <span data-ttu-id="5a099-124">Jednak w przypadku importowania środków trwałych i definiowania numerów środków w szablonie system **nie** zwiększa automatycznie sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="5a099-124">However, if you import assets and define asset numbers in the template, the system does **not** automatically increment the number sequence.</span></span> <span data-ttu-id="5a099-125">W takim przypadku administrator może ręcznie zaktualizować sekwencję numerów.</span><span class="sxs-lookup"><span data-stu-id="5a099-125">In this case, an admin might have to manually update the number sequence.</span></span> <span data-ttu-id="5a099-126">Jeśli zdefiniowano numer środka trwałego w szablonie dodatku Excel, system używa zdefiniowanego numeru środka trwałego i zwiększa sekwencję numerów.</span><span class="sxs-lookup"><span data-stu-id="5a099-126">If you defined the fixed asset number in the template of the Excel add-in, the system uses the defined fixed asset number and increments the number sequence.</span></span>
