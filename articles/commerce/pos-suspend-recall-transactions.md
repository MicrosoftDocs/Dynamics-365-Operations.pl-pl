---
title: Wstrzymywanie i wznawianie transakcji w punkcie sprzedaży (POS)
description: W tym temacie opisano, jak użytkownicy mogą zawiesić transakcje w trakcie wykonywania i następnie wznowić je później lub na innej kasie przy użyciu Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f513e2d857908f2b95d27bf48ff1e826724d7cbf
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415025"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a><span data-ttu-id="623ba-103">Wstrzymywanie i wznawianie transakcji w punkcie sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="623ba-103">Suspend and resume a transaction in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="623ba-104">Użytkownicy w punkcie sprzedaży (POS) mogą zawieszać transakcje w trakcie wykonywania, a następnie wznawiać je później lub na innej kasie.</span><span class="sxs-lookup"><span data-stu-id="623ba-104">Point of sale (POS) users can suspend in-progress transactions, and then resume them later or on a different register.</span></span> <span data-ttu-id="623ba-105">Transakcje są często wstrzymane w celu szybkiego zwolnienia kasy do innego zadania bez utraty postępu w bieżącej transakcji.</span><span class="sxs-lookup"><span data-stu-id="623ba-105">Transactions are often suspended to quickly free up a register for a different task without losing any progress on the current transaction.</span></span> <span data-ttu-id="623ba-106">Na przykład pracownik sklepu rozpoczyna przetwarzanie transakcji klienta na urządzeniu przenośnym, ale musi ją zakończyć na urządzeniu z szufladą kasową.</span><span class="sxs-lookup"><span data-stu-id="623ba-106">For example, a store associate starts to process a customer's transaction on a mobile device but must complete it on a register that has a cash drawer.</span></span> <span data-ttu-id="623ba-107">W takim przypadku pracownik sklepu może zawiesić transakcję na urządzeniu przenośnym i następnie przywołać ją i wznowić na kasie.</span><span class="sxs-lookup"><span data-stu-id="623ba-107">In this case, the store associate can suspend the transaction on the mobile device, and then recall and resume it on a register.</span></span>

## <a name="configure-suspend-and-resume-functionality"></a><span data-ttu-id="623ba-108">Konfigurowanie funkcji wstrzymywania i wznawiania</span><span class="sxs-lookup"><span data-stu-id="623ba-108">Configure suspend and resume functionality</span></span>

### <a name="pos-operations"></a><span data-ttu-id="623ba-109">Operacje aplikacji POS</span><span class="sxs-lookup"><span data-stu-id="623ba-109">POS operations</span></span>

<span data-ttu-id="623ba-110">Dwie [operacje POS](pos-operations.md) obsługują w POS scenariusze wstrzymywania i wznawiania.</span><span class="sxs-lookup"><span data-stu-id="623ba-110">Two [POS operations](pos-operations.md) let the POS support suspend and resume scenarios.</span></span> <span data-ttu-id="623ba-111">Można przypisać te operacje do [siatki przycisków](pos-screen-layouts.md) na stronie transakcji lub powitalnej.</span><span class="sxs-lookup"><span data-stu-id="623ba-111">You can assign these operations to [button grids](pos-screen-layouts.md) on the transaction page or the welcome page.</span></span>

- <span data-ttu-id="623ba-112">503: Zawieś transakcję</span><span class="sxs-lookup"><span data-stu-id="623ba-112">503: Suspend transaction</span></span>
- <span data-ttu-id="623ba-113">504: Wznów transakcję</span><span class="sxs-lookup"><span data-stu-id="623ba-113">504: Recall transaction</span></span>

### <a name="receipt-template"></a><span data-ttu-id="623ba-114">Szablon paragonu</span><span class="sxs-lookup"><span data-stu-id="623ba-114">Receipt template</span></span>

<span data-ttu-id="623ba-115">Punktu sprzedaży można skonfigurować do generowania drukowanego dokumentu, gdy transakcja została zawieszona.</span><span class="sxs-lookup"><span data-stu-id="623ba-115">The POS can be configured to generate a printed slip when a transaction is suspended.</span></span> <span data-ttu-id="623ba-116">Następnie można szybko użyć tego dokumentu do zidentyfikowania i przywołania transakcji później.</span><span class="sxs-lookup"><span data-stu-id="623ba-116">That slip can then be used to quickly identify and recall the transaction later.</span></span>

