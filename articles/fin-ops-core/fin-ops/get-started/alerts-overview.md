---
title: Omówienie alertów
description: Ten temat zawiera ogólne informacje o alertach. Alerty pozwalają na bieżąco uzyskiwać informacje o zdarzeniach, które chcesz śledzić podczas dnia pracy.
author: tjvass
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: e57b065dc1a2c0db593b38106f4391e281feb1e6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565045"
---
# <a name="alerts-overview"></a><span data-ttu-id="78a5b-104">Omówienie alertów</span><span class="sxs-lookup"><span data-stu-id="78a5b-104">Alerts overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a><span data-ttu-id="78a5b-105">Alerty — informacje</span><span class="sxs-lookup"><span data-stu-id="78a5b-105">About alerts</span></span>
<span data-ttu-id="78a5b-106">Alerty stanowią system zgłaszania zdarzeń krytycznych w systemie.</span><span class="sxs-lookup"><span data-stu-id="78a5b-106">Alerts form a notification system for critical events in the system.</span></span> <span data-ttu-id="78a5b-107">Alerty pozwalają na bieżąco uzyskiwać informacje o zdarzeniach, które chcesz śledzić podczas dnia pracy.</span><span class="sxs-lookup"><span data-stu-id="78a5b-107">You can use alerts to stay informed about events that you want to track during the workday.</span></span> <span data-ttu-id="78a5b-108">Można łatwo utworzyć własny zbiór reguł alertów dotyczących zaległych dostaw, usuniętych zamówień, zmian cen oraz innych zdarzeń, na które należy reagować.</span><span class="sxs-lookup"><span data-stu-id="78a5b-108">You can easily create your own set of alert rules so that you're alerted about deliveries that are overdue, orders that are deleted, prices that change, or other events that you must respond to.</span></span>

<span data-ttu-id="78a5b-109">W środowisku planowania zasobów przedsiębiorstwa (ERP) istnieje kilka typowych scenariuszy, gdzie można używać funkcji alertów.</span><span class="sxs-lookup"><span data-stu-id="78a5b-109">In enterprise resource planning (ERP), there are several typical scenarios where the alerts feature can be used.</span></span> <span data-ttu-id="78a5b-110">Oto kilka przykładów.</span><span class="sxs-lookup"><span data-stu-id="78a5b-110">Here are some examples.</span></span>

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a><span data-ttu-id="78a5b-111">Scenariusz 1: tworzenie reguły alertu dla nowych zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="78a5b-111">Scenario 1: Create an alert rule for new sales orders</span></span>

1. <span data-ttu-id="78a5b-112">Otwórz stronę **Wszystkie zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-112">Open the **All sales orders** page.</span></span>
2. <span data-ttu-id="78a5b-113">W okienku akcji na karcie **Opcje** w grupie **Udostępnij** wybierz opcję **Utwórz alert niestandardowy**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-113">On the Action Pane, on the **Options** tab, in the **Share** group, select **Create a custom alert**.</span></span>
3. <span data-ttu-id="78a5b-114">W oknie dialogowym **Utwórz regułę alertu** na skróconej karcie **Prześlij mi alert, gdy** w polu **Zdarzenie** zaznacz opcję **Rekord został utworzony**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-114">In the **Create alert rule** dialog box, on the **Alert me when** FastTab, in the **Event** field, select **Record has been created**.</span></span>

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a><span data-ttu-id="78a5b-115">Scenariusz 2: tworzenie reguły alertu dla opóźnienia daty dostawy</span><span class="sxs-lookup"><span data-stu-id="78a5b-115">Scenario 2: Create an alert rule for postponement of a delivery date</span></span>

