---
title: Zarządzanie gotówką podręczną w aplikacji Retail dla Europy Wschodniej
description: W tym temacie opisano sposób konfigurowania i używania funkcji zarządzania środkami pieniężnymi w aplikacji Retail dla Europy Wschodniej.
author: epopov
manager: annbe
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: c198cedba9268229dc1057711d9f16ca33acebac
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371462"
---
# <a name="petty-cash-management-for-retail-for-eastern-europe"></a><span data-ttu-id="9cf69-103">Zarządzanie gotówką podręczną w aplikacji Retail dla Europy Wschodniej</span><span class="sxs-lookup"><span data-stu-id="9cf69-103">Petty cash management for Retail for Eastern Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9cf69-104">Ten artykuł zawiera informacje dotyczące lokalizacji dla Europy Wschodniej i specyficznej dla branży handlu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="9cf69-104">This article contains information about Eastern European localization specific for the Retail industry.</span></span> 

<span data-ttu-id="9cf69-105">Zgodnie z wymaganiami dotyczącymi księgowania w krajach Europy Wschodniej operacje kont kasowych można skonfigurować do automatycznego przetwarzania paragonów, dokumentów kasowych i raportów kasowych.</span><span class="sxs-lookup"><span data-stu-id="9cf69-105">In accordance with the Eastern Europe accounting requirements, you can set up operations for cash accounts to automate the processes for receipts, cash documents and cash reports.</span></span> <span data-ttu-id="9cf69-106">Aby uzyskać więcej informacji, zobacz [(EEUR) Konfigurowanie parametrów zarządzania gotówką](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/eeur-set-up-parameters-for-cash-management).</span><span class="sxs-lookup"><span data-stu-id="9cf69-106">For more information, go to [(EEUR) Set up parameters for cash management](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/eeur-set-up-parameters-for-cash-management).</span></span> 

<span data-ttu-id="9cf69-107">Sprzadawcy detaliczni mogą akceptować różne typy płatności w zamian za produkty i usługi, które sprzedają.</span><span class="sxs-lookup"><span data-stu-id="9cf69-107">Retailers can accept various types of payment in exchange for the products and services that they sell.</span></span> <span data-ttu-id="9cf69-108">Jakkolwiek środki pieniężne to najczęściej używana forma płatności, sprzedawcy detaliczni mogą również pobierać płatności w formie czeków, kart lub załączników.</span><span class="sxs-lookup"><span data-stu-id="9cf69-108">Although cash is the most common form of payment, retailers can also receive payment in the form of checks, cards, or vouchers.</span></span> <span data-ttu-id="9cf69-109">W punkcie sprzedaży detalicznej, kasa przetwarza gotówkę, paragony z kart kredytowych i inne płatności.</span><span class="sxs-lookup"><span data-stu-id="9cf69-109">In Retail point of sale (POS), cash, credit card receipts, and other payments are processed through a cash office.</span></span>

<span data-ttu-id="9cf69-110">Przy użyciu zarządzania środkami pieniężnymi w aplikacji Retail można wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="9cf69-110">You can do the following by using Cash management in Retail:</span></span>

- <span data-ttu-id="9cf69-111">Utwórz konto środków pieniężnych dla metody płatności wybranej dla każdego sklepu sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf69-111">Create a cash account for the selected payment method for each retail store.</span></span>
- <span data-ttu-id="9cf69-112">Umożliwia korzystanie z arkuszy kasowych w celu księgowania transakcji kasowych i płatności odbiorcy , które są przyjmowane w punkcie sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="9cf69-112">Use cash journals to post cash transactions and customer payments that are received at a retail POS.</span></span>
- <span data-ttu-id="9cf69-113">Agregowanie transakcji w wierszu zestawienia podczas księgowania zestawienia sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf69-113">Aggregate transactions in a statement line when you post a retail statement.</span></span> <span data-ttu-id="9cf69-114">Można agregować przekazywanie pieniędzy do sejfu i banku, transakcje na załącznikach, transakcje usunięcia środków płatniczych, transakcje deklaracji przyjęcia do kasy, transakcje przychodów, transakcje wydatków, płatności odbiorcy, transakcje sprzedaży i transakcji zwrotu.</span><span class="sxs-lookup"><span data-stu-id="9cf69-114">You can aggregate safe drops, bank drops, voucher transactions, remove tender transactions, float entry transactions, income transactions, expense transactions, customer payments, sales transactions, and return transactions.</span></span>

