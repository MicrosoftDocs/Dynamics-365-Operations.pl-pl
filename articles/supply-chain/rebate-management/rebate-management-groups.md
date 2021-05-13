---
title: Zarządzanie rabatami — grupy
description: W tym temacie opisano sposób konfigurowania danych dla grup zarządzania rabatami. Grupy zarządzania rabatami mogą być używane podczas obliczania rabatów i mogą być dołączane do rekordu głównego.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 2d1f8ed9def03afc97c0b4c5ea86430ff089aac6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819239"
---
# <a name="rebate-management-groups"></a><span data-ttu-id="fa5d6-104">Zarządzanie rabatami — grupy</span><span class="sxs-lookup"><span data-stu-id="fa5d6-104">Rebate management groups</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="fa5d6-105">Obliczenia rabatów i potrąceń mogą być oparte na grupach.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-105">Rebate and deduction calculations can be driven by groups.</span></span> <span data-ttu-id="fa5d6-106">Grupy zarządzania rabatami mogą być tworzone dla odbiorców, dostawców i towarów.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-106">Rebate management groups can be created for customers, vendors, and items.</span></span> <span data-ttu-id="fa5d6-107">Można je dołączyć do rekordu głównego.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-107">They can be attached to a master record.</span></span>

## <a name="rebate-management-customer-groups"></a><span data-ttu-id="fa5d6-108">Zarządzanie rabatami — grupy klientów</span><span class="sxs-lookup"><span data-stu-id="fa5d6-108">Rebate management customer groups</span></span>

<span data-ttu-id="fa5d6-109">Obliczenia dla grupy odbiorców są często tworzone dla łańcucha firm, na przykład dla łańcucha supermarketów lub firmy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-109">The calculation for a group of customers is often created for a chain of companies, such as a supermarket chain or a franchise company.</span></span> <span data-ttu-id="fa5d6-110">Ten typ obliczania jest zazwyczaj związany z rabatem.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-110">This type of calculation is usually related to a rebate.</span></span>

<span data-ttu-id="fa5d6-111">Potrącenie jest często obliczane bez uwzględnienia tego, kto został sprzedany na podstawie kwalifikacji do zamówienia.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-111">A deduction is often calculated without considering who the qualifying order was sold to.</span></span> <span data-ttu-id="fa5d6-112">Występują jednak pewne wyjątki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-112">However, there are exceptions.</span></span> <span data-ttu-id="fa5d6-113">Na przykład, odbiorca może utworzyć schemat potrąceń, w którym grupa klientów A będzie otrzymywać 4 procent, a grupa odbiorcy B będzie otrzymywać tylko 3 procent.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-113">For example, a licensee might create a deduction scheme where customer group A will receive 4 percent, but customer group B will receive only 3 percent.</span></span>

### <a name="set-up-customer-groups"></a><span data-ttu-id="fa5d6-114">Ustawianie grup odbiorców</span><span class="sxs-lookup"><span data-stu-id="fa5d6-114">Set up customer groups</span></span>

<span data-ttu-id="fa5d6-115">Aby pracować z grupami klientów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy klientów**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-115">To work with Rebate management customer groups, go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span> <span data-ttu-id="fa5d6-116">Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-116">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="fa5d6-117">Dla każdej grupy ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-117">For each group, set the following fields:</span></span>

- <span data-ttu-id="fa5d6-118">**Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-118">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="fa5d6-119">**Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-119">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-customer-group-assignments"></a><span data-ttu-id="fa5d6-120">Zarządzanie przypisaniami do grup klientów</span><span class="sxs-lookup"><span data-stu-id="fa5d6-120">Manage customer group assignments</span></span>

<span data-ttu-id="fa5d6-121">Każdy odbiorca może należeć do dowolnej liczby grup zarządzania rabatami.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-121">Each customer can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="fa5d6-122">Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy klientów.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-122">To view and assign group members, you can start from either the group list or the customer list.</span></span>

<span data-ttu-id="fa5d6-123">Aby wyświetlić, dodać lub usunąć odbiorców z wybranej grupy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-123">To view, add, or remove customers for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="fa5d6-124">Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabtami \> Grupy klientów**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-124">Go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span>
1. <span data-ttu-id="fa5d6-125">Wybierz grupę do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-125">Select the group to manage.</span></span>
1. <span data-ttu-id="fa5d6-126">W okienku akcji wybierz **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-126">On the Action Pane, select **Customers**.</span></span> <span data-ttu-id="fa5d6-127">Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę odbiorców, którzy już są członkami wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-127">The **Rebate management groups** page appears and shows a list of customers that are already members of the selected group.</span></span>
1. <span data-ttu-id="fa5d6-128">Aby dodać nowego klienta do grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-128">To add a new customer to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="fa5d6-129">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="fa5d6-130">**Konto klienta**  - wybierz dowolne ID klienta.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-130">**Customer account** – Select the customer account ID.</span></span>
    - <span data-ttu-id="fa5d6-131">**Nazwa** — wprowadź nazwę i/lub opis odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-131">**Name** – Enter a name and/or description of the customer.</span></span>

