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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 489add5befe3660ad49e238b659bc8adbe1418a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263765"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="84312-103">Dodawanie błędu do zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="84312-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="84312-104">Do zlecenia pracy można dodawać usterki, które zostały skonfigurowane w projektancie usterek.</span><span class="sxs-lookup"><span data-stu-id="84312-104">You can add faults that were set up in the fault designer to a work order.</span></span> <span data-ttu-id="84312-105">Co najmniej jeden rekord usterki musi być połączony z typami składników majątku, które są używane dla składnika majątku wybranego w tym zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="84312-105">One or more fault records must be connected to the asset types that are used for the asset that is selected in the work order.</span></span> <span data-ttu-id="84312-106">Aby uzyskać więcej informacji o konfiguracji, zobacz temat [Zarządzanie usterkami](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="84312-106">For more information about the setup, see [Fault management](../setup-for-work-orders/fault-management.md).</span></span>

1. <span data-ttu-id="84312-107">Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="84312-107">Select **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="84312-108">Wybierz zlecenie pracy, w którym chcesz przeprowadzić rejestrację usterek, a następnie w okienku akcji, na karcie **Zlecenie pracy**, w grupie **Składnik majątku** wybierz pozycję **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="84312-108">Select the work order to make a fault registration on, and then, on the Action Pane, on the **Work order** tab, in the **Asset** group, select **Asset fault**.</span></span>

3. <span data-ttu-id="84312-109">Na skróconej karcie **Objawy** wybierz pozycję **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="84312-109">On the **Symptoms** FastTab, select **Add line**.</span></span> <span data-ttu-id="84312-110">Sekwencyjny numer usterki jest automatycznie wprowadzany w polu **Usterka**.</span><span class="sxs-lookup"><span data-stu-id="84312-110">A sequential fault number is automatically entered in the **Fault** field.</span></span>

4. <span data-ttu-id="84312-111">W polu **Objaw usterki** wybierz odpowiedni objaw.</span><span class="sxs-lookup"><span data-stu-id="84312-111">In the **Fault symptom** field, select the relevant symptom.</span></span>

5. <span data-ttu-id="84312-112">W polach **Obszar usterki** i **Typ usterki** wybierz odpowiednie wartości.</span><span class="sxs-lookup"><span data-stu-id="84312-112">In the **Fault area** and **Fault type** fields, select the appropriate values.</span></span>

6. <span data-ttu-id="84312-113">W polu **Data usterki** zostanie automatycznie ustawiona bieżąca data.</span><span class="sxs-lookup"><span data-stu-id="84312-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="84312-114">W razie potrzeby możesz wybrać inną datę.</span><span class="sxs-lookup"><span data-stu-id="84312-114">You can select a different date as you require.</span></span>

7. <span data-ttu-id="84312-115">Na skróconej karcie **Przyczyny dla wybranego objawu** dodaj wiersz w celu opisania przyczyny problemu.</span><span class="sxs-lookup"><span data-stu-id="84312-115">On the **Causes for selected symptom** FastTab, add a line to describe the cause of the issue.</span></span>

8. <span data-ttu-id="84312-116">Na skróconej karcie **Środki zaradcze dla wybranego objawu** dodaj wiersz, aby opisać możliwe rozwiązanie problemu.</span><span class="sxs-lookup"><span data-stu-id="84312-116">On the **Remedies for selected symptom** FastTab, add a line to describe a possible solution to the issue.</span></span>

9. <span data-ttu-id="84312-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="84312-117">Select **Save**.</span></span>

<span data-ttu-id="84312-118">Na poniższej ilustracji pokazano przykład rejestracji usterki.</span><span class="sxs-lookup"><span data-stu-id="84312-118">The illustration below shows an example of a fault registration.</span></span>

![Rysunek 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="84312-120">Zobacz usterki składnika majątku</span><span class="sxs-lookup"><span data-stu-id="84312-120">View asset faults</span></span>

<span data-ttu-id="84312-121">Na liście **Usterki składnika majątku** można uzyskać przegląd wszystkich usterek zarejestrowanych w składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="84312-121">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="84312-122">Na stronie listy **Usterki składnika majątku** można uzyskać przegląd wszystkich usterek, które zarejestrowano w składnikach majątku.</span><span class="sxs-lookup"><span data-stu-id="84312-122">On the **Asset faults** list page, you can get an overview of all faults that have been registered on assets.</span></span> <span data-ttu-id="84312-123">Aby otworzyć stronę, wybierz pozycję **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Usterki składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="84312-123">To open the page, select **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="84312-124">Drukowanie raportu usterki składnika majątku</span><span class="sxs-lookup"><span data-stu-id="84312-124">Print asset fault report</span></span>

<span data-ttu-id="84312-125">Na stronie z listą **Wszystkie składniki majątku** można wydrukować raport usterek składników majątku, który przedstawia wszystkie rejestracje usterek oraz graficzne omówienie statystyk dotyczących usterek.</span><span class="sxs-lookup"><span data-stu-id="84312-125">From the **All assets** list page, you can print an asset fault report that shows all fault registrations and a graphical overview of fault statistics.</span></span>

1. <span data-ttu-id="84312-126">Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="84312-126">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="84312-127">Wybierz składnik majątku, dla którego ma zostać wydrukowany raport usterek.</span><span class="sxs-lookup"><span data-stu-id="84312-127">Select the asset to print a fault report for.</span></span>

3. <span data-ttu-id="84312-128">W okienku akcji na karcie **Ogólne** w grupie **Raporty** wybierz pozycję **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="84312-128">On the Action Pane, on the **General** tab, in the **Reports** group, select **Asset fault**.</span></span>

4. <span data-ttu-id="84312-129">Wprowadź konkretny okres lub wybierz typ usterki.</span><span class="sxs-lookup"><span data-stu-id="84312-129">Enter a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="84312-130">Wybierz przycisk **OK**, aby wydrukować raport.</span><span class="sxs-lookup"><span data-stu-id="84312-130">Select **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="84312-131">Aby wydrukować raport usterek dla kilku składników majątku lub typów składników majątku, kliknij pozycję **Zarządzanie składnikami majątku** > **Raporty** > **Składniki majątku** > **Usterka składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="84312-131">To print a fault report for several assets or asset types, select **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]