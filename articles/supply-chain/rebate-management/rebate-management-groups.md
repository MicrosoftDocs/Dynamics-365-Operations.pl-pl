---
title: Zarządzanie rabatami — grupy
description: W tym temacie opisano sposób konfigurowania danych dla grup zarządzania rabatami. Grupy zarządzania rabatami mogą być używane podczas obliczania rabatów i mogą być dołączane do rekordu głównego.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee5a195b3d2881ff70fb1f0d4063ed681e874648
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271084"
---
# <a name="rebate-management-groups"></a><span data-ttu-id="bcc95-104">Zarządzanie rabatami — grupy</span><span class="sxs-lookup"><span data-stu-id="bcc95-104">Rebate management groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bcc95-105">Obliczenia dotyczące zarządzania rabatami mogą być prowadzone przez grupy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-105">Rebate management calculations can be driven by groups.</span></span> <span data-ttu-id="bcc95-106">Grupy zarządzania rabatami mogą być tworzone dla odbiorców, dostawców i towarów.</span><span class="sxs-lookup"><span data-stu-id="bcc95-106">Rebate management groups can be created for customers, vendors, and items.</span></span> <span data-ttu-id="bcc95-107">Można je dołączyć do rekordu głównego.</span><span class="sxs-lookup"><span data-stu-id="bcc95-107">They can be attached to a master record.</span></span>

## <a name="rebate-management-customer-groups"></a><span data-ttu-id="bcc95-108">Zarządzanie rabatami — grupy klientów</span><span class="sxs-lookup"><span data-stu-id="bcc95-108">Rebate management customer groups</span></span>

<span data-ttu-id="bcc95-109">Obliczenia dla grupy odbiorców są często tworzone dla łańcucha firm, na przykład dla łańcucha supermarketów lub firmy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-109">The calculation for a group of customers is often created for a chain of companies, such as a supermarket chain or a franchise company.</span></span> <span data-ttu-id="bcc95-110">Ten typ obliczania jest zazwyczaj związany z rabatem.</span><span class="sxs-lookup"><span data-stu-id="bcc95-110">This type of calculation is usually related to a rebate.</span></span>

<span data-ttu-id="bcc95-111">Potrącenie jest często obliczane bez uwzględnienia tego, kto został sprzedany na podstawie kwalifikacji do zamówienia.</span><span class="sxs-lookup"><span data-stu-id="bcc95-111">A deduction is often calculated without considering who the qualifying order was sold to.</span></span> <span data-ttu-id="bcc95-112">Występują jednak pewne wyjątki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-112">However, there are exceptions.</span></span> <span data-ttu-id="bcc95-113">Na przykład, odbiorca może utworzyć schemat potrąceń, w którym grupa klientów A będzie otrzymywać 4 procent, a grupa odbiorcy B będzie otrzymywać tylko 3 procent.</span><span class="sxs-lookup"><span data-stu-id="bcc95-113">For example, a licensee might create a deduction scheme where customer group A will receive 4 percent, but customer group B will receive only 3 percent.</span></span>

### <a name="set-up-customer-groups"></a><span data-ttu-id="bcc95-114">Ustawianie grup odbiorców</span><span class="sxs-lookup"><span data-stu-id="bcc95-114">Set up customer groups</span></span>

<span data-ttu-id="bcc95-115">Aby pracować z grupami klientów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy klientów**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-115">To work with Rebate management customer groups, go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span> <span data-ttu-id="bcc95-116">Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="bcc95-116">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="bcc95-117">Dla każdej grupy ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="bcc95-117">For each group, set the following fields:</span></span>

- <span data-ttu-id="bcc95-118">**Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="bcc95-118">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="bcc95-119">**Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-119">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-customer-group-assignments"></a><span data-ttu-id="bcc95-120">Zarządzanie przypisaniami do grup klientów</span><span class="sxs-lookup"><span data-stu-id="bcc95-120">Manage customer group assignments</span></span>

<span data-ttu-id="bcc95-121">Każdy odbiorca może należeć do dowolnej liczby grup zarządzania rabatami.</span><span class="sxs-lookup"><span data-stu-id="bcc95-121">Each customer can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="bcc95-122">Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy klientów.</span><span class="sxs-lookup"><span data-stu-id="bcc95-122">To view and assign group members, you can start from either the group list or the customer list.</span></span>