1. <span data-ttu-id="fa5d6-132">Aby usunąć klienta z grupy, wybierz klienta, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-132">To remove a customer from the group, select the customer, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="fa5d6-133">Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego klienta, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-133">To view, add, or remove group assignments for a selected customer, follow these steps.</span></span>

1. <span data-ttu-id="fa5d6-134">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-134">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="fa5d6-135">Wybierz klienta, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-135">Select the customer to work with.</span></span>
1. <span data-ttu-id="fa5d6-136">W okienku akcji, na karcie **Zarządzanie rabatami — umowy** w grupie **Obsługa** wybierz **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-136">On the Action Pane, on the **Customer** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="fa5d6-137">Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany klient.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-137">The **Rebate management groups** page appears and shows a list of groups that the selected customer already belongs to.</span></span>
1. <span data-ttu-id="fa5d6-138">Aby dodać nowego klienta do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-138">To add the customer to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="fa5d6-139">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-139">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="fa5d6-140">**Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-140">**Rebate management group** – Select the group to add the customer to.</span></span>
    - <span data-ttu-id="fa5d6-141">**Opis** — służy do wprowadzania opisu grupy (na przykład w celu wyjaśnienia, dlaczego odbiorca jest jej członkiem).</span><span class="sxs-lookup"><span data-stu-id="fa5d6-141">**Description** – Enter a description of the group (for example, to explain why the customer is a member of it).</span></span>

1. <span data-ttu-id="fa5d6-142">Aby usunąć klienta z grupy, wybierz grupy, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-142">To remove a customer from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="rebate-management-vendor-groups"></a><span data-ttu-id="fa5d6-143">Zarządzanie rabatami — grupy dostawców</span><span class="sxs-lookup"><span data-stu-id="fa5d6-143">Rebate management vendor groups</span></span>

<span data-ttu-id="fa5d6-144">Obliczenia dla grupy dostawców są często tworzone dla grupy punktów dostawy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-144">The calculation for a group of vendors is often created for a group of delivery points.</span></span> <span data-ttu-id="fa5d6-145">Ten typ obliczania jest zazwyczaj związany z rabatem.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-145">This type of calculation is usually related to a rebate.</span></span>

### <a name="set-up-vendor-groups"></a><span data-ttu-id="fa5d6-146">Konfigurowanie grup dostawców</span><span class="sxs-lookup"><span data-stu-id="fa5d6-146">Set up vendor groups</span></span>

<span data-ttu-id="fa5d6-147">Aby pracować z grupami dostawców w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy dostawców**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-147">To work with Rebate management vendor groups, go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span> <span data-ttu-id="fa5d6-148">Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-148">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="fa5d6-149">Dla każdej grupy ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-149">For each group, set the following fields:</span></span>

- <span data-ttu-id="fa5d6-150">**Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-150">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="fa5d6-151">**Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-151">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-vendor-group-assignments"></a><span data-ttu-id="fa5d6-152">Zarządzanie przypisaniami do grup dostawców</span><span class="sxs-lookup"><span data-stu-id="fa5d6-152">Manage vendor group assignments</span></span>

<span data-ttu-id="fa5d6-153">Każdy dostawca może należeć do dowolnej liczby grup zarządzania rabatami.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-153">Each vendor can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="fa5d6-154">Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy dostawców.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-154">To view and assign group members, you can start from either the group list or the vendor list.</span></span>

<span data-ttu-id="fa5d6-155">Aby wyświetlić, dodać lub usunąć dostawców z wybranej grupy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-155">To view, add, or remove vendors for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="fa5d6-156">Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy dostawców**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-156">Go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span>
1. <span data-ttu-id="fa5d6-157">Wybierz grupę do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-157">Select the group to manage.</span></span>
1. <span data-ttu-id="fa5d6-158">W okienku akcji wybierz pozycję **Dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-158">On the Action Pane, select **Vendors**.</span></span> <span data-ttu-id="fa5d6-159">Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę dostawców, którzy już są członkami wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-159">The **Rebate management groups** page appears and shows a list of vendors that are already members of the selected group.</span></span>
1. <span data-ttu-id="fa5d6-160">Aby dodać nowego dostawcę do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-160">To add a new vendor to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="fa5d6-161">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-161">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="fa5d6-162">**Konto dostawcy** - wybierz dowolne ID dostawcy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-162">**Vendor account** – Select the vendor account ID.</span></span>
    - <span data-ttu-id="fa5d6-163">**Nazwa** — wprowadź nazwę i/lub opis dostawcy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-163">**Name** – Enter a name and/or description of the vendor.</span></span>

