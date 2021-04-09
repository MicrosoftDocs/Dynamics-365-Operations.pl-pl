---
title: Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy
description: W tym temacie opisano sposób edytowania i przeprowadzania inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy w rozwiązaniu Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 5113f7ac0d308076ebaa9daeca0929eb537e94ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792688"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a><span data-ttu-id="9823e-103">Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9823e-103">Edit and audit online order and asynchronous customer order transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9823e-104">W tym temacie opisano sposób edytowania i przeprowadzania inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9823e-104">This topic describes how to edit and audit online order and asynchronous customer order transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9823e-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="9823e-105">Overview</span></span>

<span data-ttu-id="9823e-106">Między wersjami 10.0.5 i 10.0.6 rozwiązania Commerce dodano do niego obsługę edycji transakcji kasowych i przeniesienia (takich jak sprzedaż i zwroty) oraz transakcji zarządzania gotówką (takich jak przyjęcie do kasy i pobranie środków płatniczych).</span><span class="sxs-lookup"><span data-stu-id="9823e-106">Between Commerce versions 10.0.5 and 10.0.6, support was added for editing cash and carry transactions (such as sales and returns) and cash management transactions (such as float entry and tender removal).</span></span> <span data-ttu-id="9823e-107">W wersji 10.0.7 rozwiązania Commerce dodano obsługę edycji transakcji zamówień online i asynchronicznych transakcji zamówienia odbiorców.</span><span class="sxs-lookup"><span data-stu-id="9823e-107">In Commerce version 10.0.7, support was added for editing online order transactions and asynchronous customer order transactions.</span></span>

## <a name="edit-and-audit-order-transactions"></a><span data-ttu-id="9823e-108">Edycja i przeprowadzanie inspekcji transakcji zamówień</span><span class="sxs-lookup"><span data-stu-id="9823e-108">Edit and audit order transactions</span></span>

<span data-ttu-id="9823e-109">Aby edytować transakcje zamówień i przeprowadzać ich inspekcję w centrali Commerce, wykonaj kroki opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="9823e-109">To edit and audit order transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9823e-110">Zainstaluj [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span><span class="sxs-lookup"><span data-stu-id="9823e-110">Install the [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span></span>
1. <span data-ttu-id="9823e-111">Na skróconej karcie **Zamówienie** na karcie **Zamówienia odbiorcy** na stronie **Parametry sieci sprzedaży** określ kod wstrzymania dla opcji **Kod wstrzymania dla błędów synchronizacji zamówień**.</span><span class="sxs-lookup"><span data-stu-id="9823e-111">On the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, specify a hold code for **Hold code for order synchronization errors**.</span></span>
1. <span data-ttu-id="9823e-112">Otwórz obszar roboczy **Finanse sklepu**.</span><span class="sxs-lookup"><span data-stu-id="9823e-112">Open the **Store financials** workspace.</span></span> <span data-ttu-id="9823e-113">Kafelki **Błędy synchronizacji zamówień online** i **Błędy synchronizacji zamówień odbiorcy** oferują wstępnie przefiltrowany widok strony transakcji sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="9823e-113">The **Online order synchronization errors** and **Customer order synchronization errors** tiles provide a prefiltered view of the retail transaction page.</span></span> <span data-ttu-id="9823e-114">W każdym z tych widoków można sprawdzić rekordy transakcji, których weryfikacja się nie powiodła, dla odpowiedniego typu zamówień.</span><span class="sxs-lookup"><span data-stu-id="9823e-114">Each shows the transaction records that have failed synchronization for the corresponding order type.</span></span>
1. <span data-ttu-id="9823e-115">Otwórz stronę **Błędy synchronizacji zamówień online** lub **Błędy synchronizacji zamówień odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="9823e-115">Open either the **Online order synchronization errors** page or the **Customer order synchronization errors** page.</span></span> <span data-ttu-id="9823e-116">Wybierz rekord, aby wyświetlić szczegóły błędu synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="9823e-116">Select a record to view the synchronization error details.</span></span> <span data-ttu-id="9823e-117">Na skróconej karcie **Stan synchronizacji** są widoczne następujące szczegóły błędu:</span><span class="sxs-lookup"><span data-stu-id="9823e-117">The **Synchronization status** FastTab provides the following error details:</span></span>

    - <span data-ttu-id="9823e-118">Stan zamówienia oczekującego</span><span class="sxs-lookup"><span data-stu-id="9823e-118">Pending order status</span></span>
    - <span data-ttu-id="9823e-119">Szczegóły błędu zamówienia</span><span class="sxs-lookup"><span data-stu-id="9823e-119">Order error details</span></span>
    - <span data-ttu-id="9823e-120">Data i godzina modyfikacji</span><span class="sxs-lookup"><span data-stu-id="9823e-120">Modified date and time</span></span>
    - <span data-ttu-id="9823e-121">Liczba ponownych prób</span><span class="sxs-lookup"><span data-stu-id="9823e-121">Retry count</span></span>

