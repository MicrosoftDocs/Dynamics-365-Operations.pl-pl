---
title: Dodawanie błędu do zlecenia pracy
description: W tym temacie opisano sposób dodawania rejestracji błędów do zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e82026f1d73e7368d93109bc0b895b7368ac84d4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435252"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="53ba0-103">Dodawanie błędu do zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="53ba0-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="53ba0-104">Do zlecenia pracy można dodawać usterki, które zostały skonfigurowane w projektancie usterek.</span><span class="sxs-lookup"><span data-stu-id="53ba0-104">You can add faults that were set up in the fault designer to a work order.</span></span> <span data-ttu-id="53ba0-105">Co najmniej jeden rekord usterki musi być połączony z typami składników majątku, które są używane dla składnika majątku wybranego w tym zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="53ba0-105">One or more fault records must be connected to the asset types that are used for the asset that is selected in the work order.</span></span> <span data-ttu-id="53ba0-106">Aby uzyskać więcej informacji o konfiguracji, zobacz temat [Zarządzanie usterkami](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="53ba0-106">For more information about the setup, see [Fault management](../setup-for-work-orders/fault-management.md).</span></span>

1. <span data-ttu-id="53ba0-107">Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-107">Select **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="53ba0-108">Wybierz zlecenie pracy, w którym chcesz przeprowadzić rejestrację usterek, a następnie w okienku akcji, na karcie **Zlecenie pracy**, w grupie **Składnik majątku** wybierz pozycję **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-108">Select the work order to make a fault registration on, and then, on the Action Pane, on the **Work order** tab, in the **Asset** group, select **Asset fault**.</span></span>

3. <span data-ttu-id="53ba0-109">Na skróconej karcie **Objawy** wybierz pozycję **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-109">On the **Symptoms** FastTab, select **Add line**.</span></span> <span data-ttu-id="53ba0-110">Sekwencyjny numer usterki jest automatycznie wprowadzany w polu **Usterka**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-110">A sequential fault number is automatically entered in the **Fault** field.</span></span>

4. <span data-ttu-id="53ba0-111">W polu **Objaw usterki** wybierz odpowiedni objaw.</span><span class="sxs-lookup"><span data-stu-id="53ba0-111">In the **Fault symptom** field, select the relevant symptom.</span></span>

5. <span data-ttu-id="53ba0-112">W polach **Obszar usterki** i **Typ usterki** wybierz odpowiednie wartości.</span><span class="sxs-lookup"><span data-stu-id="53ba0-112">In the **Fault area** and **Fault type** fields, select the appropriate values.</span></span>

6. <span data-ttu-id="53ba0-113">W polu **Data usterki** zostanie automatycznie ustawiona bieżąca data.</span><span class="sxs-lookup"><span data-stu-id="53ba0-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="53ba0-114">W razie potrzeby możesz wybrać inną datę.</span><span class="sxs-lookup"><span data-stu-id="53ba0-114">You can select a different date as you require.</span></span>

7. <span data-ttu-id="53ba0-115">Na skróconej karcie **Przyczyny dla wybranego objawu** dodaj wiersz w celu opisania przyczyny problemu.</span><span class="sxs-lookup"><span data-stu-id="53ba0-115">On the **Causes for selected symptom** FastTab, add a line to describe the cause of the issue.</span></span>

8. <span data-ttu-id="53ba0-116">Na skróconej karcie **Środki zaradcze dla wybranego objawu** dodaj wiersz, aby opisać możliwe rozwiązanie problemu.</span><span class="sxs-lookup"><span data-stu-id="53ba0-116">On the **Remedies for selected symptom** FastTab, add a line to describe a possible solution to the issue.</span></span>

9. <span data-ttu-id="53ba0-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-117">Select **Save**.</span></span>

<span data-ttu-id="53ba0-118">Na poniższej ilustracji pokazano przykład rejestracji usterki.</span><span class="sxs-lookup"><span data-stu-id="53ba0-118">The illustration below shows an example of a fault registration.</span></span>

![Rysunek 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="53ba0-120">Zobacz usterki składnika majątku</span><span class="sxs-lookup"><span data-stu-id="53ba0-120">View asset faults</span></span>

<span data-ttu-id="53ba0-121">Na liście **Usterki składnika majątku** można uzyskać przegląd wszystkich usterek zarejestrowanych w składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="53ba0-121">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="53ba0-122">Na stronie listy **Usterki składnika majątku** można uzyskać przegląd wszystkich usterek, które zarejestrowano w składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="53ba0-122">On the **Asset faults** list page, you can get an overview of all faults that have been registered on assets.</span></span> <span data-ttu-id="53ba0-123">Aby otworzyć stronę, wybierz pozycję **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Usterki składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-123">To open the page, select **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="53ba0-124">Drukowanie raportu usterki składnika majątku</span><span class="sxs-lookup"><span data-stu-id="53ba0-124">Print asset fault report</span></span>

<span data-ttu-id="53ba0-125">Na stronie z listą **Wszystkie składniki majątku** można wydrukować raport usterek składników majątku, który przedstawia wszystkie rejestracje usterek oraz graficzne omówienie statystyk dotyczących usterek.</span><span class="sxs-lookup"><span data-stu-id="53ba0-125">From the **All assets** list page, you can print an asset fault report that shows all fault registrations and a graphical overview of fault statistics.</span></span>

1. <span data-ttu-id="53ba0-126">Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-126">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="53ba0-127">Wybierz składnik majątku, dla którego ma zostać wydrukowany raport usterek.</span><span class="sxs-lookup"><span data-stu-id="53ba0-127">Select the asset to print a fault report for.</span></span>

3. <span data-ttu-id="53ba0-128">W okienku akcji na karcie **Ogólne** w grupie **Raporty** wybierz pozycję **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-128">On the Action Pane, on the **General** tab, in the **Reports** group, select **Asset fault**.</span></span>

4. <span data-ttu-id="53ba0-129">Wprowadź konkretny okres lub wybierz typ usterki.</span><span class="sxs-lookup"><span data-stu-id="53ba0-129">Enter a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="53ba0-130">Wybierz przycisk **OK**, aby wydrukować raport.</span><span class="sxs-lookup"><span data-stu-id="53ba0-130">Select **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="53ba0-131">Aby wydrukować raport usterek dla kilku składników majątku lub typów składników majątku, kliknij pozycję **Zarządzanie składnikami majątku** > **Raporty** > **Składniki majątku** > **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="53ba0-131">To print a fault report for several assets or asset types, select **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

