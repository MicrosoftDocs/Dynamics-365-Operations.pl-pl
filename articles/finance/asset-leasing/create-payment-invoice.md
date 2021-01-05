---
title: Tworzenie faktur dla płatności
description: W tym temacie opisano sposób tworzenia miesięcznych faktur za wynajem. Można tworzyć faktury za pojedyncze wynajmy lub można skorzystać z procesu przetwarzania wsadowego, aby utworzyć je dla wielu wynajmów.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 32618814d00cb1e1f1082169a64b187cce1e76b4
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446986"
---
# <a name="create-payment-invoices"></a><span data-ttu-id="66f6b-104">Tworzenie faktur dla płatności</span><span class="sxs-lookup"><span data-stu-id="66f6b-104">Create payment invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66f6b-105">Można tworzyć miesięczne faktury za pojedyncze wynajmy lub można skorzystać z procesu przetwarzania wsadowego, aby utworzyć je dla wielu wynajmów.</span><span class="sxs-lookup"><span data-stu-id="66f6b-105">You can create monthly invoices for individual leases, or you can use a batch process to create them for multiple leases.</span></span> <span data-ttu-id="66f6b-106">Poniżej przedstawiono procedurę tworzenia poszczególnych wpisów płatności za wynajem, gdy jest włączona wartość parametru **Płatność do dostawcy** na stronie **Konfigurowanie ksiąg wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="66f6b-106">The following procedure shows how to create an individual lease payment entry when the **Pay to Vendor** parameter on the **Lease book setup** page is turned on.</span></span>

1. <span data-ttu-id="66f6b-107">Na stronie **Podsumowanie wynajmu** wybierz wynajem, a następnie wybierz opcję **Ksiegi \> Harmonogram płatności**.</span><span class="sxs-lookup"><span data-stu-id="66f6b-107">On the **Lease summary** page, select a lease, and then select **Books \> Payment schedule**.</span></span>
2. <span data-ttu-id="66f6b-108">Wybierz płatność, którą należy wykonać, a następnie wybierz opcję **Utwórz arkusz**.</span><span class="sxs-lookup"><span data-stu-id="66f6b-108">Select the payment that must be made, and then select **Create journal**.</span></span> <span data-ttu-id="66f6b-109">Zostanie wyświetlony komunikat informujący o utworzeniu arkusza dla wybranej płatności.</span><span class="sxs-lookup"><span data-stu-id="66f6b-109">You receive a message that states that a journal was created against the selected payment.</span></span>
3. <span data-ttu-id="66f6b-110">Wybierz **Arkusze faktur**, a następnie wybierz fakturę, która musi zostać zapłacona.</span><span class="sxs-lookup"><span data-stu-id="66f6b-110">Select **Invoice journals**, and then select the invoice that must be paid.</span></span>
4. <span data-ttu-id="66f6b-111">Na karcie **Wiersze** przejrzyj wpis w arkuszu przed zaksięgowaniem go w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="66f6b-111">On the **Lines** tab, review the journal entry before you post it to the general ledger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="66f6b-112">Domyślnie tworzone wiersze faktury od dostawcy używają profilu księgowania dostawcy ze strony **Parametry rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="66f6b-112">By default, the vendor invoice lines that are created use the vendor posting profile from the **Accounts payable parameters** page.</span></span>

5. <span data-ttu-id="66f6b-113">Wybierz poprawny arkusz, a następnie wybierz fakturę, która musi zostać zapłacona.</span><span class="sxs-lookup"><span data-stu-id="66f6b-113">Select the correct journal, and then select the invoice that must be paid.</span></span>

    <span data-ttu-id="66f6b-114">W tym przykładzie parametr **Płatność do dostawcy** w księdze wynajmu jest włączony.</span><span class="sxs-lookup"><span data-stu-id="66f6b-114">For this example, the **Pay to Vendor** parameter on the lease book is turned on.</span></span> <span data-ttu-id="66f6b-115">Z tego względu faktura będzie znajdować się w arkuszu faktur.</span><span class="sxs-lookup"><span data-stu-id="66f6b-115">Therefore, the invoice will be in the invoice journal.</span></span> <span data-ttu-id="66f6b-116">W sekcji **Przegląd** znajduje się podsumowanie wpisu w arkuszu, a w sekcji **Wiersze** wyświetlane są szczegóły dotyczące rzeczywistych wpisów w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="66f6b-116">The **Overview** section shows a summary of the journal entry, and the **Lines** section shows details of the actual journal lines.</span></span>

    > [!NOTE]
    > <span data-ttu-id="66f6b-117">Jeśli parametr **Płatność do dostawcy** jest wyłączony, wpisy w arkuszu płatności będą wyświetlane na stronie **Wynajem składnika majątku** dla księgi wynajmu, a system utworzy wpis wynajmu składnika majątku zamiast faktury.</span><span class="sxs-lookup"><span data-stu-id="66f6b-117">If the **Pay to Vendor** parameter is turned off, payment journal entries will be listed on the **Asset leasing** page for the lease book, and the system will create an asset leasing entry instead of an invoice.</span></span> <span data-ttu-id="66f6b-118">Wpis opłaty z tytułu wynajmu zostanie zaksięgowany w nazwie arkusza określonej w polu **Arkusz wynajmu miesięcznego**.</span><span class="sxs-lookup"><span data-stu-id="66f6b-118">The lease payment entry will be posted to the journal name that is specified in the **Monthly lease journal** field.</span></span>

6. <span data-ttu-id="66f6b-119">Po zaksięgowaniu transakcji można wyświetlić informacje o transakcjach i wartości bilansowej zobowiązania z tytułu wynajmu, wybierając **Transakcje zobowiązań** w księdze wynajmu.</span><span class="sxs-lookup"><span data-stu-id="66f6b-119">After the transaction is posted, you can view the transaction information and the carrying value of the lease liability by selecting **Liability transactions** in the lease book.</span></span>

    <span data-ttu-id="66f6b-120">W harmonogramie płatności zostanie zaznaczone pole wyboru **Arkusz zaksięgowany**, a w wierszu będzie wyświetlany numer arkusza faktur.</span><span class="sxs-lookup"><span data-stu-id="66f6b-120">In the payment schedule, the **Journal posted** check box will be selected, and the line will show the invoice journal number.</span></span> <span data-ttu-id="66f6b-121">Po utworzeniu arkusza płatności i zapisu dla tego arkusza należy wycofać ten wpis, aby można było go ponownie utworzyć.</span><span class="sxs-lookup"><span data-stu-id="66f6b-121">After a payment journal and an entry for that journal have been created, you must reverse the entry before it can be re-created.</span></span>
