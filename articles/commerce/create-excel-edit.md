---
title: Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych
description: W tym temacie opisano sposób tworzenia skoroszytu programu Excel w celu umożliwienia edycji transakcji detalicznych w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: a2d41dd0470a4abae1a8238be8f1549fb094a026
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795746"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="a3b6d-103">Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych</span><span class="sxs-lookup"><span data-stu-id="a3b6d-103">Create an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3b6d-104">W tym temacie opisano sposób tworzenia skoroszytu programu Excel w celu umożliwienia edycji transakcji detalicznych w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-104">This topic describes how to create an Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a3b6d-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a3b6d-105">Overview</span></span>

<span data-ttu-id="a3b6d-106">Dostępny jest wstępnie zdefiniowany szablon programu Excel, do którego odbiorcy mogą uzyskiwać dostęp z różnych części systemu i którego mogą używać do edytowania transakcji sprzedaży detalicznej i przeprowadzania ich inspekcji.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-106">There is a predefined Excel template that customers can access from different parts of the system and use to edit and audit retail transactions.</span></span> <span data-ttu-id="a3b6d-107">Odbiorcy mogą również utworzyć niestandardowy skoroszyt programu Excel, którego będzie można użyć we wspomnianych celach.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-107">However, customers can also create a custom Excel workbook for this purpose.</span></span>

## <a name="create-and-configure-an-excel-workbook"></a><span data-ttu-id="a3b6d-108">Tworzenie i konfigurowanie skoroszytu programu Excel</span><span class="sxs-lookup"><span data-stu-id="a3b6d-108">Create and configure an Excel workbook</span></span>

<span data-ttu-id="a3b6d-109">Aby utworzyć i skonfigurować skoroszyt programu Excel, by móc edytować transakcje sprzedaży detalicznej, wykonaj kroki opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-109">To create and configure an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="a3b6d-110">Otwórz program Excel i utwórz pusty skoroszyt.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-110">Open Excel, and create a blank workbook.</span></span>
1. <span data-ttu-id="a3b6d-111">Na karcie **Wstawianie** wybierz pozycję **Moje dodatki**.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-111">On the **Insert** tab, select **My add-ins**.</span></span>
1. <span data-ttu-id="a3b6d-112">W prawym okienku wybierz łącze **Dodaj informacje dotyczące serwera**.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-112">In the right pane, select the **Add server information** link.</span></span>
1. <span data-ttu-id="a3b6d-113">Wprowadź adres URL serwera, a następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-113">Enter the server URL, and then select **OK**.</span></span>
1. <span data-ttu-id="a3b6d-114">Jeśli zostanie wyświetlony komunikat o błędzie „Nie znaleziono rejestracji apletów”, w celu rozwiązania problemu należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a3b6d-114">If you receive a "No applet registrations found" error message, follow these steps to resolve the issue:</span></span>

    1. <span data-ttu-id="a3b6d-115">W rozwiązaniu Commerce wybierz kolejno opcje **Administrowanie systemem \> Konfiguracja \> Parametry aplikacji pakietu Office**.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-115">In Commerce, go to **System administration \> Setup \> Office app parameters**.</span></span>
    1. <span data-ttu-id="a3b6d-116">Na skróconej karcie **Parametry aplikacji** wybierz opcję **Zainicjuj parametry aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-116">On the **App parameters** FastTab, select **Initialize app parameters**.</span></span>
    1. <span data-ttu-id="a3b6d-117">W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-117">In the confirmation message box, select **OK**.</span></span>
    1. <span data-ttu-id="a3b6d-118">Na skróconej karcie **Zarejestrowane aplety** wybierz opcję **Zainicjuj rejestrację apletu**.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-118">On the **Registered applets** FastTab, select **Initialize applet registration**.</span></span>
    1. <span data-ttu-id="a3b6d-119">W razie potrzeby powtórz trzy poprzednie kroki.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-119">Repeat the previous three steps as required.</span></span>

