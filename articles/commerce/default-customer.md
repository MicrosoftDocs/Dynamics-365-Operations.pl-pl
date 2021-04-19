---
title: Tworzenie domyślnego odbiorcy
description: W tym temacie opisano sposób tworzenia domyślnego odbiorcy używanego podczas tworzenia kanału w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ecdf4e5618d3397527bf83977857fbe3f8dbb265
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799186"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="73b97-103">Tworzenie domyślnego odbiorcy</span><span class="sxs-lookup"><span data-stu-id="73b97-103">Create a default customer</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="73b97-104">W tym temacie opisano sposób tworzenia domyślnego odbiorcy używanego podczas tworzenia kanału w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="73b97-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="73b97-105">Podczas tworzenia kanału lub online konieczne jest podanie odbiorcy domyślnego.</span><span class="sxs-lookup"><span data-stu-id="73b97-105">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="73b97-106">Domyślny odbiorca można łatwo utworzyć po uprzednim utworzeniu grupy odbiorców i książki adresowej klienta.</span><span class="sxs-lookup"><span data-stu-id="73b97-106">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="73b97-107">Tworzenie grupy odbiorców</span><span class="sxs-lookup"><span data-stu-id="73b97-107">Create a customer group</span></span>

<span data-ttu-id="73b97-108">Jeśli nie istnieją jeszcze grupy odbiorców, można ją utworzyć.</span><span class="sxs-lookup"><span data-stu-id="73b97-108">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="73b97-109">Przykładami mogą być grupy odpowiadające różnym grupom odbiorców, takim jak hurtownie, handel detaliczny, Internet, pracownicy itd.</span><span class="sxs-lookup"><span data-stu-id="73b97-109">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="73b97-110">Aby utworzyć grupę odbiorców, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="73b97-110">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="73b97-111">W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Pracownicy etatpwi \> Grupy uprawnień**.</span><span class="sxs-lookup"><span data-stu-id="73b97-111">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="73b97-112">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="73b97-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="73b97-113">W okienku **Grupa odbiorców** wprowadź identyfikator grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="73b97-113">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="73b97-114">W razie potrzeby w polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="73b97-114">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="73b97-115">W razie potrzeby w polu **Warunki płatności** wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="73b97-115">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="73b97-116">W polu **czas między datą płatności faktury i datą** płatności wprowadź odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="73b97-116">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="73b97-117">W polu **Domyślna grupa podatków** wprowadź grupę podatków, jeśli ma ona być stosowana.</span><span class="sxs-lookup"><span data-stu-id="73b97-117">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="73b97-118">To pole wyboru **Ceny zawierają podatek**, jeśli ma być stosowane.</span><span class="sxs-lookup"><span data-stu-id="73b97-118">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="73b97-119">W polu **Domyślna przyczyna odpisu** wprowadź odpowiednią wartość, jeśli ma zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="73b97-119">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="73b97-120">Poniższy obraz pokazuje kilku skonfigurowanych grup odbiorców.</span><span class="sxs-lookup"><span data-stu-id="73b97-120">The following image shows several configured customer groups.</span></span>