1. <span data-ttu-id="fa5d6-164">Aby usunąć dostawcę z grupy, wybierz dostawcę, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-164">To remove a vendor from the group, select the vendor, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="fa5d6-165">Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego dostawcy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-165">To view, add, or remove group assignments for a selected vendor, follow these steps.</span></span>

1. <span data-ttu-id="fa5d6-166">Przejdź do pozycji **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-166">Go to **Accounts payable \> Vendors \> All vendors**.</span></span>
1. <span data-ttu-id="fa5d6-167">Wybierz dostawcy, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-167">Select the vendor to work with.</span></span>
1. <span data-ttu-id="fa5d6-168">W okienku akcji, na karcie **Dostawca** w grupie **Zarządzanie rabatami — umowy** wybierz **Grupy zarządznia rabatami**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-168">On the Action Pane, on the **Vendor** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="fa5d6-169">Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany dostawca.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-169">The **Rebate management groups** page appears and shows a list of groups that the selected vendor already belongs to.</span></span>
1. <span data-ttu-id="fa5d6-170">Aby dodać nowego dostawcę do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-170">To add the vendor to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="fa5d6-171">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-171">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="fa5d6-172">**Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać dostawcy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-172">**Rebate management group** – Select the group to add the vendor to.</span></span>
    - <span data-ttu-id="fa5d6-173">**Opis** — służy do wprowadzania opisu grupy (na przykład w celu wyjaśnienia, dlaczego dostawca jest jej członkiem).</span><span class="sxs-lookup"><span data-stu-id="fa5d6-173">**Description** – Enter a description of the group (for example, to explain why the vendor is a member of it).</span></span>

1. <span data-ttu-id="fa5d6-174">Aby usunąć dostawcę z grupy, wybierz grupy, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-174">To remove a vendor from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="item-rebate-groups"></a><span data-ttu-id="fa5d6-175">Grupy rabatowe dla pozycji</span><span class="sxs-lookup"><span data-stu-id="fa5d6-175">Item rebate groups</span></span>

<span data-ttu-id="fa5d6-176">Grupowanie towarów zapewnia większą elastyczność obliczania rabatów i potrąceń.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-176">By grouping items, you have more flexibility when rebates and deductions are calculated.</span></span> <span data-ttu-id="fa5d6-177">Takie podejście często jest rozwiązaniem bardziej efektywnym w ustawianiu rabatów i potrąceń dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-177">This approach is often a more efficient way to set up rebates and deductions for customers and vendors.</span></span>

### <a name="set-up-item-groups"></a><span data-ttu-id="fa5d6-178">Ustawianie grup pozycji</span><span class="sxs-lookup"><span data-stu-id="fa5d6-178">Set up item groups</span></span>

<span data-ttu-id="fa5d6-179">Aby pracować z grupami towarów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarów**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-179">To work with Rebate management item groups, go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span> <span data-ttu-id="fa5d6-180">Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-180">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="fa5d6-181">Dla każdej grupy ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-181">For each group, set the following fields:</span></span>

- <span data-ttu-id="fa5d6-182">**Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-182">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="fa5d6-183">**Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-183">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-item-group-assignments"></a><span data-ttu-id="fa5d6-184">Zarządzanie przypisaniami do grup towarów</span><span class="sxs-lookup"><span data-stu-id="fa5d6-184">Manage item group assignments</span></span>

<span data-ttu-id="fa5d6-185">Każdy towar może należeć do dowolnej liczby grup zarządzania rabatami.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-185">Each item can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="fa5d6-186">Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy towarów.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-186">To view and assign group members, you can start from either the group list or the item list.</span></span> <span data-ttu-id="fa5d6-187">Można również dodawać elementy na podstawie hierarchii kategorii.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-187">You can also add items based on your category hierarchy.</span></span>