<span data-ttu-id="9cf69-115">Wszystkie transakcje, które miały miejsce w module punktu sprzedaży detalicznej Retail POS, są księgowane w arkuszu księgi.</span><span class="sxs-lookup"><span data-stu-id="9cf69-115">All transactions that take place in Retail POS are posted using a ledger journal.</span></span> <span data-ttu-id="9cf69-116">Arkusze płatności gotówkowych, arkusze płatności odbiorcy i arkusze finansowe służą do tworzenia i księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="9cf69-116">You can use cash payment journals, customer payment journals, and general journals to create and post the statements.</span></span> <span data-ttu-id="9cf69-117">Aby uzyskać więcej informacji, zobacz [Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/tasks/create-calculate-post-statement-retail-store).</span><span class="sxs-lookup"><span data-stu-id="9cf69-117">For more information, go to [Create, calculate, and post statements for a retail store](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/tasks/create-calculate-post-statement-retail-store).</span></span>

<span data-ttu-id="9cf69-118">Na stronie **Zaksięgowane zestawienia** w okienku akcji można wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="9cf69-118">On the **Posted statements** page, on the Action Pane, you can do the following:</span></span>
  - <span data-ttu-id="9cf69-119">Wybierz kolejno opcje **Informacje > Arkusz płatności gotówką**, aby uzyskać dostęp do arkuszy płatności gotówkowych powiązanych z zestawieniem.</span><span class="sxs-lookup"><span data-stu-id="9cf69-119">Go to **Inquiries > Cash payment journal** to access the cash payment journals that are related to the statement.</span></span>
  - <span data-ttu-id="9cf69-120">Wybierz kolejno opcje **Informacje > Arkusz finansowy** , aby uzyskać dostęp do arkuszy księgi związanych z zestawieniami innych niż płatności odbiorcy i płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="9cf69-120">Go to **Inquiries > General journal** to access the ledger journals that are related to the statement, other than customer payments and cash payments.</span></span>

## <a name="set-up-for-cash-management-for-retail-pos"></a><span data-ttu-id="9cf69-121">Konfiguracja zarządzania gotówką dla programu Retail POS</span><span class="sxs-lookup"><span data-stu-id="9cf69-121">Set up for cash management for Retail POS</span></span>

<span data-ttu-id="9cf69-122">Przed użyciem zarządzania gotówką w programie Retail, należy wykonać poniższą procedurę konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="9cf69-122">You must complete the following setup procedure before you use cash management in Retail:</span></span>
- <span data-ttu-id="9cf69-123">Na stronie **Metody płatności** skonfiguruj metody płatności dla każdego typu płatności akceptowanego przez sprzedawcę detalicznego.</span><span class="sxs-lookup"><span data-stu-id="9cf69-123">Set up a payment method for each payment type that the retailer accepts on the **Payment methods** page.</span></span> <span data-ttu-id="9cf69-124">Można używać różnych metod płatności do księgowania transakcji w aplikacji Retail POS.</span><span class="sxs-lookup"><span data-stu-id="9cf69-124">You can use different payment methods for posting transactions in Retail POS.</span></span> <span data-ttu-id="9cf69-125">Aby uzyskać więcej informacji o metodach płatności w aplikacji Retail, zobacz [Metody płatności](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/payment-methods).</span><span class="sxs-lookup"><span data-stu-id="9cf69-125">For more information about payment methods in Retail, see [Payment methods](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/payment-methods).</span></span>

- <span data-ttu-id="9cf69-126">Skonfiguruj parametry sprzedaży detalicznej dla operacji gotówkowych.</span><span class="sxs-lookup"><span data-stu-id="9cf69-126">Set up retail parameters for cash operations.</span></span>

- <span data-ttu-id="9cf69-127">Ustaw metodę płatności dla płatności gotówką w sklepie sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf69-127">Set up a payment method for cash payments in a retail store.</span></span>

### <a name="set-up-retail-parameters-for-cash-operations"></a><span data-ttu-id="9cf69-128">Konfigurowanie parametrów sprzedaży detalicznej dla operacji gotówkowych</span><span class="sxs-lookup"><span data-stu-id="9cf69-128">Set up retail parameters for cash operations</span></span>

