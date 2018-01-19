---
title: Konfiguracja i autoryzacja karty kredytowej
description: "Ten artykuł zawiera omówienie funkcji autoryzacji kart kredytowych w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Znajdują się tu informacje o konfigurowaniu usługi płatności, dodawaniu karty kredytowej do zamówienia sprzedaży oraz o unieważnianiu autoryzacji."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, Retail
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: ff5dc8b1704b88534b199c2e9e68fbccb23bf15b
ms.contentlocale: pl-pl
ms.lasthandoff: 01/19/2018

---

# <a name="credit-card-setup-authorization-and-capture"></a><span data-ttu-id="27d4a-104">Konfiguracja i autoryzacja karty kredytowej</span><span class="sxs-lookup"><span data-stu-id="27d4a-104">Credit card setup, authorization, and capture</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="27d4a-105">Ten artykuł zawiera omówienie funkcji autoryzacji kart kredytowych w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="27d4a-105">This article provides an overview of credit card authorization in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="27d4a-106">Znajdują się tu informacje o konfigurowaniu usługi płatności, dodawaniu karty kredytowej do zamówienia sprzedaży oraz o unieważnianiu autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="27d4a-106">It includes information about how to set up a payment service, add a credit card to a sales order, and void an authorization.</span></span>

<a name="setting-up-the-credit-card-payment-service"></a><span data-ttu-id="27d4a-107">Konfigurowanie usługi płatności kartą kredytową</span><span class="sxs-lookup"><span data-stu-id="27d4a-107">Setting up the credit card payment service</span></span>
------------------------------------------

<span data-ttu-id="27d4a-108">Aby skonfigurować karty kredytowe, należy ustawić i aktywować usługę płatności na stronie Usługi płatności.</span><span class="sxs-lookup"><span data-stu-id="27d4a-108">To use credit cards, you must set up and activate a payment service on the Payment services page.</span></span> <span data-ttu-id="27d4a-109">Usługa płatności pełni rolę pomostu między firmą i bankiem, który przetwarza opłaty kartą kredytową odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="27d4a-109">A payment service acts as a bridge between your legal entity and the bank that processes a customer's credit card charges.</span></span> <span data-ttu-id="27d4a-110">Należy skontaktować się z wystawcą karty kredytowej wymienionym w polu Łącznik płatności i skonfigurować konto u tego wystawcy.</span><span class="sxs-lookup"><span data-stu-id="27d4a-110">You must work with a credit card provider that is listed in the Payment connector field and set up an account with that provider.</span></span> <span data-ttu-id="27d4a-111">Następnie trzeba ustawić inne opcje na stronie Usługi płatności, ustawić typy kart kredytowych American Express, Discover, MasterCard na stronie Typy kart kredytowych i aktywować wystawcę jako domyślnego.</span><span class="sxs-lookup"><span data-stu-id="27d4a-111">You must then set up the other options on the Payment services page, set up credit card types for American Express, Discover, MasterCard, and Discover on the Credit card types page, and activate the provider as the default provider.</span></span> <span data-ttu-id="27d4a-112">Trzeba też wykonać następujące kroki, by ukończyć konfigurację:</span><span class="sxs-lookup"><span data-stu-id="27d4a-112">You must also follow these steps to complete your setup:</span></span>
-   <span data-ttu-id="27d4a-113">Na stronie Parametry rozrachunków z odbiorcami należy określić parametry korzystania z autoryzacji karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="27d4a-113">On the Accounts receivable parameters page, specify parameters for using credit card authorizations.</span></span>
-   <span data-ttu-id="27d4a-114">Na stronie Warunki płatności należy ustawić wartości płatności dla kart kredytowych.</span><span class="sxs-lookup"><span data-stu-id="27d4a-114">On the Terms of payment page, set up payment terms for credit cards.</span></span> <span data-ttu-id="27d4a-115">W polu Typ płatności należy wybrać opcję Karta kredytowa.</span><span class="sxs-lookup"><span data-stu-id="27d4a-115">In the Payment type field, select Credit card.</span></span>
-   <span data-ttu-id="27d4a-116">Na stronie Karty kredytowe klienta należy wpisać dane karty kredytowej dla klientów.</span><span class="sxs-lookup"><span data-stu-id="27d4a-116">On the Customer credit cards page, enter credit card information for customers.</span></span>

## <a name="adding-a-new-credit-card"></a><span data-ttu-id="27d4a-117">Dodawanie nowej karty kredytowej</span><span class="sxs-lookup"><span data-stu-id="27d4a-117">Adding a new credit card</span></span>
<span data-ttu-id="27d4a-118">Można tworzyć nowe rekordy kart kredytowych na stronie Odbiorcy, używając opcji Odbiorca, Ustawienia, Karta kredytowa.</span><span class="sxs-lookup"><span data-stu-id="27d4a-118">You can create new credit card records on the Customers page by using Customer, Set up, Credit card.</span></span> <span data-ttu-id="27d4a-119">Można też tworzyć rekordy kart kredytowych podczas wprowadzania zamówień sprzedaży na stronie Zamówienie sprzedaży, używają opcji Zarządzaj, Odbiorca, Karta kredytowa, Rejestr.</span><span class="sxs-lookup"><span data-stu-id="27d4a-119">You can also create credit card records when you enter sales orders on the Sales order page, by using Manage, Customer, Credit card, Register.</span></span>
<span data-ttu-id="27d4a-120">Dodawanie karty kredytowej dla zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="27d4a-120">Adding a credit card to a sales order</span></span>
-------------------------------------

