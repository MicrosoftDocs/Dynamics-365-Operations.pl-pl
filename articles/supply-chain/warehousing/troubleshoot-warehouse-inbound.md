---
title: Rozwiązywanie problemów dotyczących przychodzących operacji magazynowych
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z przychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6f6d689c596b4ec924cb50ec3bea8ce907e6dc6b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920994"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="ed945-103">Rozwiązywanie problemów dotyczących przychodzących operacji magazynowych</span><span class="sxs-lookup"><span data-stu-id="ed945-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed945-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z przychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ed945-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="ed945-105">Zgłaszany jest następujący komunikat o błędzie: Wygenerowano „Zlecenie kontroli jakości %1.</span><span class="sxs-lookup"><span data-stu-id="ed945-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="ed945-106">Nie można odnaleźć profilu grupy. Sprawdź konfigurację".</span><span class="sxs-lookup"><span data-stu-id="ed945-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ed945-107">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ed945-107">Issue description</span></span>

<span data-ttu-id="ed945-108">Ten komunikat o błędzie jest związany z procesem odbierania, w którym jest włączona funkcja zarządzania jakością (QMS).</span><span class="sxs-lookup"><span data-stu-id="ed945-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="ed945-109">W zależności od konfiguracji w danym środowisku dodatkowe szczegóły dotyczące transakcji, która generuje komunikat o błędzie, mogą pomóc w rozwiązaniu problemu.</span><span class="sxs-lookup"><span data-stu-id="ed945-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ed945-110">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ed945-110">Issue resolution</span></span>

<span data-ttu-id="ed945-111">Najpierw przejrzyj ustawienia [pobierania dla grupy](set-up-cluster-picking.md) i upewnij się, że profile grup są skonfigurowane poprawnie.</span><span class="sxs-lookup"><span data-stu-id="ed945-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="ed945-112">Nie można skorzystać z elementu menu urządzenia przenośnego do pobierania grup, dopóki nie zostaną skonfigurowane Profile grup.</span><span class="sxs-lookup"><span data-stu-id="ed945-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="ed945-113">W zależności od środowiska konieczne może być również przejrzenie innych pokrewnych konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="ed945-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="ed945-114">Odbieranie mieszanego numeru identyfikacyjnego nie działa dla kodu dyspozycji z wyjątkiem kredytu.</span><span class="sxs-lookup"><span data-stu-id="ed945-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="ed945-115">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ed945-115">Issue description</span></span>

<span data-ttu-id="ed945-116">Jeśli pole **Akcja** dla kodu dyspozycji ma wartość *Kredyt* lub *Odpadki*, do przetwarzania zwróconych towarów można używać tylko elementu menu [Odbieranie mieszanych numerów identyfikacyjnych](mixed-license-plate-receiving.md).</span><span class="sxs-lookup"><span data-stu-id="ed945-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ed945-117">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ed945-117">Issue resolution</span></span>

<span data-ttu-id="ed945-118">Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji.</span><span class="sxs-lookup"><span data-stu-id="ed945-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="ed945-119">Obecnie tylko [kody dyspozycji](../service-management/set-up-disposition-codes.md), w których pole **Akcja** ma wartość *Kredyt* lub *Odpadki*, są obsługiwane w przypadku otrzymywania mieszanego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="ed945-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="ed945-120">Kiedy uruchamiam zadanie okresowe Aktualizuj przyjęcia produktów, niepotwierdzone zamówienia zakupu są potwierdzane.</span><span class="sxs-lookup"><span data-stu-id="ed945-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="ed945-121">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ed945-121">Issue description</span></span>

<span data-ttu-id="ed945-122">Po uruchomieniuzadania okresowego *Aktualizowanie dokumentów przyjęcia produktów* system automatycznie potwierdza niepotwierdzone zamówienia zakupu ze stanem transakcji magazynowej *Zarejestrowane*.</span><span class="sxs-lookup"><span data-stu-id="ed945-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ed945-123">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ed945-123">Issue resolution</span></span>

<span data-ttu-id="ed945-124">Nowa funkcja obsługi ładunków przychodzących *Przekroczenie przyjmowania ilości ładunku* rozwiązuje ten problem.</span><span class="sxs-lookup"><span data-stu-id="ed945-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="ed945-125">Aby włączyć tę funkcję, przejdź do obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje (w kolejności, w jakiej są wymienione):</span><span class="sxs-lookup"><span data-stu-id="ed945-125">To turn on this feature, go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="ed945-126">Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem</span><span class="sxs-lookup"><span data-stu-id="ed945-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="ed945-127">Przyjęcie nadmiernej ilości obciążenia pracą</span><span class="sxs-lookup"><span data-stu-id="ed945-127">Over receipt of load quantities</span></span>

