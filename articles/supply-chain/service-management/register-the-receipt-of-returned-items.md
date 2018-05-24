---
title: "Rejestrowanie przyjęcia zwróconych towarów"
description: "Przyjęcie zwróconych towarów można zarejestrować za pomocą formularza Przegląd przyjęć lub Rejestracja."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSArrivalOverview, InventTransRegister
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
ms.openlocfilehash: 550b59a64fb0e81a56d6fea921e1b1df20c5f6e6
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---


# <a name="register-the-receipt-of-returned-items"></a><span data-ttu-id="4a867-103">Rejestrowanie przyjęcia zwróconych towarów</span><span class="sxs-lookup"><span data-stu-id="4a867-103">Register the receipt of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="4a867-104">Istnieją dwie metody rejestrowania przyjęcia zwróconych towarów.</span><span class="sxs-lookup"><span data-stu-id="4a867-104">There are two methods for registering the receipt of returned items.</span></span> <span data-ttu-id="4a867-105">Pierwsza metoda to proces przyjęcia w magazynie, w którym należy użyć formularza **Przegląd przyjęć**.</span><span class="sxs-lookup"><span data-stu-id="4a867-105">The first method is a warehouse receiving process that uses the **Arrival overview** form.</span></span> <span data-ttu-id="4a867-106">Druga metoda korzysta z formularza **Rejestracja**.</span><span class="sxs-lookup"><span data-stu-id="4a867-106">The second uses the **Registration** form.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a><span data-ttu-id="4a867-107">Rejestrowanie zwróconych towarów za pomocą formularza Przegląd przyjęć</span><span class="sxs-lookup"><span data-stu-id="4a867-107">Register the receipt of returned items in the Arrival overview form</span></span>

<span data-ttu-id="4a867-108">Za pomocą formularza **Przegląd przyjęć** można zidentyfikować wysyłkę zwrotną według numeru autoryzacji zwrotu (RMA).</span><span class="sxs-lookup"><span data-stu-id="4a867-108">You can use the **Arrival overview** form to identify a return shipment by its Return Material Authorization (RMA) number.</span></span> <span data-ttu-id="4a867-109">Jeśli nazwa arkusza jest zdefiniowana na karcie **Ustawienia** i istnieją wiersze arkusza, które odpowiadają wierszom wybranym w formularzu **Przegląd przyjęć**, nowy nagłówek arkusza jest tworzony po kliknięciu przycisku **Rozpocznij przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="4a867-109">If a journal name is defined on the **Setup** tab, and journal lines that correspond to the lines selected on the **Arrival overview** form exist, a new journal header is created when you click **Start arrival**.</span></span>

1.  <span data-ttu-id="4a867-110">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Przegląd przyjęć**.</span><span class="sxs-lookup"><span data-stu-id="4a867-110">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="4a867-111">W polu **Nazwa konfiguracji** zaznacz opcję **Zamówienie zwrotu**, a następnie kliknij przycisk **Aktualizuj**.</span><span class="sxs-lookup"><span data-stu-id="4a867-111">In the **Setup name** field, select **Return order**, and then click **Update**.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="4a867-112">Wprowadzając odpowiednie dane w polach <STRONG>Zakres</STRONG>, można ograniczyć liczbę wyników wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="4a867-112">You can use the <STRONG>Range</STRONG> fields to narrow the search results.</span></span> <span data-ttu-id="4a867-113">Aby uzyskać dokładny wynik, w polu <STRONG>Numer autoryzacji zwrotu</STRONG> można wpisać lub wybrać numer RMA.</span><span class="sxs-lookup"><span data-stu-id="4a867-113">You can type or select the RMA number in the <STRONG>RMA number</STRONG> field for an exact result.</span></span> <span data-ttu-id="4a867-114">Aby zdefiniować i zapisać zestaw filtrów ograniczających wyświetlanie przywozów, kliknij kartę <STRONG>Ustawienia</STRONG>. Dostępne filtry obejmują typy, magazyny i doki.</span><span class="sxs-lookup"><span data-stu-id="4a867-114">To define and save a set of filters that will restrict which incoming arrivals are displayed, click the <STRONG>Setup</STRONG> tab. The available filters include types, warehouses, and docks.</span></span></P>

    

    > [!WARNING]
    > <P><span data-ttu-id="4a867-115">Zamówień zwrotu nie można mieszać z innymi typami przyjęć w formularzu <STRONG>Przegląd przyjęć</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a867-115">Return orders cannot be mixed with other arrival types in the <STRONG>Arrival overview</STRONG> form.</span></span> <span data-ttu-id="4a867-116">Dlatego odniesieniem będzie zawsze zamówienie sprzedaży, ale brak identyfikatora zamówienia sprzedaży zostanie określony w nagłówku arkusza.</span><span class="sxs-lookup"><span data-stu-id="4a867-116">Therefore, the reference will always be sales order, but no sales order ID will be specified on the journal header.</span></span></P>