<span data-ttu-id="623ba-117">Aby umożliwić drukowanie dokumentu w punkcie sprzedaży, należy dodać format paragonu **Zawieszona transakcja** do profilu paragonów w sklepie.</span><span class="sxs-lookup"><span data-stu-id="623ba-117">To enable the POS to print a slip, you must add the **Suspended transaction** receipt format to the store's receipt profile.</span></span> <span data-ttu-id="623ba-118">Można zaprojektować format paragonu, aby zawierał lub ignorował konkretne informacje na temat transakcji.</span><span class="sxs-lookup"><span data-stu-id="623ba-118">You can design the receipt format so that it includes or excludes specific details about the transaction.</span></span> <span data-ttu-id="623ba-119">Na przykład format może zawierać kod kreskowy obsługujący skanowanie.</span><span class="sxs-lookup"><span data-stu-id="623ba-119">For example, the format can include a barcode to support scanning.</span></span>

### <a name="receipt-numbering"></a><span data-ttu-id="623ba-120">Numeracja paragonów</span><span class="sxs-lookup"><span data-stu-id="623ba-120">Receipt numbering</span></span>

<span data-ttu-id="623ba-121">Tak jak w przypadku innych typów transakcji w punkcie sprzedaży, które generują drukowane pokwitowanie, można zdefiniować sekwencję dla zawieszonych transakcji w sekcji **Numerowanie paragonów** sekcji profilu funkcji sklepu.</span><span class="sxs-lookup"><span data-stu-id="623ba-121">As for other POS transaction types that generate a printed receipt, you can define a number sequence for suspended transactions in the **Receipt numbering** section of the store's functionality profile.</span></span>

### <a name="void-when-closing-shift"></a><span data-ttu-id="623ba-122">Unieważnij podczas zamykania zmiany</span><span class="sxs-lookup"><span data-stu-id="623ba-122">Void when closing shift</span></span>

<span data-ttu-id="623ba-123">Można użyć opcji **Unieważnij podczas zamykania zmiany**, aby wymagać od użytkowników ukończenia lub unieważnienia podejrzanych transakcji przed zamknięciem zmiany.</span><span class="sxs-lookup"><span data-stu-id="623ba-123">You can use the **Void when closing shift** option to require that users either complete or void any suspended transactions before they close their shift.</span></span> <span data-ttu-id="623ba-124">Podczas operacji **Zamknij zmianę** punkt sprzedaży będzie monitował użytkowników o wyświetlanie lub unieważnienie wszelkich zaległych zawieszonych transakcji.</span><span class="sxs-lookup"><span data-stu-id="623ba-124">During the **Close shift** operation, the POS will prompt users to either view or void any outstanding suspended transactions.</span></span>

## <a name="suspend-and-resume-a-transaction"></a><span data-ttu-id="623ba-125">Zawieszanie i wznawianie transakcji</span><span class="sxs-lookup"><span data-stu-id="623ba-125">Suspend and resume a transaction</span></span>

### <a name="suspend-a-transaction"></a><span data-ttu-id="623ba-126">Zawieszanie transakcji</span><span class="sxs-lookup"><span data-stu-id="623ba-126">Suspend a transaction</span></span>

<span data-ttu-id="623ba-127">Użytkownicy, którzy mają wystarczające uprawnienia i mają układ ekranu zawierający operację **Zawieś transakcję**, mogą zawiesić transakcję, dzięki czemu można ją wywołać później lub na innej kasie.</span><span class="sxs-lookup"><span data-stu-id="623ba-127">Users who have sufficient privileges, and who have a screen layout that includes the **Suspend transaction** operation, can suspend a transaction so that it can be recalled later or on a different register.</span></span>

<span data-ttu-id="623ba-128">Transakcje mogą być zawieszane, tylko jeśli **nie** zawierają następujących wierszy:</span><span class="sxs-lookup"><span data-stu-id="623ba-128">Transactions can be suspended only if they do **not** contain the following types of lines:</span></span>

- <span data-ttu-id="623ba-129">Aktywne wiersze płatności</span><span class="sxs-lookup"><span data-stu-id="623ba-129">Active payment lines</span></span>
- <span data-ttu-id="623ba-130">Wiersze kart upominkowych (do wystawienia karty upominkowej lub dodania salda na karcie upominkowej)</span><span class="sxs-lookup"><span data-stu-id="623ba-130">Gift card lines (either to issue a gift card or to add to the gift card balance)</span></span>

<span data-ttu-id="623ba-131">Wstrzymana transakcja nie ma wpływu na informacje o sprzedaży ani dostępność zapasów w sklepie.</span><span class="sxs-lookup"><span data-stu-id="623ba-131">A suspended transaction doesn't affect sales information or inventory availability information for the store.</span></span>