<span data-ttu-id="ed945-128">Aby uzyskać więcej informacji, zajrzyj do [Księguj zarejestrowane ilości produktów na podstawie zamówień zakupu](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="ed945-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a><span data-ttu-id="ed945-129">Podczas rejestrowania zamówień przychodzących wyświetlany jest następujący komunikat o błędzie: „Ilość jest nieprawidłowa”.</span><span class="sxs-lookup"><span data-stu-id="ed945-129">When I register inbound orders, I receive the following error message: "The quantity is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ed945-130">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ed945-130">Issue description</span></span>

<span data-ttu-id="ed945-131">Jeśli w polu **Zasady grupowania identyfikatorów** jest ustawiona wartość *Użytkownik zdefiniowany* dla elementu menu urządzenia przenośnego używanego do rejestrowania zamówień przychodzących, pojawia się komunikat o błędzie („Ilość jest prawidłowa”) i nie można zakończyć rejestracji.</span><span class="sxs-lookup"><span data-stu-id="ed945-131">If the **License plate grouping policy** field is set to *User defined* for a mobile device menu item that is used to register inbound orders, you receive an error message ("The quantity is not valid"), and you can't complete the registration.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="ed945-132">Przyczyna problemu</span><span class="sxs-lookup"><span data-stu-id="ed945-132">Issue cause</span></span>

<span data-ttu-id="ed945-133">Gdy *Zdefiniowana przez użytkownika* jest używana jako zasada grupowania numerów identyfikacyjnych, system rozdziela przychodzące zapasy na osobne numery identyfikacyjne, zgodnie z grupą sekwencji jednostek.</span><span class="sxs-lookup"><span data-stu-id="ed945-133">When *User defined* is used as a license plate grouping policy, the system splits the incoming inventory into separate license plates, as indicated by the unit sequence group.</span></span> <span data-ttu-id="ed945-134">Jeśli do śledzenia otrzymywanego towaru używane są numery partii lub serii, ilości każdej partii lub serii należy określić zgodnie z zarejestrowanym numerem identyfikacyjnym.</span><span class="sxs-lookup"><span data-stu-id="ed945-134">If batch or serial numbers are used to track the item that is being received, the quantities of each batch or serial must be specified per license plate that is registered.</span></span> <span data-ttu-id="ed945-135">Jeśli ilość określona dla numeru rejestracyjnego przekracza ilość, która nadal musi zostać odebrana dla bieżących wymiarów, zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ed945-135">If the quantity that is specified for a license plate exceeds the quantity that must still be received for the current dimensions, you receive the error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ed945-136">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ed945-136">Issue resolution</span></span>

<span data-ttu-id="ed945-137">Podczas rejestrowania towaru za pomocą elementu menu urządzenia przenośnego, w którym w polu **Zasady grupowania numerów identyfikacyjnych** jest ustawiona wartość *Zdefiniowana przez użytkownika*, system może wymagać potwierdzenia lub wprowadzenia numerów identyfikacyjnych, numerów partii lub numerów seryjnych.</span><span class="sxs-lookup"><span data-stu-id="ed945-137">When you register an item by using a mobile device menu item where the **License plate grouping policy** field is set to *User defined*, the system might require that you confirm or enter license plate numbers, batch numbers, or serial numbers.</span></span>

<span data-ttu-id="ed945-138">Na stronie potwierdzenia dla bieżącego numeru identyfikacyjnego system pokazuje ilość zaalokowana dla bieżącego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="ed945-138">On the license plate confirmation page, the system will show the quantity that is allocated for the current license plate.</span></span> <span data-ttu-id="ed945-139">Na stronach potwierdzenia przetwarzania wsadowego lub seryjnego w systemie będzie pokazywana ilość, jaka musi zostać jeszcze odebrana dla bieżącego numeru seryjnego.</span><span class="sxs-lookup"><span data-stu-id="ed945-139">On the batch or serial confirmation pages, the system will show the quantity that must still be received on the current license plate.</span></span> <span data-ttu-id="ed945-140">Zawiera również pole, w którym można wprowadzić ilość do rejestracji dla tej kombinacji numeru identyfikacyjnego i numeru seryjnego.</span><span class="sxs-lookup"><span data-stu-id="ed945-140">It will also include a field where you can enter the quantity to register for that combination of license plate and batch or serial number.</span></span> <span data-ttu-id="ed945-141">W tym przypadku upewnij się, że ilość zarejestrowana dla tego numeru identyfikacyjnego nie przekracza ilości, która musi być jeszcze otrzymana.</span><span class="sxs-lookup"><span data-stu-id="ed945-141">In this case, make sure that the quantity that is being registered for the license plate doesn't exceed the quantity that must still be received.</span></span>

<span data-ttu-id="ed945-142">Jeśli podczas rejestracji zamówienia przychodzącego generowana jest zbyt wiele numerów identyfikacyjnych, wartość pola **Zasady grupowania numerów identyfikacyjnych** może zostać zmieniona na *Grupowanie numerów identyfikacyjnych*, można przypisać do towaru nową grupę sekwencji jednostek lub można dezaktywować opcję **Grupowania numerów identyfikacyjnych** dla tej grupy sekwencji jednostek.</span><span class="sxs-lookup"><span data-stu-id="ed945-142">Alternatively, if too many license plates are being generated on inbound order registration, the value of the **License plate grouping policy** field can be changed to *License plate grouping*, a new unit sequence group can be assigned to the item, or the **License plate grouping** option for the unit sequence group can be inactivated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