<span data-ttu-id="9cf69-129">Można skonfigurować parametry, aby utworzyć i zaksięgować transakcje gotówkowe w sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf69-129">You can set up parameters to create and post cash transactions in Retail.</span></span> <span data-ttu-id="9cf69-130">W aplikacji Retail POS można używać arkuszy płatności gotówkowych, arkuszy płatności odbiorcy lub arkuszy finansowych do księgowania transakcji sprzedaży i płatności.</span><span class="sxs-lookup"><span data-stu-id="9cf69-130">You can use cash payment journals, customer payment journals, or general journals to post sales transactions and payment transactions in the Retail POS.</span></span> <span data-ttu-id="9cf69-131">Można zagregować transakcje, które mają te same właściwości, podczas księgowania zestawienia.</span><span class="sxs-lookup"><span data-stu-id="9cf69-131">You can aggregate transactions that have the same properties when you post a statement.</span></span> 

1. <span data-ttu-id="9cf69-132">Kliknij kolejno opcje **Handel detaliczny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="9cf69-132">Go to **Retail > Headquarters setup > Parameters > Retail parameters**.</span></span> <span data-ttu-id="9cf69-133">W lewym okienku kliknij opcję **Księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="9cf69-133">In the left pane, click **Posting**</span></span>

2. <span data-ttu-id="9cf69-134">W obszarze **Księgowanie** na skróconej karcie **Agregacja** w opcji **Usunięcie/zmiana środków płatniczych** ustaw wartość **Tak**, aby agregować transakcje usunięcia lub przyjęcia środków płatniczych, które są skojarzone z wierszem zestawienia podczas księgowania zestawienia.</span><span class="sxs-lookup"><span data-stu-id="9cf69-134">In the **Posting** area, on the **Aggregation** FastTab, set **Tender remove/float** to **Yes** to aggregate the remove tender transactions or float entry transactions that are associated with a statement line when you post the statement.</span></span> <span data-ttu-id="9cf69-135">Transakcja usunięcia środków płatniczych jest tworzona podczas wypłaty gotówki z szuflady kasowej w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf69-135">A remove tender transaction is created when you withdraw cash from the POS cash drawer.</span></span> <span data-ttu-id="9cf69-136">Transakcja przyjęcia środków płatniczych jest tworzona podczas wpłaty gotówki do szuflady kasowej w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf69-136">A float entry transaction is created when you deposit cash in the POS cash drawer.</span></span>

3. <span data-ttu-id="9cf69-137">Aktywuj poszczególne parametry wymienione poniżej, aby agregować transakcje, które są skojarzone z wierszem zestawienia podczas księgowania zestawienia:</span><span class="sxs-lookup"><span data-stu-id="9cf69-137">Activate the individual parameters listed below to aggregate the transactions that are associated with a statement line when you post the statement:</span></span>
   - <span data-ttu-id="9cf69-138">**Przekazanie pieniędzy do banku** — Agregowanie transakcji bankowych.</span><span class="sxs-lookup"><span data-stu-id="9cf69-138">**Bank drop** – Aggregate bank transactions.</span></span>
   - <span data-ttu-id="9cf69-139">**Przekazanie do sejfu** — Agregowanie transakcji przekazania do sejfu.</span><span class="sxs-lookup"><span data-stu-id="9cf69-139">**Safe drop** – Aggregate safe transactions.</span></span>
   - <span data-ttu-id="9cf69-140">**Transakcje przychodów/wydatków** — Agregowanie transakcji wpływu/wpłaty lub wypływu/wypłaty.</span><span class="sxs-lookup"><span data-stu-id="9cf69-140">**Income/Expense transactions** – Aggregate income transactions or expense transactions.</span></span>
   - <span data-ttu-id="9cf69-141">**Transakcje na załączniku** — Agregowanie transakcji w załączniku.</span><span class="sxs-lookup"><span data-stu-id="9cf69-141">**Voucher transactions** – Aggregate voucher transactions.</span></span>
   - <span data-ttu-id="9cf69-142">**Płatności odbiorcy** — Agregowanie płatności od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="9cf69-142">**Customer payments** – Aggregate customer payments.</span></span>
   - <span data-ttu-id="9cf69-143">**Sprzedaż i zwroty** — Agregowanie transakcji sprzedaży i zwrotu.</span><span class="sxs-lookup"><span data-stu-id="9cf69-143">**Sales and returns** – Aggregate sales and returns transactions.</span></span>