1. <span data-ttu-id="78a5b-116">Otwórz stronę **Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-116">Open the **All purchase orders** page.</span></span>
2. <span data-ttu-id="78a5b-117">Zaznacz identyfikator zamówienia zakupu, aby przejdź do szczegółów zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="78a5b-117">Select a purchase order ID to access the purchase order details.</span></span>
3. <span data-ttu-id="78a5b-118">Rozwiń skróconą kartę **Nagłówek zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-118">Expand the **Purchase order header** FastTab.</span></span>
4. <span data-ttu-id="78a5b-119">W okienku akcji na karcie **Opcje** w grupie **Udostępnij** wybierz opcję **Utwórz alert niestandardowy**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-119">On the Action Pane, on the **Options** tab, in the **Share** group, select **Create a custom alert**.</span></span>
5. <span data-ttu-id="78a5b-120">W oknie dialogowym **Utwórz regułę alertu** na skróconej karcie **Prześlij mi alert, gdy** w polu **Pole** zaznacz opcję **Data dostawy**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-120">In the **Create alert rule** dialog box, on the **Alert me when** FastTab, in the **Field** field, select **Delivery date**.</span></span>
6. <span data-ttu-id="78a5b-121">W polu **Zdarzenie** wybierz wartość **odroczono**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-121">In the **Event** field, select **has been postponed**.</span></span>
    
<span data-ttu-id="78a5b-122">Po zamknięciu okna dialogowego **Utwórz regułę alertu** reguła pojawi się na stronie **Zarządzaj regułami alertów**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-122">After you close the **Create alert rule** dialog box, your rule appears on the **Manage alert rules** page.</span></span> <span data-ttu-id="78a5b-123">Można użyć strony **Zarządzaj regułami alertów**, aby zaktualizować istniejące reguły alertów.</span><span class="sxs-lookup"><span data-stu-id="78a5b-123">You can use the **Manage alert rules** page to update your existing alert rules.</span></span> <span data-ttu-id="78a5b-124">Na przykład można zmodyfikować wyzwalacze zdarzeń oraz zaktualizować powiadomienia o zdarzeniach i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="78a5b-124">For example, you can modify event triggers, update event notifications, and update expiration dates.</span></span> <span data-ttu-id="78a5b-125">Aby otworzyć stronę **Zarządzaj regułami alertów**, użyj przycisku **Prześlij mi alert** znajdującego się na karcie **Opcje** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="78a5b-125">To open the **Manage alert rules** page, use the **Alert me** button on the **Options** tab of the Action Pane.</span></span>

## <a name="what-occurs-when-an-alert-rule-is-created"></a><span data-ttu-id="78a5b-126">Co się dzieje po utworzeniu reguły alertu?</span><span class="sxs-lookup"><span data-stu-id="78a5b-126">What occurs when an alert rule is created?</span></span>

<span data-ttu-id="78a5b-127">Podczas tworzenia reguł alertów można skojarzyć wstępnie zdefiniowane zdarzenie z określonym polem.</span><span class="sxs-lookup"><span data-stu-id="78a5b-127">When you create alert rules, you can associate a predefined event with a specific field.</span></span> <span data-ttu-id="78a5b-128">Może ono dotyczyć na przykład nadejścia dnia określonego w polu lub zmiany zawartości pola.</span><span class="sxs-lookup"><span data-stu-id="78a5b-128">For example, the date that is specified in the field arrives, or the contents of the field change.</span></span> <span data-ttu-id="78a5b-129">Alternatywnie można skojarzyć zdarzenie z rekordami na konkretnej stronie.</span><span class="sxs-lookup"><span data-stu-id="78a5b-129">Alternatively, you can associate an event with the records on a specific page.</span></span> <span data-ttu-id="78a5b-130">Na przykład rekord jest tworzony lub usuwany.</span><span class="sxs-lookup"><span data-stu-id="78a5b-130">For example, a record is created, or a record is deleted.</span></span>

<span data-ttu-id="78a5b-131">Gdy wybrane zdarzenie nastąpi dla określonego pola lub rekordu na stronie, zostanie Ci wysłany alert.</span><span class="sxs-lookup"><span data-stu-id="78a5b-131">When the selected event occurs for the field or for a record on the page, an alert is sent to you.</span></span> <span data-ttu-id="78a5b-132">Na przykład można utworzyć regułę, w której skojarzysz pole **Data dostawy** określonego wiersza zamówienia zakupu ze zdarzeniem **ta kwota była należna pewien czas temu**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-132">For example, you create a rule where you associate the **Delivery date** field on a specific purchase order line with the **was due this amount of time ago** event.</span></span> <span data-ttu-id="78a5b-133">Ustawiasz przedział czasu na pięć dni.</span><span class="sxs-lookup"><span data-stu-id="78a5b-133">You set the time frame to five days.</span></span> <span data-ttu-id="78a5b-134">W takim przypadku alert zostanie wysłany 5 dni po dacie dostawy towarów z tego wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="78a5b-134">In this case, an alert is sent five days after the delivery date of that purchase order line.</span></span>

