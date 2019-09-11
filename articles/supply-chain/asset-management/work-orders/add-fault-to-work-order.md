---
title: Dodawanie błędu do zlecenia pracy
description: W tym temacie opisano sposób dodawania rejestracji błędów do zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875845"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="41d89-103">Dodawanie błędu do zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="41d89-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="41d89-104">Do zlecenia pracy można dodawać błędy ustawione w projektancie usterek.</span><span class="sxs-lookup"><span data-stu-id="41d89-104">You can add faults set up in the fault designer to a work order.</span></span> <span data-ttu-id="41d89-105">Składnik majątku wybrany w zleceniu pracy musi zawierać typy składników majątku, z którymi jest połączony jeden lub więcej rekordów usterek.</span><span class="sxs-lookup"><span data-stu-id="41d89-105">The asset selected in the work order must contain asset types that have one or more fault records connected to it.</span></span> <span data-ttu-id="41d89-106">Więcej informacji o ustawieniach można znaleźć w sekcji [Zarządzanie usterkami](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="41d89-106">Read more about setup in the [Fault management](../setup-for-work-orders/fault-management.md) section.</span></span>

1. <span data-ttu-id="41d89-107">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="41d89-107">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="41d89-108">Z listy wybierz zlecenie pracy, dla którego chcesz dokonać rejestracji usterek i kliknij przycisk **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="41d89-108">In the list, select the work order on which you want to make a fault registration and click **Asset fault**.</span></span>

3. <span data-ttu-id="41d89-109">Na skróconej karcie **Objawy**, należy kliknąć przycisk **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="41d89-109">On the **Symptoms** FastTab, click **Add line**.</span></span> <span data-ttu-id="41d89-110">Sekwencyjny numer błędu jest automatycznie wstawiany w polu **Usterka**.</span><span class="sxs-lookup"><span data-stu-id="41d89-110">A sequential fault number is automatically inserted in the **Fault** field.</span></span>

4. <span data-ttu-id="41d89-111">Wybierz odpowiedni objaw w polu **Objaw usterki**.</span><span class="sxs-lookup"><span data-stu-id="41d89-111">Select the relevant symptom in the **Fault symptom** field.</span></span>

5. <span data-ttu-id="41d89-112">Wybierz **Obszar usterki** i **Typ usterki**.</span><span class="sxs-lookup"><span data-stu-id="41d89-112">Select **Fault area** and **Fault type**.</span></span>

6. <span data-ttu-id="41d89-113">W polu **Data usterki** zostanie automatycznie ustawiona bieżąca data.</span><span class="sxs-lookup"><span data-stu-id="41d89-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="41d89-114">W razie potrzeby można wybrać inną datę.</span><span class="sxs-lookup"><span data-stu-id="41d89-114">You can select another date, if necessary.</span></span>

7. <span data-ttu-id="41d89-115">Na skróconej karcie **Przyczyny dla wybranego objawu** dodaj wiersz opisujący przyczynę problemu.</span><span class="sxs-lookup"><span data-stu-id="41d89-115">On the **Causes for selected symptom** FastTab, add a line describing the cause of the problem.</span></span>

8. <span data-ttu-id="41d89-116">Na skróconej karcie **Środki zaradcze dla wybranego objawu** dodaj wiersz opisujący możliwe rozwiązanie problemu.</span><span class="sxs-lookup"><span data-stu-id="41d89-116">On the **Remedies for selected symptom** FastTab, add a line describing a possible solution to the problem.</span></span>

9. <span data-ttu-id="41d89-117">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="41d89-117">Click **Save**.</span></span>

![Rysunek 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="41d89-119">Zobacz usterki składnika majątku</span><span class="sxs-lookup"><span data-stu-id="41d89-119">View asset faults</span></span>

<span data-ttu-id="41d89-120">Na liście **Usterki składnika majątku** można uzyskać przegląd wszystkich usterek zarejestrowanych w składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="41d89-120">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="41d89-121">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Usterki składnika majątku**, aby otworzyć listę.</span><span class="sxs-lookup"><span data-stu-id="41d89-121">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults** to open the list.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="41d89-122">Drukowanie raportu usterki składnika majątku</span><span class="sxs-lookup"><span data-stu-id="41d89-122">Print asset fault report</span></span>

<span data-ttu-id="41d89-123">Na stronie z listą **Wszystkie składniki majątku** można wydrukować raport dotyczący usterek składników majątku zawierający wszystkie rejestracje usterek oraz graficzne omówienie statystyk usterek.</span><span class="sxs-lookup"><span data-stu-id="41d89-123">From the **All assets** list page, you can print an asset fault report displaying all fault registrations as well as a graphic overview of fault statistics.</span></span>

1. <span data-ttu-id="41d89-124">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="41d89-124">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="41d89-125">Na liście **Składniki majątku** wybierz składnik majątku, dla którego chcesz wydrukować raport usterki.</span><span class="sxs-lookup"><span data-stu-id="41d89-125">In the **Assets** list, select the asset for which you want to print a fault report.</span></span>

3. <span data-ttu-id="41d89-126">Na karcie **Ogólne** > **sekcja Raporty**, kliknij **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="41d89-126">On the **General** tab > **Reports section**, click **Asset fault**.</span></span>

4. <span data-ttu-id="41d89-127">Wstaw konkretny okres lub wybierz typ błędu.</span><span class="sxs-lookup"><span data-stu-id="41d89-127">Insert a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="41d89-128">Kliknij przycisk **OK**, aby wydrukować raport.</span><span class="sxs-lookup"><span data-stu-id="41d89-128">Click **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="41d89-129">Można również wydrukować raport o usterkach dla kilku składników majątku lub typów składników majątku klikając **Zarządzanie składnikami majątku** > **Raporty** > **Składniki majątku** > **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="41d89-129">You can also print a fault report for several assets or asset types by clicking **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