3.  <span data-ttu-id="4a867-117">W siatce **Przyjęcia** znajdź wiersz odpowiadający zwracanemu towarowi, a następnie zaznacz pole wyboru w kolumnie **Zaznacz do przyjęcia**.</span><span class="sxs-lookup"><span data-stu-id="4a867-117">In the **Receipts** grid, locate the line that matches the item being returned, and then select the check box in the **Select for arrival** column.</span></span>

4.  <span data-ttu-id="4a867-118">Aby wykluczyć określone wiersze z pokwitowania zwrotu, na przykład towary z pierwotnego zamówienia, które nie znalazły się w wysyłce zwrotnej, wyczyść odpowiednie pola wyboru **Zaznacz do przyjęcia** w tabeli **Wiersze** w dolnej części formularza.</span><span class="sxs-lookup"><span data-stu-id="4a867-118">To exclude certain lines from the return receipt, such as items from the original order that were not included in the return shipment, clear the associated **Select for arrival** check boxes in the **Lines** table in the lower part of the form.</span></span>

5.  <span data-ttu-id="4a867-119">Kliknij przycisk **Rozpocznij przyjęcie**, aby skonfigurować arkusz przyjęć.</span><span class="sxs-lookup"><span data-stu-id="4a867-119">Click the **Start arrival** button to create an arrival journal.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="4a867-120">W programie można zaznaczyć wiele zwrotów zamówień i uwzględnić je wszystkie w jednym procesie przyjęcia towaru.</span><span class="sxs-lookup"><span data-stu-id="4a867-120">You can select multiple return orders and include them all in a single arrival process.</span></span> <span data-ttu-id="4a867-121">Każdy wiersz zwrotu zamówienia zostanie skopiowany do odpowiedniego wiersza arkusza przyjęcia towaru.</span><span class="sxs-lookup"><span data-stu-id="4a867-121">Each return order line will be copied into a corresponding item arrival journal line.</span></span></P>

    

    > [!NOTE]
    > <P><span data-ttu-id="4a867-122">Można także ręcznie utworzyć arkusz przywozu za pomocą formularza <STRONG>Przyjęcie pozycji</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a867-122">You can also manually create an arrival journal by using the <STRONG>Item arrival</STRONG> form.</span></span> 



6.  <span data-ttu-id="4a867-123">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Arkusze** \> **Przyjęcie pozycji** \> **Przyjęcie pozycji**.</span><span class="sxs-lookup"><span data-stu-id="4a867-123">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>

7.  <span data-ttu-id="4a867-124">Wybierz arkusz przywozu, który został właśnie utworzony, a następnie kliknij przycisk **Wiersze**, aby otworzyć formularz **Wiersze arkusza, lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="4a867-124">Select the arrival journal that you just created and then click **Lines** to open the **Journal lines, locations** form.</span></span>

8.  <span data-ttu-id="4a867-125">Na karcie **Ogólne** dostosuj liczbę w polu **Ilość**, jeśli jest to wymagane, a następnie przypisz kod dyspozycji w polu **Kod dyspozycji**.</span><span class="sxs-lookup"><span data-stu-id="4a867-125">On the **General** tab, adjust the number in the **Quantity** field, if it is required, and then assign a disposition code in the **Disposition code** field.</span></span>
    
    <span data-ttu-id="4a867-126">Alternatywnie można zaznaczyć pole wyboru **Zarządzanie kwarantanną**, aby zwracane towary przechodziły proces inspekcji w kontekście zlecenia kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="4a867-126">Alternatively, you can select the **Quarantine management** check box to have the returned items sent through an inspection process in the context of a quarantine order.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="4a867-127">Jeśli wyślesz zwracane towary do kwarantanny, nie można określić kodu dyspozycji.</span><span class="sxs-lookup"><span data-stu-id="4a867-127">If you send the returned items through quarantine, you cannot specify a disposition code.</span></span></P>



