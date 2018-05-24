---
title: "Ręczne tworzenie zleceń serwisowych"
description: "Zlecenia serwisowe można tworzyć ręcznie na podstawie umowy serwisowej lub za pomocą formularza **Zlecenia serwisowe**."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a0cc6b2646929776f4efb20474de6b0fc5c4719c
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-orders-manually"></a><span data-ttu-id="90be2-103">Ręczne tworzenie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="90be2-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="90be2-104">Zlecenia serwisowe można tworzyć ręcznie na podstawie umowy serwisowej lub za pomocą formularza **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="90be2-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="90be2-105">Można również utworzyć zlecenie serwisowe na podstawie projektu.</span><span class="sxs-lookup"><span data-stu-id="90be2-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="90be2-106">Do tworzenia zleceń serwisowych można używać zautomatyzowanych procesów.</span><span class="sxs-lookup"><span data-stu-id="90be2-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="90be2-107">Tworzenie zlecenia serwisowego ręcznie na podstawie umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="90be2-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="90be2-108">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="90be2-108">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="90be2-109">Wybierz umowę serwisową lub utwórz nową umowę.</span><span class="sxs-lookup"><span data-stu-id="90be2-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="90be2-110">Kliknij kartę **Dostarcz**, a następnie w grupie **Tworzenie** kliknij opcję **Planowane zlecenia serwisowe**, a zostanie otwarty formularz **Utwórz zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="90be2-110">Click the **Deliver** tab and in the **Create** group click **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="90be2-111">Tworzenie zlecenia serwisowego ręcznie w formularzu Zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="90be2-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="90be2-112">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="90be2-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="90be2-113">Naciśnij klawisze Ctrl+N, aby utworzyć nowe zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="90be2-113">Press Ctrl+N to create a new service order.</span></span>

3.  <span data-ttu-id="90be2-114">Utwórz wiersze zlecenia serwisowego dla zlecenia.</span><span class="sxs-lookup"><span data-stu-id="90be2-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="90be2-115">Jeśli pole wyboru <STRONG>Dozwolone bez umowy serwisowej</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG> jest zaznaczone, można księgować transakcje z wierszy zlecenia serwisowego, nie dołączając do zlecenia serwisowego umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="90be2-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="90be2-116">Jeżeli nie zaznaczono tego pola wyboru, przed zaksięgowaniem wierszy zlecenia serwisowego należy dołączyć do projektu zlecenie serwisowe utworzone ręcznie.</span><span class="sxs-lookup"><span data-stu-id="90be2-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="90be2-117">Tworzenie zlecenia serwisowego na podstawie projektu</span><span class="sxs-lookup"><span data-stu-id="90be2-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="90be2-118">Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Wspólne** \> **Projekty** \> **Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="90be2-118">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="90be2-119">W formularzu **Projekty** w **okienku akcji** kliknij kartę **Zarządzaj** \> kliknij kolejno opcje **Serwis** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="90be2-119">In the **Projects** form, on the **Action pane**, click the **Manage** tab \> click **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="90be2-120">Postępuj zgodnie z poprzednią procedurą ręcznego tworzenia zlecenia serwisowego na podstawie formularza **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="90be2-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="90be2-121">W polu **Identyfikator projektu** jest wyświetlane odwołanie do projektu.</span><span class="sxs-lookup"><span data-stu-id="90be2-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="90be2-122">Jeśli pole wyboru <STRONG>Dozwolone bez umowy serwisowej</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG> jest zaznaczone, można księgować transakcje z wierszy zlecenia serwisowego, nie dołączając do zlecenia serwisowego umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="90be2-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="90be2-123">Jeżeli nie zaznaczono tego pola wyboru, przed zaksięgowaniem wierszy zlecenia serwisowego należy dołączyć do projektu zlecenie serwisowe utworzone ręcznie.</span><span class="sxs-lookup"><span data-stu-id="90be2-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="90be2-124">Tworzenie zlecenia serwisowego na podstawie formularza Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="90be2-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="90be2-125">Zlecenie serwisowe można utworzyć na podstawie formularza **Zamówienia sprzedaży**, używając kreatora **Utwórz nowe zlecenie serwisowe na podstawie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="90be2-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="90be2-126">Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia sprzedaży** \> **Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="90be2-126">Click **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="90be2-127">Otwórz odnośne zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="90be2-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="90be2-128">Na karcie **Zamówienie sprzedaży** kliknij opcję **Zlecenie serwisowe**, aby uruchomić kreatora **Utwórz nowe zlecenie serwisowe na podstawie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="90be2-128">On the **Sales order** tab, click **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="90be2-129">Kliknij przycisk **Dalej \>**, a następnie wykonaj następujące kroki na stronie **Wybierz umowę dla zlecenia serwisowego**:</span><span class="sxs-lookup"><span data-stu-id="90be2-129">Click **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="90be2-130">Użyj pola **Umowa serwisowa** w celu wybrania umowy serwisowej, z którą będzie skojarzone nowe zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="90be2-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="90be2-131">Opcjonalnie: Użyj pola **Identyfikator projektu** w celu skojarzenia tego zlecenia serwisowego z określonym projektem.</span><span class="sxs-lookup"><span data-stu-id="90be2-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="90be2-132">Kliknij przycisk **Dalej \>**, a następnie wykonaj następujące kroki na stronie **Utwórz zlecenie serwisowe**:</span><span class="sxs-lookup"><span data-stu-id="90be2-132">Click **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="90be2-133">W polu **Preferowany czas serwisu** wprowadź datę i godzinę rozpoczęcia serwisu.</span><span class="sxs-lookup"><span data-stu-id="90be2-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="90be2-134">Opcjonalnie: Zmodyfikuj tekst w polu **Opis**.</span><span class="sxs-lookup"><span data-stu-id="90be2-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="90be2-135">Domyślnie to pole zawiera opis umowy serwisowej wybranej na poprzedniej stronie.</span><span class="sxs-lookup"><span data-stu-id="90be2-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="90be2-136">W polu **Osoba odpowiedzialna** wybierz identyfikator pracownika odpowiedzialnego za umowę oraz — jeśli znasz — wprowadź identyfikator preferowanego przez klienta serwisanta mającego się zająć zgłoszeniem serwisowym.</span><span class="sxs-lookup"><span data-stu-id="90be2-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="90be2-137">W polu **Identyfikator kontaktu** wybierz osobę w firmie klienta, z którą należy kontaktować się w sprawach dotyczących danego zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="90be2-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="90be2-138">Kliknij przycisk **Dalej \>**, a następnie przycisk **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="90be2-138">Click **Next \>**, and then click **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="90be2-139">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="90be2-139">See also</span></span>

[<span data-ttu-id="90be2-140">Zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="90be2-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="90be2-141">Automatyczne tworzenie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="90be2-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="90be2-142">[Utwórz zlecenia serwisowe (formularz klasy)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="90be2-142">[Create service orders (class form)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\))</span></span> 