1. <span data-ttu-id="9823e-122">Jeśli szczegóły błędu wskazują na konieczność naprawienia rekordu, wybierz pozycję **Dodatek pakietu Office**, a następnie wybierz pozycję **Edytuj wybraną transakcję**.</span><span class="sxs-lookup"><span data-stu-id="9823e-122">If the error details indicate that the record must be fixed, select **Office Add in**, and then select **Edit selected transaction**.</span></span> <span data-ttu-id="9823e-123">Zostanie otwarty plik programu Excel ze szczegółowymi informacjami dotyczącymi wybranej transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-123">An Excel file that shows the details of the selected transaction is opened.</span></span>

    - <span data-ttu-id="9823e-124">Jeśli edytowana transakcja to transakcja zamówienia online, plik programu Excel będzie zawierać następujące arkusze:</span><span class="sxs-lookup"><span data-stu-id="9823e-124">If the transaction that is being edited is an online order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="9823e-125">**Transakcja** — ten arkusz zawiera szczegóły nagłówka dotyczące transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-125">**Transaction** – This worksheet has the header details for the transaction.</span></span>
        - <span data-ttu-id="9823e-126">**Transakcja sprzedaży** — ten arkusz zawiera szczegóły wiersza dotyczące transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-126">**Sales transaction** – This worksheet has the line details for the transaction.</span></span>
        - <span data-ttu-id="9823e-127">**Transakcje płatności** — ten arkusz zawiera wiersze szczegółów płatności dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-127">**Payment transactions** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="9823e-128">**Transakcje rabatu** — ten arkusz zawiera szczegóły dotyczące rabatów dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-128">**Discount transactions** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="9823e-129">**Transakcje podatku** — ten arkusz zawiera szczegóły dotyczące podatku dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-129">**Tax transactions** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="9823e-130">**Transakcje opłat** — ten arkusz zawiera dane dotyczące opłat dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-130">**Charges transactions** – This worksheet has the charges-related data for the transaction.</span></span>

    - <span data-ttu-id="9823e-131">Jeśli edytowana transakcja to transakcja asynchronicznego zamówienia odbiorcy, plik programu Excel będzie zawierać następujące arkusze:</span><span class="sxs-lookup"><span data-stu-id="9823e-131">If the transaction that is being edited is an asynchronous customer order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="9823e-132">**Wiersze** — ten arkusz zawiera szczegóły nagłówka i wiersza dotyczące transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-132">**Lines** – This worksheet has the header and line details for the transaction.</span></span>
        - <span data-ttu-id="9823e-133">**Płatności** — ten arkusz zawiera wiersze szczegółów płatności dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-133">**Payments** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="9823e-134">**Rabaty** — ten arkusz zawiera szczegóły dotyczące rabatów dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-134">**Discounts** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="9823e-135">**Podatki** — ten arkusz zawiera szczegóły dotyczące podatków dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-135">**Taxes** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="9823e-136">**Opłaty** — ten arkusz zawiera dane dotyczące opłat dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-136">**Charges** – This worksheet has the charges-related data for the transaction.</span></span>