<span data-ttu-id="bcc95-123">Aby wyświetlić, dodać lub usunąć odbiorców z wybranej grupy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-123">To view, add, or remove customers for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="bcc95-124">Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabtami \> Grupy klientów**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-124">Go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span>
1. <span data-ttu-id="bcc95-125">Wybierz grupę do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="bcc95-125">Select the group to manage.</span></span>
1. <span data-ttu-id="bcc95-126">W okienku akcji wybierz **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-126">On the Action Pane, select **Customers**.</span></span> <span data-ttu-id="bcc95-127">Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę odbiorców, którzy już są członkami wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-127">The **Rebate management groups** page appears and shows a list of customers that are already members of the selected group.</span></span>
1. <span data-ttu-id="bcc95-128">Aby dodać nowego klienta do grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-128">To add a new customer to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="bcc95-129">Następnie ustaw następujące pole dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="bcc95-129">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="bcc95-130">**Konto klienta**  - wybierz dowolne ID klienta.</span><span class="sxs-lookup"><span data-stu-id="bcc95-130">**Customer account** – Select the customer account ID.</span></span>

1. <span data-ttu-id="bcc95-131">Aby usunąć klienta z grupy, wybierz klienta, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="bcc95-131">To remove a customer from the group, select the customer, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="bcc95-132">Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego klienta, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-132">To view, add, or remove group assignments for a selected customer, follow these steps.</span></span>

1. <span data-ttu-id="bcc95-133">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-133">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="bcc95-134">Wybierz klienta, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="bcc95-134">Select the customer to work with.</span></span>
1. <span data-ttu-id="bcc95-135">W okienku akcji, na karcie **Zarządzanie rabatami — umowy** w grupie **Obsługa** wybierz **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-135">On the Action Pane, on the **Customer** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="bcc95-136">Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany klient.</span><span class="sxs-lookup"><span data-stu-id="bcc95-136">The **Rebate management groups** page appears and shows a list of groups that the selected customer already belongs to.</span></span>
1. <span data-ttu-id="bcc95-137">Aby dodać nowego klienta do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-137">To add the customer to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="bcc95-138">Następnie ustaw następujące pole dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="bcc95-138">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="bcc95-139">**Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-139">**Rebate management group** – Select the group to add the customer to.</span></span>

1. <span data-ttu-id="bcc95-140">Aby usunąć klienta z grupy, wybierz grupy, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="bcc95-140">To remove a customer from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="rebate-management-vendor-groups"></a><span data-ttu-id="bcc95-141">Zarządzanie rabatami — grupy dostawców</span><span class="sxs-lookup"><span data-stu-id="bcc95-141">Rebate management vendor groups</span></span>

<span data-ttu-id="bcc95-142">Obliczenia dla grupy dostawców są często tworzone dla grupy punktów dostawy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-142">The calculation for a group of vendors is often created for a group of delivery points.</span></span> <span data-ttu-id="bcc95-143">Ten typ obliczania jest zazwyczaj związany z rabatem.</span><span class="sxs-lookup"><span data-stu-id="bcc95-143">This type of calculation is usually related to a rebate.</span></span>

### <a name="set-up-vendor-groups"></a><span data-ttu-id="bcc95-144">Konfigurowanie grup dostawców</span><span class="sxs-lookup"><span data-stu-id="bcc95-144">Set up vendor groups</span></span>

<span data-ttu-id="bcc95-145">Aby pracować z grupami dostawców w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy dostawców**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-145">To work with Rebate management vendor groups, go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span> <span data-ttu-id="bcc95-146">Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="bcc95-146">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="bcc95-147">Dla każdej grupy ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="bcc95-147">For each group, set the following fields:</span></span>

- <span data-ttu-id="bcc95-148">**Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="bcc95-148">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="bcc95-149">**Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-149">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-vendor-group-assignments"></a><span data-ttu-id="bcc95-150">Zarządzanie przypisaniami do grup dostawców</span><span class="sxs-lookup"><span data-stu-id="bcc95-150">Manage vendor group assignments</span></span>

<span data-ttu-id="bcc95-151">Każdy dostawca może należeć do dowolnej liczby grup zarządzania rabatami.</span><span class="sxs-lookup"><span data-stu-id="bcc95-151">Each vendor can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="bcc95-152">Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy dostawców.</span><span class="sxs-lookup"><span data-stu-id="bcc95-152">To view and assign group members, you can start from either the group list or the vendor list.</span></span>

<span data-ttu-id="bcc95-153">Aby wyświetlić, dodać lub usunąć dostawców z wybranej grupy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-153">To view, add, or remove vendors for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="bcc95-154">Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy dostawców**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-154">Go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span>
1. <span data-ttu-id="bcc95-155">Wybierz grupę do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="bcc95-155">Select the group to manage.</span></span>
1. <span data-ttu-id="bcc95-156">W okienku akcji wybierz pozycję **Dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-156">On the Action Pane, select **Vendors**.</span></span> <span data-ttu-id="bcc95-157">Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę dostawców, którzy już są członkami wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-157">The **Rebate management groups** page appears and shows a list of vendors that are already members of the selected group.</span></span>
1. <span data-ttu-id="bcc95-158">Aby dodać nowego dostawcę do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-158">To add a new vendor to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="bcc95-159">Następnie ustaw następujące pole dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="bcc95-159">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="bcc95-160">**Konto dostawcy** - wybierz dowolne ID dostawcy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-160">**Vendor account** – Select the vendor account ID.</span></span>