<span data-ttu-id="27d4a-121">Można dodać kartę kredytową do zamówienia sprzedaży , wybierając kartę kredytową w sekcji wyszukiwania kart kredytowych na skróconej karcie Cena i rabaty na stronie Zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="27d4a-121">You can add a credit card to a sales order by selecting a credit card in the credit card lookup on the Price and discounts FastTab on the Sales order page.</span></span> <span data-ttu-id="27d4a-122">Aby rozpocząć proces autoryzacji w okienku akcji na karcie Zarządzanie wybierz opcję Karta kredytowa i Autoryzuj.</span><span class="sxs-lookup"><span data-stu-id="27d4a-122">To start the authorization process, on the Action Pane, on the Manage tab, select Credit card and Authorize.</span></span>
<span data-ttu-id="27d4a-123">Autoryzacja karty kredytowej</span><span class="sxs-lookup"><span data-stu-id="27d4a-123">Authorizing a credit card</span></span>
-------------------------

<span data-ttu-id="27d4a-124">Autoryzacja karty kredytowej polega na zweryfikowaniu numeru karty i tożsamości jej posiadacza oraz potwierdzeniu dostępnego salda kredytu.</span><span class="sxs-lookup"><span data-stu-id="27d4a-124">When a credit card is authorized, the card number and cardholder's name are verified, and the available credit balance is confirmed.</span></span> <span data-ttu-id="27d4a-125">Opcjonalnie weryfikowane są wartość weryfikacji karty i adres posiadacza karty.</span><span class="sxs-lookup"><span data-stu-id="27d4a-125">Optionally, the card verification value and the cardholder’s address are verified.</span></span> <span data-ttu-id="27d4a-126">Dostępne saldo kredytu odbiorcy jest następnie zmniejszane o kwotę faktury.</span><span class="sxs-lookup"><span data-stu-id="27d4a-126">The customer's available credit balance is then reduced by the amount of the invoice.</span></span> <span data-ttu-id="27d4a-127">Usługa płatności wysyła informację, czy karta kredytowa została przyjęta, czy odrzucona.</span><span class="sxs-lookup"><span data-stu-id="27d4a-127">The payment service sends information that the credit card has been approved or declined.</span></span> <span data-ttu-id="27d4a-128">Podczas fakturowania zamówienia sprzedaży karta kredytowa jest obciążana (autoryzowana) kwotą faktury.</span><span class="sxs-lookup"><span data-stu-id="27d4a-128">When the sales order is invoiced, the credit card is charged (captured) for the invoice amount.</span></span>

### <a name="card-verification-value"></a><span data-ttu-id="27d4a-129">Wartość weryfikacji karty</span><span class="sxs-lookup"><span data-stu-id="27d4a-129">Card verification value</span></span>

<span data-ttu-id="27d4a-130">Można wymagać wartości weryfikacji karty, która jest czasem określana jako kod bezpieczeństwa na karcie.</span><span class="sxs-lookup"><span data-stu-id="27d4a-130">You can require the card verification value, which is sometimes referred to as the card's security code.</span></span> <span data-ttu-id="27d4a-131">Na kartach American Express jest to kod czterocyfrowy.</span><span class="sxs-lookup"><span data-stu-id="27d4a-131">For American Express, this is a four-digit value.</span></span> <span data-ttu-id="27d4a-132">Na kartach Discover, MasterCard i Visa są to trzy cyfry.</span><span class="sxs-lookup"><span data-stu-id="27d4a-132">For Discover, MasterCard, and Visa, it is a three-digit value.</span></span>

### <a name="address-verification"></a><span data-ttu-id="27d4a-133">Weryfikacja adresu</span><span class="sxs-lookup"><span data-stu-id="27d4a-133">Address verification</span></span>