<span data-ttu-id="78a5b-135">Ponadto reguły alertów można doprecyzować, ustawiając warunki.</span><span class="sxs-lookup"><span data-stu-id="78a5b-135">Additionally, you can refine alert rules by setting conditions.</span></span> <span data-ttu-id="78a5b-136">Na przykład możesz otrzymywać alerty o nowych zamówieniach zakupu, które są tworzone dla określonych kont dostawców.</span><span class="sxs-lookup"><span data-stu-id="78a5b-136">For example, you can be alerted about new purchase orders that are created for specific vendor accounts.</span></span>

## <a name="preparing-for-an-alert"></a><span data-ttu-id="78a5b-137">Przygotowywanie się do odbierania alertów</span><span class="sxs-lookup"><span data-stu-id="78a5b-137">Preparing for an alert</span></span>

<span data-ttu-id="78a5b-138">Przed utworzeniem reguły alertu musisz zdecydować, kiedy i w jakich sytuacjach chcesz otrzymywać alerty.</span><span class="sxs-lookup"><span data-stu-id="78a5b-138">Before you set up an alert rule, decide when or in what situations you want to receive alerts.</span></span> <span data-ttu-id="78a5b-139">Gdy już wiesz, o którym zdarzeniu chcesz otrzymywać powiadomienia, odszukaj stronę, na której pojawiają się dane wywołujące zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="78a5b-139">When you know which event you want to be notified about, find the page where the data that causes that event appears.</span></span> <span data-ttu-id="78a5b-140">Zdarzeniem może być nadejście określonego dnia lub wystąpienie konkretnej zmiany.</span><span class="sxs-lookup"><span data-stu-id="78a5b-140">The event can be a date that arrives or a specific change that occurs.</span></span> <span data-ttu-id="78a5b-141">W związku z tym należy odnaleźć stronę, gdzie jest podana data, znajduje się modyfikowane pole lub widać nowo tworzony rekord.</span><span class="sxs-lookup"><span data-stu-id="78a5b-141">Therefore, you must find the page where the date is specified, or where the field that changes or the new record that is created appears.</span></span> <span data-ttu-id="78a5b-142">Mając te informacje, można utworzyć regułę alertu.</span><span class="sxs-lookup"><span data-stu-id="78a5b-142">After you have this information, you can create the alert rule.</span></span>

## <a name="components-of-an-alert-rule"></a><span data-ttu-id="78a5b-143">Składniki reguły alertu</span><span class="sxs-lookup"><span data-stu-id="78a5b-143">Components of an alert rule</span></span>

<span data-ttu-id="78a5b-144">Reguła alertu ma pięć składników:</span><span class="sxs-lookup"><span data-stu-id="78a5b-144">An alert rule has five components:</span></span>