### <a name="resume-a-suspended-transaction"></a><span data-ttu-id="623ba-132">Usuwanie wstrzymanej transakcję</span><span class="sxs-lookup"><span data-stu-id="623ba-132">Resume a suspended transaction</span></span>

<span data-ttu-id="623ba-133">Zawieszone transakcje mogą być wywoływane i wznawiane w tym samym sklepie przez dowolnego użytkownika, który ma wystarczające uprawnienia, i który ma układ zawierający operację **Wywołaj transakcję**.</span><span class="sxs-lookup"><span data-stu-id="623ba-133">Suspended transactions can be recalled and resumed in the same store by any user who has sufficient privileges, and who also has a layout that includes the **Recall transaction** operation.</span></span>

<span data-ttu-id="623ba-134">Aby szybko i łatwo wznowić zawieszoną transakcję, zeskanuj kod kreskowy na wydrukowanym dokumencie podczas przeglądania listy transakcji z operacji **Wywołaj transakcję**.</span><span class="sxs-lookup"><span data-stu-id="623ba-134">To quickly and easily recall a suspended transaction, scan the barcode on the printed slip while you're viewing the list of transactions from the **Recall transaction** operation.</span></span>

### <a name="considerations-for-offline-mode"></a><span data-ttu-id="623ba-135">Uwagi dotyczące trybu offline</span><span class="sxs-lookup"><span data-stu-id="623ba-135">Considerations for offline mode</span></span>

- <span data-ttu-id="623ba-136">Transakcji zawieszonych w punkcie sprzedaży w trybie online nie można wznowić w trybie offline, ponieważ dane nie są synchronizowane z bazą danych offline.</span><span class="sxs-lookup"><span data-stu-id="623ba-136">Any transaction that is suspended while the POS is in online mode can't be resumed in offline mode, because the data isn't synced to the offline database.</span></span>
- <span data-ttu-id="623ba-137">Jeśli transakcja została zawieszona gdy punkt sprzedaży działał w trybie offline, można ją wznowić w trybie offline, pod warunkiem że punkt sprzedaży nie został przełączony do trybu online od czasu zawieszenia transakcji.</span><span class="sxs-lookup"><span data-stu-id="623ba-137">If you suspend a transaction while the POS is in offline mode, you can recall it in offline mode, provided that the POS wasn't switched back to online mode at any time since you suspended the transaction.</span></span> <span data-ttu-id="623ba-138">Kiedy punkt sprzedaży zostanie przełączony do trybu online, dane dotyczące zawieszonych transakcjach są przenoszone do bazy danych online i usuwane z bazy danych offline.</span><span class="sxs-lookup"><span data-stu-id="623ba-138">When the POS is switched back to online mode, data about suspended transactions is moved to the online database and removed from the offline database.</span></span> <span data-ttu-id="623ba-139">W związku z tym transakcje można wznowić tylko w trybie online.</span><span class="sxs-lookup"><span data-stu-id="623ba-139">Therefore, the transactions can be resumed only in online mode.</span></span> <span data-ttu-id="623ba-140">Jeśli punkt sprzedaży zostanie przełączony z powrotem do trybu offline, nie będzie można wznowić tej zawieszonej transakcji, ponieważ została już usunięta z bazy danych offline.</span><span class="sxs-lookup"><span data-stu-id="623ba-140">If you switch the POS back to offline mode, you won't be able to resume those suspended transaction, because they have already been removed from the offline database.</span></span>

### <a name="void-a-suspended-transaction"></a><span data-ttu-id="623ba-141">Unieważnienie zawieszonej transakcji</span><span class="sxs-lookup"><span data-stu-id="623ba-141">Void a suspended transaction</span></span>

<span data-ttu-id="623ba-142">Można unieważnić zawieszone transakcje przez ich wywołanie a następnie wykonanie operacji **Unieważnij transakcję** lub przez wybranie transakcji z listy **Wycofaj transakcję** i wybranie opcji **Unieważnij** na pasku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="623ba-142">You can void suspended transactions either by recalling the transaction and then performing the **Void transaction** operation, or by selecting the transaction in the **Recall transaction** list and selecting **Void** on the app bar.</span></span> <span data-ttu-id="623ba-143">Ewentualnie można skonfigurować sklepu do wyświetlania użytkownikom monitów o unieważnienie zawieszonych transakcji w chwili kończenia zmiany.</span><span class="sxs-lookup"><span data-stu-id="623ba-143">Alternatively, the store can be configured to prompt users to void suspended transactions when they close their shift.</span></span>