9.  <span data-ttu-id="4a867-128">Kliknij przycisk **Weryfikuj**.</span><span class="sxs-lookup"><span data-stu-id="4a867-128">Click the **Validate** button.</span></span>

10. <span data-ttu-id="4a867-129">Jeśli w procesie sprawdzania poprawności nie występują błędy, kliknij opcję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="4a867-129">If there are no errors in the validation process, click **Post**.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a><span data-ttu-id="4a867-130">Zarejestruj zwrócone towary za pomocą formularza rejestracji</span><span class="sxs-lookup"><span data-stu-id="4a867-130">Register the receipt of returned items in the Registration form</span></span>

<span data-ttu-id="4a867-131">Jako alternatywy do korzystania z formularza **Przegląd przyjęć** można użyć formularza **Rejestracja**, aby zarejestrować przywóz zwracanych towarów.</span><span class="sxs-lookup"><span data-stu-id="4a867-131">As an alternative to using the **Arrival overview** form, you can use the **Registration** form to register the arrival of returned items.</span></span>

1.  <span data-ttu-id="4a867-132">Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.</span><span class="sxs-lookup"><span data-stu-id="4a867-132">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span> <span data-ttu-id="4a867-133">Utwórz nowe zamówienie zwrotu lub otwórz zamówienie zwrotu z listy.</span><span class="sxs-lookup"><span data-stu-id="4a867-133">Create a new return order or open the return order from the list.</span></span> <span data-ttu-id="4a867-134">Na skróconej karcie **Wiersze** wybierz wiersz zamówienia zwrotu.</span><span class="sxs-lookup"><span data-stu-id="4a867-134">On the **Lines** FastTab, select the return order line.</span></span> <span data-ttu-id="4a867-135">Kliknij opcję **Aktualizuj wiersz**, a następnie opcję **Rejestracja**.</span><span class="sxs-lookup"><span data-stu-id="4a867-135">Click **Update line**, and then click **Registration**.</span></span>

2.  <span data-ttu-id="4a867-136">Przypisz kod dyspozycji w polu **Kod dyspozycji**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a867-136">Assign a disposition code in the **Disposition code** field, and then click **OK**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="4a867-137">Nie można wysłać towaru do celów inspekcji jako zlecenia kwarantanny, korzystając z formularza <STRONG>Rejestracja</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a867-137">It is not possible to send the item for inspection as a quarantine order using the <STRONG>Registration</STRONG> form.</span></span></P>



3.  <span data-ttu-id="4a867-138">W siatce **Transakcje** wybierz transakcję do zarejestrowania.</span><span class="sxs-lookup"><span data-stu-id="4a867-138">In the **Transactions** grid, select the transaction to be registered.</span></span>

4.  <span data-ttu-id="4a867-139">W siatce **Rejestruj teraz** kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="4a867-139">In the **Register now** grid, click **Add**.</span></span> <span data-ttu-id="4a867-140">Powtarzaj poprzednie dwa kroki, dopóki wszystkie zwrócone towary nie będą wyświetlane w siatce **Rejestruj teraz**.</span><span class="sxs-lookup"><span data-stu-id="4a867-140">Repeat the previous two steps until all of the returned items appear in the **Register now** grid.</span></span>

5.  <span data-ttu-id="4a867-141">Kliknij przycisk **Zaksięguj wszystkie**.</span><span class="sxs-lookup"><span data-stu-id="4a867-141">Click **Post all**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a867-142">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4a867-142">See also</span></span>

<span data-ttu-id="4a867-143">[Przegląd przyjęć (formularz)](https://technet.microsoft.com/en-us/library/hh227654\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="4a867-143">[Arrival overview (form)](https://technet.microsoft.com/en-us/library/hh227654\(v=ax.60\))</span></span>

  