![Grupy odbiorców](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="73b97-122">Tworzenie książki adresowej odbiorców</span><span class="sxs-lookup"><span data-stu-id="73b97-122">Create a customer address book</span></span>

<span data-ttu-id="73b97-123">Odbiorca musi być skojarzony z książką adresową.</span><span class="sxs-lookup"><span data-stu-id="73b97-123">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="73b97-124">Jeśli jeszcze nie została utworzona, należy ją utworzyć.</span><span class="sxs-lookup"><span data-stu-id="73b97-124">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="73b97-125">Aby utworzyć książkę adresową odbiorcy należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="73b97-125">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="73b97-126">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Książki adresowe**.</span><span class="sxs-lookup"><span data-stu-id="73b97-126">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="73b97-127">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="73b97-127">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="73b97-128">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="73b97-128">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="73b97-129">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="73b97-129">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="73b97-130">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="73b97-130">On the action pane, select **Save**.</span></span>

<span data-ttu-id="73b97-131">Poniższy obraz przedstawia przykład książki adresowej.</span><span class="sxs-lookup"><span data-stu-id="73b97-131">The following image shows an example address book.</span></span>

![Książka adresowa](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="73b97-133">Tworzenie domyślnego odbiorcy</span><span class="sxs-lookup"><span data-stu-id="73b97-133">Create a default customer</span></span>

<span data-ttu-id="73b97-134">Aby utworzyć domyślnego odbiorcę, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="73b97-134">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="73b97-135">W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Pracownicy etatpwi \> Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="73b97-135">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="73b97-136">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="73b97-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="73b97-137">Z listy rozwijanej **Typ** wybierz „Osoba”.</span><span class="sxs-lookup"><span data-stu-id="73b97-137">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="73b97-138">Z listy rozwijanej **Konto odbiorcy** wybierz lub wprowadź numer konta (na przykład „100001”).</span><span class="sxs-lookup"><span data-stu-id="73b97-138">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="73b97-139">Z listy rozwijanej **Imię** wybierz lub wprowadź nazwę (na przykład „domyślna”).</span><span class="sxs-lookup"><span data-stu-id="73b97-139">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="73b97-140">Z listy rozwijanej **Drugie imię** wybierz lub wprowadź nazwę (na przykład „Retail”).</span><span class="sxs-lookup"><span data-stu-id="73b97-140">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="73b97-141">Z listy rozwijanej **Nazwisko** wybierz lub wprowadź nazwę (na przykład „Odbiorca”).</span><span class="sxs-lookup"><span data-stu-id="73b97-141">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="73b97-142">Z listy rozwijanej **Waluta** wybierz lub wprowadź walutę (na przykład „USD”).</span><span class="sxs-lookup"><span data-stu-id="73b97-142">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="73b97-143">Z listy rozwijanej **Waluta** Wybierz utworzoną wcześniej grupę odbiorców.</span><span class="sxs-lookup"><span data-stu-id="73b97-143">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="73b97-144">Z listy rozwijanej **Książki adresowe** wybierz istniejącą książkę adresową klienta.</span><span class="sxs-lookup"><span data-stu-id="73b97-144">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="73b97-145">Wybierz opcję **Zapisz**, aby zapisać i powrócić do ekranu szczegółów odbiorcy dla nowego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="73b97-145">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="73b97-146">Nie trzeba dodawać adresu dla domyślnego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="73b97-146">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="73b97-147">Poniższy obraz przedstawia przykład tworzenia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="73b97-147">The following image shows an example of customer creation.</span></span>

![Domyślne tworzenie odbiorcy](media/default-customer-creation.png)

<span data-ttu-id="73b97-149">Poniższy rysunek przedstawia domyślną konfigurację klienta.</span><span class="sxs-lookup"><span data-stu-id="73b97-149">The following image shows a default customer configuration.</span></span>

![Konfiguracja przykładowa odbiorcy](media/default-customer-configuration1.png)

<span data-ttu-id="73b97-151">Większość wartości domyślnych na ekranie szczegóły odbiorcy może pozostać, ale dwie wartości powinny zostać zmienione.</span><span class="sxs-lookup"><span data-stu-id="73b97-151">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="73b97-152">Na ekranie szczegóły odbiorcy rozwiń węzeł **Ustawienia domyślne zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="73b97-152">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="73b97-153">Z listy rozwijanej **Witryna** wybierz lub wprowadź wstępnie skonfigurowany oddział.</span><span class="sxs-lookup"><span data-stu-id="73b97-153">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="73b97-154">Z listy rozwijanej **Magazyn** wybierz lub wprowadź wstępnie skonfigurowany magazyn.</span><span class="sxs-lookup"><span data-stu-id="73b97-154">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="73b97-155">Poniższy obraz przedstawia przykład konfiguracji tworzenia odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="73b97-155">The following image shows an example customer configuration.</span></span>

![Przykład konfiguracji odbiorcy](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="73b97-157">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="73b97-157">Additional resources</span></span>

[<span data-ttu-id="73b97-158">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="73b97-158">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="73b97-159">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="73b97-159">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