1. <span data-ttu-id="a3b6d-120">Wybierz opcję **Projekt**, a następnie wybierz opcję **Dodaj tabelę**.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-120">Select **Design**, and then select **Add table**.</span></span>
1. <span data-ttu-id="a3b6d-121">W zależności od danych, które mają zostać zmodyfikowane, należy wybrać jednostki, które muszą zostać dodane do skoroszytu programu Excel na potrzeby edycji.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-121">Based on the data that has to be modified, select the entities that must be added to the Excel workbook for editing.</span></span> <span data-ttu-id="a3b6d-122">Dla ułatwienia można skorzystać z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-122">Use the following table as a reference.</span></span>

    | <span data-ttu-id="a3b6d-123">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="a3b6d-123">Transaction type</span></span> | <span data-ttu-id="a3b6d-124">Jednostki danych, których należy użyć</span><span class="sxs-lookup"><span data-stu-id="a3b6d-124">Data entities to use</span></span> |
    |------------------|----------------------|
    | <span data-ttu-id="a3b6d-125">Transakcje kasowe i przeniesienia, zamówienia online, asynchroniczne zamówienia odbiorcy, asynchroniczne zapytania ofertowe odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a3b6d-125">Cash and carry transactions, Online orders, Async customer orders, Async customer quotes</span></span> | <span data-ttu-id="a3b6d-126">Transakcja (podlegająca inspekcji), transakcja sprzedaży (podlegająca inspekcji), transakcje płatności (podlegające inspekcji), transakcje podatku (podlegające inspekcji), transakcje rabatu (podlegające inspekcji), transakcje opłat (podlegające inspekcji)</span><span class="sxs-lookup"><span data-stu-id="a3b6d-126">Transaction (auditable), Sales transaction (auditable), Payment transactions (auditable), Tax transactions (auditable), Discount transactions (auditable), Charge transactions (auditable)</span></span> |
    | <span data-ttu-id="a3b6d-127">Przekazanie pieniędzy do banku</span><span class="sxs-lookup"><span data-stu-id="a3b6d-127">Bank drop</span></span> | <span data-ttu-id="a3b6d-128">Transakcja (podlegająca inspekcji), transakcje wpłat bankowych (podlegające inspekcji)</span><span class="sxs-lookup"><span data-stu-id="a3b6d-128">Transaction (auditable), Banked tender transactions (auditable)</span></span> |
    | <span data-ttu-id="a3b6d-129">Przekazanie pieniędzy do sejfu</span><span class="sxs-lookup"><span data-stu-id="a3b6d-129">Safe drop</span></span> | <span data-ttu-id="a3b6d-130">Transakcja (podlegająca inspekcji), transakcje wpływające na kwotę w kasecie kasowej (podlegające inspekcji)</span><span class="sxs-lookup"><span data-stu-id="a3b6d-130">Transaction (auditable), Safe tender transactions (auditable)</span></span> |
    | <span data-ttu-id="a3b6d-131">Deklaracja środków płatniczych</span><span class="sxs-lookup"><span data-stu-id="a3b6d-131">Tender declaration</span></span> | <span data-ttu-id="a3b6d-132">Transakcja (podlegająca inspekcji), transakcje deklaracji środków płatniczych (podlegające inspekcji)</span><span class="sxs-lookup"><span data-stu-id="a3b6d-132">Transaction (auditable), Tender declaration transactions (auditable)</span></span> |
    | <span data-ttu-id="a3b6d-133">Przychód, wydatek</span><span class="sxs-lookup"><span data-stu-id="a3b6d-133">Income, Expense</span></span> | <span data-ttu-id="a3b6d-134">Transakcja (podlegająca inspekcji), transakcje przychodów/wydatków (podlegające inspekcji), transakcje płatności (podlegające inspekcji)</span><span class="sxs-lookup"><span data-stu-id="a3b6d-134">Transaction (auditable), Income/Expense transactions (auditable), Payment transactions (auditable)</span></span> |
    | <span data-ttu-id="a3b6d-135">Deklaracja kwoty początkowej, pobranie środków płatniczych, przyjęcie do kasy, reszta dla metody płatności, płatność faktury, kaucja odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a3b6d-135">Declare starting amount, Tender removal, Float entry, Change tender, Invoice payment, Customer deposit</span></span> | <span data-ttu-id="a3b6d-136">Transakcja (podlegająca inspekcji), transakcje płatności (podlegające inspekcji)</span><span class="sxs-lookup"><span data-stu-id="a3b6d-136">Transaction (auditable), Payment transactions (auditable)</span></span> |

    > [!NOTE]
    > <span data-ttu-id="a3b6d-137">Ważne jest, aby do każdego skoroszytu programu Excel dodać tylko jedną jednostkę danych.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-137">It's important that you add only one data entity to each Excel workbook.</span></span> <span data-ttu-id="a3b6d-138">Ponadto wszystkie pola oznaczone symbolem klucza muszą zostać dodane do odpowiedniego skoroszytu.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-138">Additionally, all fields that are marked by a key symbol must be added to the relevant workbook.</span></span>

1. <span data-ttu-id="a3b6d-139">Po skonfigurowaniu skoroszytu zastosuj wymagane filtry.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-139">After the workbook is configured, apply the required filters.</span></span> <span data-ttu-id="a3b6d-140">Należy pamiętać o zastosowaniu tych samych filtrów do wszystkich arkuszy w pliku.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-140">Be sure to apply the same filters to all the worksheets in the file.</span></span> <span data-ttu-id="a3b6d-141">Należy unikać ładowania bardzo dużych ilości danych do pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-141">Avoid loading very large amounts of data into the Excel file.</span></span> <span data-ttu-id="a3b6d-142">Mogłoby to negatywnie wpłynąć na wydajność oraz spowolnić działanie programu Excel i systemu.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-142">Otherwise, performance might be affected, and Excel and your system might slow down.</span></span> <span data-ttu-id="a3b6d-143">Zaleca się, aby w pliku były zawsze stosowane filtry „Firma” oraz „Numer zestawienia” lub „Numer transakcji”.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-143">We recommend that you always use "Company" and either "Statement Number" or "Transaction Number" as filters for your file.</span></span>
1. <span data-ttu-id="a3b6d-144">Po skonfigurowaniu filtrów wybierz opcję **Odśwież**, aby załadować dane.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-144">After the filters are configured, select **Refresh** to load the data.</span></span>
1. <span data-ttu-id="a3b6d-145">Edytuj wymagane dane, a następnie opublikuj je.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-145">Edit the required data, and then publish it.</span></span> <span data-ttu-id="a3b6d-146">Jeśli przycisk **Publikuj** jest niedostępny, oznacza to, że niektóre pola kluczy prawdopodobnie nie zostały dodane do skoroszytu programu Excel.</span><span class="sxs-lookup"><span data-stu-id="a3b6d-146">If the **Publish** button is unavailable, some key fields probably weren't added to the Excel workbook.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3b6d-147">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a3b6d-147">Additional resources</span></span>

[<span data-ttu-id="a3b6d-148">Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką</span><span class="sxs-lookup"><span data-stu-id="a3b6d-148">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="a3b6d-149">Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a3b6d-149">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="a3b6d-150">Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="a3b6d-150">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="a3b6d-151">Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych</span><span class="sxs-lookup"><span data-stu-id="a3b6d-151">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]