1. <span data-ttu-id="9823e-137">W polu **Stan zamówienia oczekującego** w pliku programu Excel wprowadź wartość **Edycja**, a następnie opublikuj zmianę.</span><span class="sxs-lookup"><span data-stu-id="9823e-137">In the Excel file, in the **Pending order status** field, enter **Editing**, and then publish the change.</span></span> <span data-ttu-id="9823e-138">Dzięki temu podczas przetwarzania w czasie wykonywania zadania **Synchronizacja zamówienia** uruchamianego w trybie wsadowym ten rekord nie zostanie pominięty.</span><span class="sxs-lookup"><span data-stu-id="9823e-138">In this way, you prevent the **Synchronize order** job that is running in batch mode from skipping this record during processing.</span></span>
1. <span data-ttu-id="9823e-139">W pliku programu Excel możesz zmodyfikować odpowiednie pola, a następnie przekazać dane z powrotem do centrali Commerce, korzystając z funkcji publikowania aplikacji dodatkowej Dynamics Excel.</span><span class="sxs-lookup"><span data-stu-id="9823e-139">In the Excel file, modify the appropriate fields, and then upload the data back into Commerce headquarters by using the publishing functionality of the Dynamics Excel Add-in.</span></span> <span data-ttu-id="9823e-140">Po opublikowaniu danych zmiany staną się widoczne w systemie.</span><span class="sxs-lookup"><span data-stu-id="9823e-140">After the data is published, the changes will be reflected in the system.</span></span> <span data-ttu-id="9823e-141">W trakcie publikacji nie jest przeprowadzana weryfikacja zmian wprowadzonych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9823e-141">During publication, no validation is done for changes that users make.</span></span>
1. <span data-ttu-id="9823e-142">Pełen dziennik inspekcji zmian można wyświetlić, wybierając opcję **Wyświetl dziennik inspekcji** na nagłówku **Transakcja sprzedaży detalicznej** dla zmian na poziomie nagłówka i w odpowiednim obszarze i rekordzie na stosownej stronie transakcji.</span><span class="sxs-lookup"><span data-stu-id="9823e-142">You can view a complete audit trail of the changes by selecting **View audit trail** in the **Retail transaction** header for the header-level changes, and in the relevant section and record on the appropriate transaction page.</span></span> <span data-ttu-id="9823e-143">Na przykład wszystkie zmiany związane z wierszami sprzedaży będą wyświetlane na stronie **Transakcje sprzedaży**, a wszystkie zmiany związane z płatnościami będą wyświetlane na stronie **Transakcje płatności**.</span><span class="sxs-lookup"><span data-stu-id="9823e-143">For example, all changes that are related to sales lines will be shown on the **Sales transactions** page, and all changes that are related to payments will be shown on the **Payment transactions** page.</span></span> <span data-ttu-id="9823e-144">Dla zmian są obsługiwane następujące szczegóły inspekcji:</span><span class="sxs-lookup"><span data-stu-id="9823e-144">The following audit details are maintained for the changes:</span></span>

    - <span data-ttu-id="9823e-145">Data i godzina modyfikacji</span><span class="sxs-lookup"><span data-stu-id="9823e-145">Modified date and time</span></span>
    - <span data-ttu-id="9823e-146">Pole</span><span class="sxs-lookup"><span data-stu-id="9823e-146">Field</span></span>
    - <span data-ttu-id="9823e-147">Stara wartość</span><span class="sxs-lookup"><span data-stu-id="9823e-147">Old value</span></span>
    - <span data-ttu-id="9823e-148">Nowa wartość</span><span class="sxs-lookup"><span data-stu-id="9823e-148">New value</span></span>
    - <span data-ttu-id="9823e-149">Zmodyfikowane przez</span><span class="sxs-lookup"><span data-stu-id="9823e-149">Modified by</span></span>

1. <span data-ttu-id="9823e-150">Po dokonaniu i opublikowaniu zmian wybierz pozycję **Synchronizacja zamówienia**, aby natychmiast rozpocząć proces synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="9823e-150">After you've made and published your changes, select **Synchronize order** to immediately start the synchronization process.</span></span> <span data-ttu-id="9823e-151">Możesz również poczekać na przetworzenie transakcji w ramach procesu synchronizacji uruchomionego w trybie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="9823e-151">Alternatively, you can wait for the synchronization process that is running in batch mode to process the transaction.</span></span>

<span data-ttu-id="9823e-152">Pomyślnie zsynchronizowane zamówienia zostają domyślnie wstrzymane w oparciu o kod wstrzymania zdefiniowany w parametrach rozwiązania Commerce.</span><span class="sxs-lookup"><span data-stu-id="9823e-152">By default, after the orders are successfully synced, they are put in a hold status, based on the hold code that is defined in the Commerce parameters.</span></span> <span data-ttu-id="9823e-153">Wstrzymanie zleceń musi zostać usunięte, zanim zamówienia będą mogły zostać przekazane do dalszego przetworzenia w celu umożliwienia realizacji zamówień lub wykonania innych operacji.</span><span class="sxs-lookup"><span data-stu-id="9823e-153">The hold on the orders must be removed before the orders can be processed further for fulfillment or other operations.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9823e-154">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9823e-154">Additional resources</span></span>

[<span data-ttu-id="9823e-155">Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką</span><span class="sxs-lookup"><span data-stu-id="9823e-155">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="9823e-156">Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="9823e-156">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="9823e-157">Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych</span><span class="sxs-lookup"><span data-stu-id="9823e-157">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="9823e-158">Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych</span><span class="sxs-lookup"><span data-stu-id="9823e-158">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]