4. <span data-ttu-id="9cf69-144">Na skróconej karcie **Płatności** wybierz domyślną nazwę arkusza dla następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="9cf69-144">On the **Payments** FastTab, select a default journal name for the following options:</span></span>
     - <span data-ttu-id="9cf69-145">**Arkusz płatności odbiorcy** — Ten arkusz jest używany do księgowania płatności od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="9cf69-145">**Customer payment journal** – This journal is used to post customer payments.</span></span>
     - <span data-ttu-id="9cf69-146">**Arkusz płatności gotówką** — Ten arkusz jest używany do księgowania płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="9cf69-146">**Cash payment journal** – This journal is used to post cash payments.</span></span>
     - <span data-ttu-id="9cf69-147">**Arkusz finansowy** — Ten arkusz jest używany do księgowania transakcji innych niż płatności gotówkowe i płatności od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="9cf69-147">**General journal** – This journal is used to post transactions other than cash payments and customer payments.</span></span>

### <a name="set-up-a-payment-method-for-cash-payments-in-a-retail-store"></a><span data-ttu-id="9cf69-148">Konfigurowanie metody płatności dla płatności gotówką w sklepie sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9cf69-148">Set up a payment method for cash payments in a retail store</span></span>

<span data-ttu-id="9cf69-149">Poniższa procedura umożliwia konfigurowanie metody płatności dla płatności gotówką w sklepie sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9cf69-149">Use the following procedure to set up a payment method for cash payments in a retail store.</span></span>

1. <span data-ttu-id="9cf69-150">Wybierz kolejno opcje **Handel detaliczny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="9cf69-150">Go to **Retail > Channels > Retail stores > All retail stores**.</span></span>

2. <span data-ttu-id="9cf69-151">Na stronie listy **Wszystkie sklepy sieci sprzedaży** wybierz sklep, dla którego chcesz skonfigurować metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="9cf69-151">On the **All retail stores** list page, select the store to set up a payment method for.</span></span>

3. <span data-ttu-id="9cf69-152">W okienku akcji na karcie **Konfiguracja** w grupie **Konfiguracja** kliknij opcję **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="9cf69-152">On the Action Pane, on the **Set up** tab, in the **Set up** group, click **Payment methods**.</span></span>

4. <span data-ttu-id="9cf69-153">Na stronie **Metody płatności** utwórz lub wybierz metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="9cf69-153">On the **Payment method** page, create or select a payment method.</span></span> 

5. <span data-ttu-id="9cf69-154">Na skróconej karcie **Księgowanie** w grupie pól **Konto** w polu **Typ konta** zaznacz opcję **Konto kasowe**.</span><span class="sxs-lookup"><span data-stu-id="9cf69-154">On the **Posting** FastTab, in the **Account** field group, in the **Account type** field, select **Cash account**.</span></span>

   > [!NOTE]
    > <span data-ttu-id="9cf69-155">Opcję **Konto kasowe** w polu **Typ konta** można wybrać tylko po zaznaczeniu opcji **Normalnie** lub **Usunięcie/zmiana środków płatniczych** w polu **Funkcja**.</span><span class="sxs-lookup"><span data-stu-id="9cf69-155">You can select **Cash account** in the **Account type** field only if you select **Normal** or **Tender remove/float** in the **Function** field.</span></span>

6. <span data-ttu-id="9cf69-156">W polu **Numer konta** wybierz numer konta kasowego dla metody płatności.</span><span class="sxs-lookup"><span data-stu-id="9cf69-156">In the **Account number** field, select a cash account number for the payment method.</span></span>

7. <span data-ttu-id="9cf69-157">W grupie pól **Usunięcie/zmiana środków płatniczych** w polu **Konto przeciwstawne** wybierz konto przeciwstawne do księgowania transakcji usunięcia lub deklaracji przyjęcia dla metody płatności.</span><span class="sxs-lookup"><span data-stu-id="9cf69-157">In the **Tender remove/float** field group, in the **Offset account** field, select the offset account to post remove tender or float entry transactions for the payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf69-158">Konta przeciwstawne należy skonfigurować dla obu metod płatności używanych w sklepie — wpłacania gotówki oraz usunięcia lub przyjęcia środków płatniczych.</span><span class="sxs-lookup"><span data-stu-id="9cf69-158">You must set up offset accounts for both the cash tender payment method and the remove tender or float entry payment method for a store.</span></span> <span data-ttu-id="9cf69-159">Spowoduje to utworzenie zbilansowanych zapisów księgi głównej dla transakcji usunięcia lub przyjęcia środków płatniczych.</span><span class="sxs-lookup"><span data-stu-id="9cf69-159">This creates balanced general ledger entries for remove tender or float entry transactions.</span></span>