1. <span data-ttu-id="bcc95-161">Aby usunąć dostawcę z grupy, wybierz dostawcę, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="bcc95-161">To remove a vendor from the group, select the vendor, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="bcc95-162">Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego dostawcy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-162">To view, add, or remove group assignments for a selected vendor, follow these steps.</span></span>

1. <span data-ttu-id="bcc95-163">Przejdź do pozycji **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-163">Go to **Accounts payable \> Vendors \> All vendors**.</span></span>
1. <span data-ttu-id="bcc95-164">Wybierz dostawcy, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="bcc95-164">Select the vendor to work with.</span></span>
1. <span data-ttu-id="bcc95-165">W okienku akcji, na karcie **Dostawca** w grupie **Zarządzanie rabatami — umowy** wybierz **Grupy zarządznia rabatami**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-165">On the Action Pane, on the **Vendor** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="bcc95-166">Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany dostawca.</span><span class="sxs-lookup"><span data-stu-id="bcc95-166">The **Rebate management groups** page appears and shows a list of groups that the selected vendor already belongs to.</span></span>
1. <span data-ttu-id="bcc95-167">Aby dodać nowego dostawcę do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-167">To add the vendor to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="bcc95-168">Następnie ustaw następujące pole dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="bcc95-168">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="bcc95-169">**Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać dostawcy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-169">**Rebate management group** – Select the group to add the vendor to.</span></span>

1. <span data-ttu-id="bcc95-170">Aby usunąć dostawcę z grupy, wybierz grupy, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="bcc95-170">To remove a vendor from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="item-rebate-groups"></a><span data-ttu-id="bcc95-171">Grupy rabatowe dla pozycji</span><span class="sxs-lookup"><span data-stu-id="bcc95-171">Item rebate groups</span></span>

<span data-ttu-id="bcc95-172">Grupowanie towarów zapewnia większą elastyczność obliczania rabatów i potrąceń.</span><span class="sxs-lookup"><span data-stu-id="bcc95-172">By grouping items, you have more flexibility when rebates and deductions are calculated.</span></span> <span data-ttu-id="bcc95-173">Takie podejście często jest rozwiązaniem bardziej efektywnym w ustawianiu rabatów i potrąceń dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="bcc95-173">This approach is often a more efficient way to set up rebates and deductions for customers and vendors.</span></span>

### <a name="set-up-item-groups"></a><span data-ttu-id="bcc95-174">Ustawianie grup pozycji</span><span class="sxs-lookup"><span data-stu-id="bcc95-174">Set up item groups</span></span>

<span data-ttu-id="bcc95-175">Aby pracować z grupami towarów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarów**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-175">To work with Rebate management item groups, go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span> <span data-ttu-id="bcc95-176">Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="bcc95-176">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="bcc95-177">Dla każdej grupy ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="bcc95-177">For each group, set the following fields:</span></span>

- <span data-ttu-id="bcc95-178">**Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="bcc95-178">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="bcc95-179">**Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-179">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-item-group-assignments"></a><span data-ttu-id="bcc95-180">Zarządzanie przypisaniami do grup towarów</span><span class="sxs-lookup"><span data-stu-id="bcc95-180">Manage item group assignments</span></span>

<span data-ttu-id="bcc95-181">Każdy towar może należeć do dowolnej liczby grup zarządzania rabatami.</span><span class="sxs-lookup"><span data-stu-id="bcc95-181">Each item can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="bcc95-182">Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy towarów.</span><span class="sxs-lookup"><span data-stu-id="bcc95-182">To view and assign group members, you can start from either the group list or the item list.</span></span> <span data-ttu-id="bcc95-183">Można również dodawać elementy na podstawie hierarchii kategorii.</span><span class="sxs-lookup"><span data-stu-id="bcc95-183">You can also add items based on your category hierarchy.</span></span>

<span data-ttu-id="bcc95-184">Aby wyświetlić, dodać lub usunąć towary z wybranej grupy, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-184">To view, add, or remove items for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="bcc95-185">Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarow**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-185">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="bcc95-186">Wybierz grupę do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="bcc95-186">Select the group to manage.</span></span>
1. <span data-ttu-id="bcc95-187">W okienku akcji kliknij pozycję **Towary**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-187">On the Action Pane, select **Items**.</span></span> <span data-ttu-id="bcc95-188">Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę towarów, którzy już są członkami wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-188">The **Rebate management groups** page appears and shows a list of items that are already members of the selected group.</span></span>
1. <span data-ttu-id="bcc95-189">Aby dodać nowego towar do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-189">To add a new item to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="bcc95-190">Następnie ustaw następujące pole dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="bcc95-190">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="bcc95-191">**Konto towaru** - wybierz dowolne ID towaru.</span><span class="sxs-lookup"><span data-stu-id="bcc95-191">**Item account** – Select the item account ID.</span></span>