- <span data-ttu-id="78a5b-145">**Zdarzenie** — zdarzeniem wyzwalającym regułę alertu może być nadejście określonego dnia lub wystąpienie konkretnej zmiany.</span><span class="sxs-lookup"><span data-stu-id="78a5b-145">**Event** – The event that triggers an alert rule can be a date that arrives or a specific change that occurs.</span></span> <span data-ttu-id="78a5b-146">Zdarzenia definiuje się na skróconej karcie **Wyślij alerty e-mail dotyczące zmian stanu zadania** w oknie dialogowym **Utwórz regułę alertu**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-146">You define events on the **Send email alerts for job status changes** FastTab of the **Create alert rule** dialog box.</span></span>
- <span data-ttu-id="78a5b-147">**Warunek** — na skróconej karcie **Prześlij mi alert dla** w oknie dialogowym **Utwórz regułę alertu** można wybrać zakres warunku, aby kontrolować, kiedy otrzymujesz alerty o zdarzeniach.</span><span class="sxs-lookup"><span data-stu-id="78a5b-147">**Condition** – On the **Alert me for** FastTab of the **Create alert rule** dialog box, you can select the scope of the condition, to control when you're alerted about events.</span></span> <span data-ttu-id="78a5b-148">Regułę można zastosować tylko do bieżącego rekordu lub do wszystkich rekordów widocznych na stronie.</span><span class="sxs-lookup"><span data-stu-id="78a5b-148">You can apply the rule either to the current record only or to all visible records on the page.</span></span> <span data-ttu-id="78a5b-149">Jeśli reguła jest stosowana do wielu firm, można w opcji **Na poziomie organizacji** ustawić wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="78a5b-149">If the rule applies across legal entities, you can set the **Organization-wide** option to **Yes**.</span></span>
- <span data-ttu-id="78a5b-150">**Wygaśnięcie reguły** — na skróconej karcie **Przesyłaj mi alerty do** w oknie dialogowym **Utwórz regułę alertu** można określić, jak długo reguła alertu powinna być aktywna.</span><span class="sxs-lookup"><span data-stu-id="78a5b-150">**Expiry of rule** – On the **Alert me until** FastTab of the **Create alert rule** dialog box, you can specify how long the alert rule should be active.</span></span>
- <span data-ttu-id="78a5b-151">**Zawartość** — na skróconej karcie **Prześlij mi alert za pomocą** w oknie dialogowym **Utwórz regułę alertu** można określić tekst tematu i treść wiadomości, które mają być używane w komunikatach alarmowych.</span><span class="sxs-lookup"><span data-stu-id="78a5b-151">**Contents** – On the **Alert me with** FastTab of the **Create alert rule** dialog box, you can specify the subject text and message text that the alert messages should use.</span></span>
- <span data-ttu-id="78a5b-152">**Użytkownik** — na skróconej karcie **Adresat alertu** w oknie dialogowym **Utwórz regułę alertu** można określić, który użytkownik powinien otrzymywać komunikaty alarmowe.</span><span class="sxs-lookup"><span data-stu-id="78a5b-152">**User** – On the **Alert who** FastTab of the **Create alert rule** dialog box, you can specify which user should receive the alert messages.</span></span> <span data-ttu-id="78a5b-153">Domyślnie jest zaznaczony Twój identyfikator użytkownika.</span><span class="sxs-lookup"><span data-stu-id="78a5b-153">By default, your user ID is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78a5b-154">Dostęp do tej opcji mają tylko administratorzy organizacji.</span><span class="sxs-lookup"><span data-stu-id="78a5b-154">This option is restricted to organization administrators.</span></span>

## <a name="videos"></a><span data-ttu-id="78a5b-155">Filmy wideo</span><span class="sxs-lookup"><span data-stu-id="78a5b-155">Videos</span></span>

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a><span data-ttu-id="78a5b-156">Sposób używania alertów do monitorowania filtrowanych danych</span><span class="sxs-lookup"><span data-stu-id="78a5b-156">How to use alerts to monitor filtered data</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3DWZ3]

<span data-ttu-id="78a5b-157">Film wideo [Sposób używania alertów do monitorowania filtrowanych danych](https://youtu.be/ZYKMcv6kl9s) (pokazany powyżej) znajduje się na [Liście odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.</span><span class="sxs-lookup"><span data-stu-id="78a5b-157">The [How to use alerts to monitor filtered data](https://youtu.be/ZYKMcv6kl9s) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

### <a name="alert-rule-options"></a><span data-ttu-id="78a5b-158">Opcje reguł alertów</span><span class="sxs-lookup"><span data-stu-id="78a5b-158">Alert rule options</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E4PV]

<span data-ttu-id="78a5b-159">Film wideo [Opcje reguł alertów](https://youtu.be/cpzimwOjicM) (widoczny powyżej) jest zawarty na [liście odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.</span><span class="sxs-lookup"><span data-stu-id="78a5b-159">The [Alert rule options](https://youtu.be/cpzimwOjicM) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]