<span data-ttu-id="27d4a-134">Informacje weryfikacji adresu są zawsze wysyłane do dostawcy płatności.</span><span class="sxs-lookup"><span data-stu-id="27d4a-134">Address verification information is always sent to the payment provider.</span></span> <span data-ttu-id="27d4a-135">Można określić, ile informacji jest wymaganych do zaakceptowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="27d4a-135">You can decide how much information is required for a transaction to be accepted.</span></span> <span data-ttu-id="27d4a-136">Należy skontaktować się z dostawcą, aby określić, czy może on akceptować te informacje.</span><span class="sxs-lookup"><span data-stu-id="27d4a-136">Be sure to check with your provider to determine whether it accepts this information.</span></span> <span data-ttu-id="27d4a-137">Oto opcje weryfikacji adresu:</span><span class="sxs-lookup"><span data-stu-id="27d4a-137">Here are the options for address verification:</span></span>
-   <span data-ttu-id="27d4a-138">**Zawsze akceptuj transakcję** — akceptuj transakcję, niezależnie od wyników weryfikacji adresu.</span><span class="sxs-lookup"><span data-stu-id="27d4a-138">**Always accept transaction** – Accept the transaction, regardless of address verification results.</span></span>
-   <span data-ttu-id="27d4a-139">**Posiadacz konta** — porównanie imienia i nazwiska z transakcji z informacjami od wystawcy karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="27d4a-139">**Account holder** – Compare the cardholder's name from the transaction with the credit card company’s information.</span></span>
-   <span data-ttu-id="27d4a-140">**Adres na fakturze** — porównanie imienia i nazwiska i adresu rozliczeniowego z transakcji z informacjami od wystawcy karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="27d4a-140">**Billing address** – Compare the cardholder's name and billing address from the transaction with the credit card company’s information.</span></span>
-   <span data-ttu-id="27d4a-141">**Kod pocztowy do faktury** — porównanie imienia i nazwiska, adresu rozliczeniowego i kodu pocztowego z transakcji z informacjami od wystawcy karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="27d4a-141">**Billing postal code** – Compare the cardholder's name, billing address, and postal code from the transaction with the credit card company’s information.</span></span>

## <a name="data-support"></a><span data-ttu-id="27d4a-142">Obsługa danych</span><span class="sxs-lookup"><span data-stu-id="27d4a-142">Data support</span></span>
<span data-ttu-id="27d4a-143">Dla każdego typu karty kredytowej, który jest obsługiwany, można określić poziom obsługi danych.</span><span class="sxs-lookup"><span data-stu-id="27d4a-143">For each credit card type that is supported, you can specify the level of data support.</span></span> <span data-ttu-id="27d4a-144">Poziom określa ilość informacji dotyczących transakcji, jaka jest przesyłana do usługi płatności.</span><span class="sxs-lookup"><span data-stu-id="27d4a-144">The level controls how much information about a transaction is transferred to the payment service.</span></span> <span data-ttu-id="27d4a-145">Należy skontaktować się z dostawcą, aby określić, czy ma on te informacje.</span><span class="sxs-lookup"><span data-stu-id="27d4a-145">Be sure to check with your provider to determine whether it can provide this information.</span></span> <span data-ttu-id="27d4a-146">Poniżej przedstawiono opcje poziom obsługi danych:</span><span class="sxs-lookup"><span data-stu-id="27d4a-146">Here are the options for the level of data support:</span></span>
-   <span data-ttu-id="27d4a-147">**Poziom 1** — przesłanie danych transakcji, kwoty transakcji i opisu.</span><span class="sxs-lookup"><span data-stu-id="27d4a-147">**Level 1** – Transfer the transaction date, transaction amount, and description.</span></span>
-   <span data-ttu-id="27d4a-148">**Poziom 2** — przesłanie informacje poziomu 1 plus adresy wysyłki i handlowca oraz informacji podatkowych.</span><span class="sxs-lookup"><span data-stu-id="27d4a-148">**Level 2** – Transfer all Level 1 information, plus the shipping and merchant addresses, and tax information.</span></span>
-   <span data-ttu-id="27d4a-149">**Poziom 3** — przesłanie informacji poziomu 2 plus informacji w wierszu zamówienia.</span><span class="sxs-lookup"><span data-stu-id="27d4a-149">**Level 3** – Transfer all Level 2 information, plus order line information.</span></span>

## <a name="partial-payments"></a><span data-ttu-id="27d4a-150">Płatności częściowe</span><span class="sxs-lookup"><span data-stu-id="27d4a-150">Partial payments</span></span>
<span data-ttu-id="27d4a-151">Jeśli wysyłasz części zamówienia, kwota częściowego zamówienia jest rejestrowana, a autoryzacja będącą kwotą całego zamówienia jest zamykana.</span><span class="sxs-lookup"><span data-stu-id="27d4a-151">If you ship part of an order, the amount of the partial order is captured, and the authorization, which was for the amount of the whole order, is closed.</span></span> <span data-ttu-id="27d4a-152">Nowa autoryzacja jest następnie przesyłana na pozostałą kwotę zamówienia, która nie została jeszcze wysłana.</span><span class="sxs-lookup"><span data-stu-id="27d4a-152">A new authorization is then submitted for the remaining amount of the order that hasn't been shipped.</span></span>

## <a name="voiding-an-authorization"></a><span data-ttu-id="27d4a-153">Unieważnianie autoryzacji </span><span class="sxs-lookup"><span data-stu-id="27d4a-153">Voiding an authorization</span></span>
<span data-ttu-id="27d4a-154">Abu unieważnić autoryzację karty kredytowej, można zmienić metodę płatności na inną, która nie ma typu karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="27d4a-154">To void a credit card authorization, you can change the method of payment to another method that doesn't have a type of Credit card.</span></span>