1. <span data-ttu-id="bcc95-192">Aby usunąć towar z grupy, wybierz dostawcę, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="bcc95-192">To remove an item from the group, select the item, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="bcc95-193">Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego towaru, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-193">To view, add, or remove group assignments for a selected item, follow these steps.</span></span>

1. <span data-ttu-id="bcc95-194">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-194">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="bcc95-195">Wybierz towar, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="bcc95-195">Select the item to work with.</span></span>
1. <span data-ttu-id="bcc95-196">W okienku akcji, na karcie **Produkt** w grupie **Zarządzanie rabatami — umowy** wybierz **Grupy zarządznia rabatami**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-196">On the Action Pane, on the **Product** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="bcc95-197">Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany towar.</span><span class="sxs-lookup"><span data-stu-id="bcc95-197">The **Rebate management groups** page appears and shows a list of groups that the selected item already belongs to.</span></span>
1. <span data-ttu-id="bcc95-198">Aby dodać towar do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-198">To add the item to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="bcc95-199">Następnie ustaw następujące pole dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="bcc95-199">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="bcc95-200">**Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać towar.</span><span class="sxs-lookup"><span data-stu-id="bcc95-200">**Rebate management group** – Select the group to add the item to.</span></span>

1. <span data-ttu-id="bcc95-201">Aby usunąć towar z grupy, wybierz grupę, a następnie wybierz polecenie **Usuń** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="bcc95-201">To remove an item from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="bcc95-202">Aby dodać towary do grupy na podstawie hierarchii kategorii, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bcc95-202">To add items to a group based on your category hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="bcc95-203">Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarow**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-203">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="bcc95-204">Wybierz grupę do zarządzania.</span><span class="sxs-lookup"><span data-stu-id="bcc95-204">Select the group to manage.</span></span>
1. <span data-ttu-id="bcc95-205">W okienku akcji kliknij pozycję **Dodaj towary**.</span><span class="sxs-lookup"><span data-stu-id="bcc95-205">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="bcc95-206">W oknie dialogowym **Dodawanie towarów** w polu **Hierarchia kategorii** wybierz kategorię najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="bcc95-206">In the **Add items** dialog box, in the **Category hierarchy** field, select a top-level category.</span></span>
1. <span data-ttu-id="bcc95-207">Hierarchia towarów jest otwarta w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="bcc95-207">The item hierarchy is opened in the left pane.</span></span> <span data-ttu-id="bcc95-208">Wybierz poziom hierarchii, którego chcesz szukać.</span><span class="sxs-lookup"><span data-stu-id="bcc95-208">Select the hierarchy level that you're looking for.</span></span> 
1. <span data-ttu-id="bcc95-209">Elementy z wybranej hierarchii i poziomu hierarchii są teraz wyświetlane w prawym okienku.</span><span class="sxs-lookup"><span data-stu-id="bcc95-209">Items from the selected hierarchy and hierarchy level are now listed in the right pane.</span></span> <span data-ttu-id="bcc95-210">Aby pracować z tym okienkiem, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="bcc95-210">Follow these steps to work with the pane:</span></span>

    - <span data-ttu-id="bcc95-211">Zaznacz pole wyboru przy każdym towarze, który chcesz dodać.</span><span class="sxs-lookup"><span data-stu-id="bcc95-211">Select the check box for each item that you want to add.</span></span>
    - <span data-ttu-id="bcc95-212">Zaznacz pole wyboru w nagłówku siatki, aby zaznaczyć wszystkie pozycje, które są wymienione.</span><span class="sxs-lookup"><span data-stu-id="bcc95-212">Select the check box on the grid header to select all the items that are listed.</span></span>
    - <span data-ttu-id="bcc95-213">Wybierz przycisk **Pokaż wybrane**, aby przefiltrować siatkę tak, aby wyświetlała tylko wybrane do tej pory elementy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-213">Select the **Show selected** button to filter the grid so that it shows only the items that you've selected so far.</span></span> <span data-ttu-id="bcc95-214">Wybierz przycisk ponownie, aby powrócić do pełnej listy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-214">Select the button again to return to the full list.</span></span>

1. <span data-ttu-id="bcc95-215">Wybierz przycisk **OK**, aby zastosować wybraną pozycję do wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="bcc95-215">Select **OK** to apply your item selection to the selected group.</span></span>
