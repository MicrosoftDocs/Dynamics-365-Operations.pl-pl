---
title: Tworzenie domyślnego odbiorcy
description: W tym temacie opisano sposób tworzenia domyślnego odbiorcy używanego podczas tworzenia kanału w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1dd4dfc5b8ca7af66941d081b4c20be0f5d6001d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993407"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="b2c0d-103">Tworzenie domyślnego odbiorcy</span><span class="sxs-lookup"><span data-stu-id="b2c0d-103">Create a default customer</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b2c0d-104">W tym temacie opisano sposób tworzenia domyślnego odbiorcy używanego podczas tworzenia kanału w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b2c0d-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="b2c0d-105">Overview</span></span>

<span data-ttu-id="b2c0d-106">Podczas tworzenia kanału lub online konieczne jest podanie odbiorcy domyślnego.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-106">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="b2c0d-107">Domyślny odbiorca można łatwo utworzyć po uprzednim utworzeniu grupy odbiorców i książki adresowej klienta.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-107">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="b2c0d-108">Tworzenie grupy odbiorców</span><span class="sxs-lookup"><span data-stu-id="b2c0d-108">Create a customer group</span></span>

<span data-ttu-id="b2c0d-109">Jeśli nie istnieją jeszcze grupy odbiorców, można ją utworzyć.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-109">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="b2c0d-110">Przykładami mogą być grupy odpowiadające różnym grupom odbiorców, takim jak hurtownie, handel detaliczny, Internet, pracownicy itd.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-110">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="b2c0d-111">Aby utworzyć grupę odbiorców, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-111">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="b2c0d-112">W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Pracownicy etatpwi \> Grupy uprawnień**.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-112">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="b2c0d-113">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b2c0d-114">W okienku **Grupa odbiorców** wprowadź identyfikator grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-114">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="b2c0d-115">W razie potrzeby w polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-115">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="b2c0d-116">W razie potrzeby w polu **Warunki płatności** wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-116">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="b2c0d-117">W polu **czas między datą płatności faktury i datą** płatności wprowadź odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-117">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="b2c0d-118">W polu **Domyślna grupa podatków** wprowadź grupę podatków, jeśli ma ona być stosowana.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-118">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="b2c0d-119">To pole wyboru **Ceny zawierają podatek**, jeśli ma być stosowane.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-119">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="b2c0d-120">W polu **Domyślna przyczyna odpisu** wprowadź odpowiednią wartość, jeśli ma zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-120">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="b2c0d-121">Poniższy obraz pokazuje kilku skonfigurowanych grup odbiorców.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-121">The following image shows several configured customer groups.</span></span>

![Grupy odbiorców](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="b2c0d-123">Tworzenie książki adresowej odbiorców</span><span class="sxs-lookup"><span data-stu-id="b2c0d-123">Create a customer address book</span></span>

<span data-ttu-id="b2c0d-124">Odbiorca musi być skojarzony z książką adresową.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-124">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="b2c0d-125">Jeśli jeszcze nie została utworzona, należy ją utworzyć.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-125">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="b2c0d-126">Aby utworzyć książkę adresową odbiorcy należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-126">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="b2c0d-127">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Książki adresowe**.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-127">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="b2c0d-128">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-128">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b2c0d-129">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-129">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="b2c0d-130">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-130">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="b2c0d-131">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-131">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b2c0d-132">Poniższy obraz przedstawia przykład książki adresowej.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-132">The following image shows an example address book.</span></span>

![Książka adresowa](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="b2c0d-134">Tworzenie domyślnego odbiorcy</span><span class="sxs-lookup"><span data-stu-id="b2c0d-134">Create a default customer</span></span>

<span data-ttu-id="b2c0d-135">Aby utworzyć domyślnego odbiorcę, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-135">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="b2c0d-136">W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Pracownicy etatpwi \> Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-136">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="b2c0d-137">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b2c0d-138">Z listy rozwijanej **Typ** wybierz „Osoba”.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-138">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="b2c0d-139">Z listy rozwijanej **Konto odbiorcy** wybierz lub wprowadź numer konta (na przykład „100001”).</span><span class="sxs-lookup"><span data-stu-id="b2c0d-139">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="b2c0d-140">Z listy rozwijanej **Imię** wybierz lub wprowadź nazwę (na przykład „domyślna”).</span><span class="sxs-lookup"><span data-stu-id="b2c0d-140">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="b2c0d-141">Z listy rozwijanej **Drugie imię** wybierz lub wprowadź nazwę (na przykład „Retail”).</span><span class="sxs-lookup"><span data-stu-id="b2c0d-141">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="b2c0d-142">Z listy rozwijanej **Nazwisko** wybierz lub wprowadź nazwę (na przykład „Odbiorca”).</span><span class="sxs-lookup"><span data-stu-id="b2c0d-142">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="b2c0d-143">Z listy rozwijanej **Waluta** wybierz lub wprowadź walutę (na przykład „USD”).</span><span class="sxs-lookup"><span data-stu-id="b2c0d-143">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="b2c0d-144">Z listy rozwijanej **Waluta** Wybierz utworzoną wcześniej grupę odbiorców.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-144">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="b2c0d-145">Z listy rozwijanej **Książki adresowe** wybierz istniejącą książkę adresową klienta.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-145">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="b2c0d-146">Wybierz opcję **Zapisz**, aby zapisać i powrócić do ekranu szczegółów odbiorcy dla nowego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-146">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="b2c0d-147">Nie trzeba dodawać adresu dla domyślnego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-147">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="b2c0d-148">Poniższy obraz przedstawia przykład tworzenia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-148">The following image shows an example of customer creation.</span></span>

![Domyślne tworzenie odbiorcy](media/default-customer-creation.png)

<span data-ttu-id="b2c0d-150">Poniższy rysunek przedstawia domyślną konfigurację klienta.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-150">The following image shows a default customer configuration.</span></span>

![Konfiguracja przykładowa odbiorcy](media/default-customer-configuration1.png)

<span data-ttu-id="b2c0d-152">Większość wartości domyślnych na ekranie szczegóły odbiorcy może pozostać, ale dwie wartości powinny zostać zmienione.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-152">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="b2c0d-153">Na ekranie szczegóły odbiorcy rozwiń węzeł **Ustawienia domyślne zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-153">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="b2c0d-154">Z listy rozwijanej **Witryna** wybierz lub wprowadź wstępnie skonfigurowany oddział.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-154">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="b2c0d-155">Z listy rozwijanej **Magazyn** wybierz lub wprowadź wstępnie skonfigurowany magazyn.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-155">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="b2c0d-156">Poniższy obraz przedstawia przykład konfiguracji tworzenia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="b2c0d-156">The following image shows an example customer configuration.</span></span>

![Przykład konfiguracji odbiorcy](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="b2c0d-158">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b2c0d-158">Additional resources</span></span>

[<span data-ttu-id="b2c0d-159">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="b2c0d-159">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="b2c0d-160">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="b2c0d-160">Channel setup prerequisites</span></span>](channels-prerequisites.md)