<span data-ttu-id="fa5d6-188">Aby wyświetlić, dodać lub usunąć towary z wybranej grupy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-188">To view, add, or remove items for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="fa5d6-189">Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarow**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-189">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="fa5d6-190">Wybierz grupę do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-190">Select the group to manage.</span></span>
1. <span data-ttu-id="fa5d6-191">W okienku akcji kliknij pozycję **Towary**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-191">On the Action Pane, select **Items**.</span></span> <span data-ttu-id="fa5d6-192">Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę towarów, którzy już są członkami wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-192">The **Rebate management groups** page appears and shows a list of items that are already members of the selected group.</span></span>
1. <span data-ttu-id="fa5d6-193">Aby dodać nowego towar do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-193">To add a new item to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="fa5d6-194">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-194">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="fa5d6-195">**Konto towaru** - wybierz dowolne ID towaru.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-195">**Item account** – Select the item account ID.</span></span>
    - <span data-ttu-id="fa5d6-196">**Nazwa produktu** — wprowadź nazwę i/lub opis towaru.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-196">**Product name** – Enter a name and/or description of the item.</span></span>

1. <span data-ttu-id="fa5d6-197">Aby usunąć towar z grupy, wybierz dostawcę, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-197">To remove an item from the group, select the item, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="fa5d6-198">Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego towaru, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-198">To view, add, or remove group assignments for a selected item, follow these steps.</span></span>

1. <span data-ttu-id="fa5d6-199">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-199">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="fa5d6-200">Wybierz towar, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-200">Select the item to work with.</span></span>
1. <span data-ttu-id="fa5d6-201">W okienku akcji, na karcie **Produkt** w grupie **Zarządzanie rabatami — umowy** wybierz **Grupy zarządznia rabatami**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-201">On the Action Pane, on the **Product** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="fa5d6-202">Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany towar.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-202">The **Rebate management groups** page appears and shows a list of groups that the selected item already belongs to.</span></span>
1. <span data-ttu-id="fa5d6-203">Aby dodać towar do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-203">To add the item to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="fa5d6-204">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-204">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="fa5d6-205">**Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać towar.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-205">**Rebate management group** – Select the group to add the item to.</span></span>
    - <span data-ttu-id="fa5d6-206">**Opis** — służy do wprowadzania opisu grupy (na przykład w celu wyjaśnienia, dlaczego towar jest jej członkiem).</span><span class="sxs-lookup"><span data-stu-id="fa5d6-206">**Description** – Enter a description of the group (for example, to explain why the item is a member of it).</span></span>

1. <span data-ttu-id="fa5d6-207">Aby usunąć towar z grupy, wybierz grupę, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-207">To remove an item from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="fa5d6-208">Aby dodać towary do grupy na podstawie hierarchii kategorii, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-208">To add items to a group based on your category hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="fa5d6-209">Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarow**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-209">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="fa5d6-210">Wybierz grupę do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-210">Select the group to manage.</span></span>
1. <span data-ttu-id="fa5d6-211">W okienku akcji kliknij pozycję **Dodaj towary**.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-211">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="fa5d6-212">W oknie dialogowym **Dodawanie towarów** w polu **Hierarchia kategorii** wybierz kategorię najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-212">In the **Add items** dialog box, in the **Category hierarchy** field, select a top-level category.</span></span>
1. <span data-ttu-id="fa5d6-213">Hierarchia towarów jest otwarta w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-213">The item hierarchy is opened in the left pane.</span></span> <span data-ttu-id="fa5d6-214">Wybierz poziom hierarchii, którego chcesz szukać.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-214">Select the hierarchy level that you're looking for.</span></span> 
1. <span data-ttu-id="fa5d6-215">Elementy z wybranej hierarchii i poziomu hierarchii są teraz wyświetlane w prawym okienku.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-215">Items from the selected hierarchy and hierarchy level are now listed in the right pane.</span></span> <span data-ttu-id="fa5d6-216">Aby pracować z tym okienkiem, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="fa5d6-216">Follow these steps to work with the pane:</span></span>

    - <span data-ttu-id="fa5d6-217">Zaznacz pole wyboru przy każdym towarze, który chcesz dodać.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-217">Select the check box for each item that you want to add.</span></span>
    - <span data-ttu-id="fa5d6-218">Zaznacz pole wyboru w nagłówku siatki, aby zaznaczyć wszystkie pozycje, które są wymienione.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-218">Select the check box on the grid header to select all the items that are listed.</span></span>
    - <span data-ttu-id="fa5d6-219">Wybierz przycisk **Pokaż wybrane**, aby przefiltrować siatkę tak, aby wyświetlała tylko wybrane do tej pory elementy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-219">Select the **Show selected** button to filter the grid so that it shows only the items that you've selected so far.</span></span> <span data-ttu-id="fa5d6-220">Wybierz przycisk ponownie, aby powrócić do pełnej listy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-220">Select the button again to return to the full list.</span></span>

1. <span data-ttu-id="fa5d6-221">Wybierz przycisk **OK**, aby zastosować wybraną pozycję do wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="fa5d6-221">Select **OK** to apply your item selection to the selected group.</span></span>