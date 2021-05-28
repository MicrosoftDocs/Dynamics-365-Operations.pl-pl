---
title: Komunikaty procesora komunikatów
description: Ten temat zawiera informacje dotyczące funkcji komunikatów procesora komunikatów dotyczących obciążeń jednostek skalowania.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysMessageProcessorMessage, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 03d8cad743ac2b2b1e7b2832b8272ca3dbf5a163
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021062"
---
# <a name="message-processor-messages"></a><span data-ttu-id="17a2f-103">Komunikaty procesora komunikatów</span><span class="sxs-lookup"><span data-stu-id="17a2f-103">Message processor messages</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="17a2f-104">Komunikaty procesora komunikatów są używane podczas uruchamiania jednostek skalowania chmury i urządzenia brzegowego w przypadku [obciążeń produkcyjnych](cloud-edge-workload-manufacturing.md) oraz [obciążeń zarządzania magazynu](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="17a2f-104">Message processor messages are used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="17a2f-105">W celu ich synchronizacji między środowiskami wdrażania centrum i jednostki skalowania wymieniana jest duża ilość danych, ale *procesor komunikatów* przetworzy tylko część z tych wymian.</span><span class="sxs-lookup"><span data-stu-id="17a2f-105">A large amount of data is exchanged between the hub and scale unit deployment environments to keep them in sync, but only a few of these data exchanges will be processed by the *message processor*.</span></span> <span data-ttu-id="17a2f-106">Komunikaty przetwarzane przez procesor komunikatów można wyświetlić, przechodząc do widoku **Administrowanie systemem > Procesor komunikatów > Komunikaty procesora komunikatów**.</span><span class="sxs-lookup"><span data-stu-id="17a2f-106">You can view the messages processed by the message processor by going to **System administration > Message processor > Message processor messages**.</span></span>

## <a name="message-grid-columns-and-filters"></a><span data-ttu-id="17a2f-107">Kolumny i filtry siatki komunikatów</span><span class="sxs-lookup"><span data-stu-id="17a2f-107">Message grid columns and filters</span></span>

<span data-ttu-id="17a2f-108">Pól w górnej części strony **Komunikaty procesora komunikatów** można używać do wyszukiwania określonych komunikatów.</span><span class="sxs-lookup"><span data-stu-id="17a2f-108">You can use the fields at the top of the **Message processor messages** page to help find any particular messages you are looking for.</span></span> <span data-ttu-id="17a2f-109">Większość z tych filtrów pasuje do nagłówków kolumn w siatce wiadomości.</span><span class="sxs-lookup"><span data-stu-id="17a2f-109">Most of these filters match the column headings in the message grid.</span></span> <span data-ttu-id="17a2f-110">Dostępne są następujące filtry i nagłówki kolumn:</span><span class="sxs-lookup"><span data-stu-id="17a2f-110">The following filters and column headings are available:</span></span>

- <span data-ttu-id="17a2f-111">**Typ komunikatu** — określa typ komunikatu.</span><span class="sxs-lookup"><span data-stu-id="17a2f-111">**Message type** – Specifies the type of message.</span></span>
- <span data-ttu-id="17a2f-112">**Kolejka komunikatów** — określa nazwę kolejki, w której komunikat ma być przetwarzany.</span><span class="sxs-lookup"><span data-stu-id="17a2f-112">**Message queue** – Specifies the name of the queue in which the message is to be processed.</span></span> <span data-ttu-id="17a2f-113">Dostępne są następujące kolejki:</span><span class="sxs-lookup"><span data-stu-id="17a2f-113">The following queues are provided:</span></span>
  - <span data-ttu-id="17a2f-114">*Jednostka skalowania do piasty*</span><span class="sxs-lookup"><span data-stu-id="17a2f-114">*Scale unit to hub*</span></span>
  - <span data-ttu-id="17a2f-115">*Jednostka skalowania wykonania magazynu do centrali*</span><span class="sxs-lookup"><span data-stu-id="17a2f-115">*Hub to warehouse execution scale unit*</span></span>
  - <span data-ttu-id="17a2f-116">*Jednostka skalowania wykonania produkcji do centrali*</span><span class="sxs-lookup"><span data-stu-id="17a2f-116">*Hub to manufacturing execution scale unit*</span></span>
- <span data-ttu-id="17a2f-117">**Stan komunikatu** — określa stan komunikatu.</span><span class="sxs-lookup"><span data-stu-id="17a2f-117">**Message state** – Specifies the state of the message.</span></span> <span data-ttu-id="17a2f-118">Istnieją następujące stany:</span><span class="sxs-lookup"><span data-stu-id="17a2f-118">The following states exists:</span></span>
  - <span data-ttu-id="17a2f-119">*W kolejce* — komunikat jest gotowy do przetworzenia przez procesor komunikatów.</span><span class="sxs-lookup"><span data-stu-id="17a2f-119">*Queued* – The message is ready to be processed by the message processor.</span></span>
  - <span data-ttu-id="17a2f-120">*Przetworzony* — komunikat został przetworzony przez procesor komunikatów.</span><span class="sxs-lookup"><span data-stu-id="17a2f-120">*Processed* – The message was successfully processed by the message processor.</span></span>
  - <span data-ttu-id="17a2f-121">*Anulowany* — komunikat został przetworzony, ale przetwarzanie nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="17a2f-121">*Canceled* – The message was processed, but processing failed.</span></span>
- <span data-ttu-id="17a2f-122">**Zawartość komunikatu** — ten filtr umożliwia przeprowadzanie wyszukiwania pełnotekstowego w treści komunikatu.</span><span class="sxs-lookup"><span data-stu-id="17a2f-122">**Message content** – This filter does a full-text search of message content.</span></span> <span data-ttu-id="17a2f-123">(Zawartość komunikatu nie jest wyświetlana w siatce). Filtr traktuje większość symboli specjalnych (takich jak „-”) jako spacje, a wszystkie znaki spacji — jako operatory logiczne LUB.</span><span class="sxs-lookup"><span data-stu-id="17a2f-123">(Message content is not shown in the grid.) The filter treats most special symbols (such as "-") as spaces, and treats all space characters as Boolean OR operators.</span></span> <span data-ttu-id="17a2f-124">T=jeśli na przykład wyszukiwana jest wartość `journalid` równa „USMF-123456”, system znajdzie wszystkie komunikaty zawierające „USMF” lub „123456”, co może być długa listą.</span><span class="sxs-lookup"><span data-stu-id="17a2f-124">T=For example, this means if you search for a specific `journalid` value equal "USMF-123456", the system will find all messages that contain "USMF" or "123456", which is likely to be a long list.</span></span> <span data-ttu-id="17a2f-125">W związku z tym lepiej jest wpisać tylko wartość „123456”, ponieważ spowoduje to zwrócenie bardziej precyzyjnych wyników.</span><span class="sxs-lookup"><span data-stu-id="17a2f-125">Therefore, it would be better to enter just "123456" alone because that will return more specific results.</span></span>

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a><span data-ttu-id="17a2f-126">Przykładowy typ komunikatu: żądanie aktualizacji finansowej korekty zapasów</span><span class="sxs-lookup"><span data-stu-id="17a2f-126">Example message type: Request inventory adjustment financial update</span></span>

<span data-ttu-id="17a2f-127">Na przykład **typ komunikatu** *Żądanie aktualizacji finansowej korekty zapasów* jest używany do tworzenia i księgowania arkusza zliczania w centrum, gdy pracownik używa aplikacji magazynu do [rejestrowania korekty zapasów](cloud-edge-warehouse-inventory-adjustment.md) w obciążeniach zarządzania magazynem jednostki skalowania.</span><span class="sxs-lookup"><span data-stu-id="17a2f-127">For example, the **Message type** *Request inventory adjustment financial update* is used to create and post a counting journal on the hub when a worker uses the warehouse app to [register an inventory adjustment](cloud-edge-warehouse-inventory-adjustment.md) on a scale unit warehouse management workload.</span></span> <span data-ttu-id="17a2f-128">Ponieważ ten określony proces pochodzi z jednostki skalowania, w polu **Kolejki wiadomości** jest pokazywana wartość *Jednostka skalowania z centrum*.</span><span class="sxs-lookup"><span data-stu-id="17a2f-128">Because this specific process originates from a scale unit, the **Message queue** field will show the value *Scale unit to hub*.</span></span>

<span data-ttu-id="17a2f-129">Dla tego typu komunikatu obciążenie jednostki skalowania rejestruje komunikat jako część operacji korekty zapasów w aplikacji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="17a2f-129">For this message type, a scale unit workload records the message as part of a warehouse app inventory adjustment operation.</span></span> <span data-ttu-id="17a2f-130">Dane komunikatu są następnie przenoszone do centrum w ramach tego samego procesu używanego dla [architektury Commerce Data Exchange](../../commerce/commerce-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="17a2f-130">The message data is then transferred to the hub as part of the same process used for the [Commerce data exchange architecture](../../commerce/commerce-architecture.md).</span></span> <span data-ttu-id="17a2f-131">Komunikat zostanie zaktualizowany, aby wyświetlić **stan komunikatu** jako *oczekujący*.</span><span class="sxs-lookup"><span data-stu-id="17a2f-131">The message will be updated to show **Message state** as *Queued*.</span></span> <span data-ttu-id="17a2f-132">Następnie procesor komunikatów spróbuje przetworzyć komunikat i zaktualizuje **stan komunikatu** na *Przetworzony* lub *Anulowany*.</span><span class="sxs-lookup"><span data-stu-id="17a2f-132">The message processor then attempts to process the message and updates the **Message state** to *Processed* on success, or *Canceled* on failure.</span></span>

## <a name="view-the-message-log-message-content-and-details"></a><span data-ttu-id="17a2f-133">Wyświetlanie dziennika komunikatów, zawartości komunikatu i szczegółów</span><span class="sxs-lookup"><span data-stu-id="17a2f-133">View the message log, message content, and details</span></span>

<span data-ttu-id="17a2f-134">Szczegółowe informacje o komunikacie można znaleźć, zaznaczając go w siatce, a następnie otwierając karty **Dziennik** lub **Zawartość komunikatu** w siatce komunikatów, na których są wyświetlane poszczególne zdarzenia przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="17a2f-134">You can find detailed information about a message by selecting it in the grid and then opening the **Log** or **Message content** tabs under the message grid, where each processing event is shown.</span></span>

<span data-ttu-id="17a2f-135">**Zawartość komunikatu** zależy od **typu komunikatu** i dlatego będzie mieć różną długość tekstu.</span><span class="sxs-lookup"><span data-stu-id="17a2f-135">The **Message content** depends on the **Message type** and will therefore have different text length.</span></span> <span data-ttu-id="17a2f-136">Typowy tekst komunikatu rozpoczyna się od znaku **{** i kończy znakiem **}**, a pomiędzy nimi znajdują się nazwy pól, jak `journalId`, a następnie znak **:** i wartość, jak *USMF-123456*.</span><span class="sxs-lookup"><span data-stu-id="17a2f-136">A typical message content text will start with a **{** and end with a **}** and in between have field names such as `journalId` followed by a **:** and a value such as *USMF-123456*.</span></span>

<span data-ttu-id="17a2f-137">Pasek narzędzi na karcie **Dziennik** zawiera następujące przyciski:</span><span class="sxs-lookup"><span data-stu-id="17a2f-137">The toolbar on the **Log** tab includes the following buttons:</span></span>

- <span data-ttu-id="17a2f-138">**Dziennik** — wyświetlane są wyniki przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="17a2f-138">**Log** – Displays the processing results.</span></span> <span data-ttu-id="17a2f-139">Jest to szczególnie pomocne w celu zrozumienia przyczyn niepowodzenia przetwarzania komunikatów o **wyniku przetwarzania** *Niepowodzenie*.</span><span class="sxs-lookup"><span data-stu-id="17a2f-139">This is especially helpful for understanding the reasons for a processing failure for messages having a **Processing result** of *Failed*.</span></span>
- <span data-ttu-id="17a2f-140">**Pakiet** — wiele operacji przetwarzania wiadomości może być uruchomionych w ramach tego samego procesu wsadowego.</span><span class="sxs-lookup"><span data-stu-id="17a2f-140">**Bundle** – Multiple message processing operations can run as part of the same batch process.</span></span> <span data-ttu-id="17a2f-141">Ten przycisk należy nacisnąć, aby wyświetlić te szczegółowe dane.</span><span class="sxs-lookup"><span data-stu-id="17a2f-141">Select this button to view this detailed data.</span></span> <span data-ttu-id="17a2f-142">Na przykład można sprawdzić, czy istnieją zależności wymagające od systemu przetwarzania określonych komunikatów w określonej kolejności.</span><span class="sxs-lookup"><span data-stu-id="17a2f-142">For example, you can see whether dependencies exist that require the system to process certain messages in a specific sequence.</span></span>

## <a name="message-processor-batch-job"></a><span data-ttu-id="17a2f-143">Zadanie wsadowe procesora komunikatów</span><span class="sxs-lookup"><span data-stu-id="17a2f-143">Message processor batch job</span></span>

<span data-ttu-id="17a2f-144">Podczas uruchamiania chmury i urządzenia brzegowego zadanie wsadowe *Procesor komunikatów* zostanie automatycznie utworzone w celu wykonania, więc nie ma potrzeby ręcznego planowania tego zadania.</span><span class="sxs-lookup"><span data-stu-id="17a2f-144">When running a cloud and edge deployment, the *Message processor* batch job will automatically be evoked when a new message is created for processing, so you should not need to schedule this job manually.</span></span>

<span data-ttu-id="17a2f-145">W razie potrzeby można uzyskać dostęp do zadania wsadowego, klikając pozycję **Administrowanie systemem > Procesor komunikatów > Procesor komunikatów**.</span><span class="sxs-lookup"><span data-stu-id="17a2f-145">If necessary, you can access the batch job by going to **System administration > Message  processor > Message processor**.</span></span>

## <a name="manually-process-or-cancel-a-message"></a><span data-ttu-id="17a2f-146">Ręczne przetwarzanie lub anulowanie komunikatu</span><span class="sxs-lookup"><span data-stu-id="17a2f-146">Manually process or cancel a message</span></span>

<span data-ttu-id="17a2f-147">W razie potrzeby można ręcznie przetworzyć lub anulować komunikat, w zależności od jego bieżącego stanu.</span><span class="sxs-lookup"><span data-stu-id="17a2f-147">If needed, you can manually process or cancel a message, depending on its current state.</span></span> <span data-ttu-id="17a2f-148">W tym celu zaznacz komunikat w siatce, a następnie wybierz opcję **Przetwórz** lub **Anuluj** w okienku akcji</span><span class="sxs-lookup"><span data-stu-id="17a2f-148">To do so, select the message in the grid and then select **Process** or **Cancel** on the Action Pane</span></span>

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a><span data-ttu-id="17a2f-149">Konfigurowanie zdarzeń biznesowych w celu dostarczania alertów o nieudanym przetwarzaniu</span><span class="sxs-lookup"><span data-stu-id="17a2f-149">Set up business events to deliver alerts for failed processing results</span></span>

<span data-ttu-id="17a2f-150">Oprócz filtrowania według wartości **stanu komunikatu** *Anulowany* w celu wyszukiwania informacji o nieudanych komunikatach, można skonfigurować [zdarzenia biznesowe](../../fin-ops-core/dev-itpro/business-events/home-page.md) w centrum, aby otrzymywać alerty o nieudanym przetwarzaniu.</span><span class="sxs-lookup"><span data-stu-id="17a2f-150">In addition to filtering on the **Message state** value *Canceled* to inquire for failed messages, you can set up [Business events](../../fin-ops-core/dev-itpro/business-events/home-page.md) on the hub to alert you to failed processing results.</span></span> <span data-ttu-id="17a2f-151">W tym celu aktywuj zdarzenie biznesowe o nazwie *Przetworzenie komunikatu procesora komunikatów* na stronie **Katalog zdarzeń biznesowych** (**Administrowanie systemem > Ustawienia > Zdarzenia biznesowe > Katalog zdarzeń biznesowych**).</span><span class="sxs-lookup"><span data-stu-id="17a2f-151">To do so, activate the business event named *Message processor message processed*  on the **Business events catalog** page (**System administration > Setup > Business events > Business events catalog**).</span></span>

<span data-ttu-id="17a2f-152">W trakcie procesu aktywacji należy określić, czy zdarzenie jest specyficzne dla jednej czy wszystkich firm, i podać **nazwę punktu końcowego**, którą należy najpierw zdefiniować.</span><span class="sxs-lookup"><span data-stu-id="17a2f-152">As part of the activation process, you will be guided to specify whether the event is specific to one or all legal entities and provide an **Endpoint name**, which must be defined first.</span></span>

>[!NOTE]
> <span data-ttu-id="17a2f-153">Jeśli w polu **w przypadku wystąpienia zdarzenia biznesowego** jest wybrane ustawienie *Microsoft Power Automate* (a nie na przykład *HTTPS*), **nazwa punktu końcowego** zostanie automatycznie utworzona w module Supply Chain Management na podstawie ustawień *Microsoft Power Automate*.</span><span class="sxs-lookup"><span data-stu-id="17a2f-153">If **When a Business Event occurs** is set to *Microsoft Power Automate* (rather than *HTTPS*, for example), the **Endpoint name** will automatically be created in Supply Chain Management based on the *Microsoft Power Automate* setup.</span></span>

### <a name="microsoft-power-automate-example"></a><span data-ttu-id="17a2f-154">Przykład: Microsoft Power Automate</span><span class="sxs-lookup"><span data-stu-id="17a2f-154">Microsoft Power Automate example</span></span>

<span data-ttu-id="17a2f-155">W tym przykładzie używasz pola **w przypadku wystąpienia zdarzenia biznesowego** z ustawieniem *Microsoft Power Automate*, aby wysyłać wiadomości e-mail zawierające komunikaty InfoLog i hiperłącza do strony **Komunikaty procesora komunikatów** określonego nieprzetworzonego komunikatu we wdrożeniu centrum.</span><span class="sxs-lookup"><span data-stu-id="17a2f-155">In this example, use **When a Business Event occurs** with *Microsoft Power Automate* sends emails containing InfoLog messages and hyperlinks to open the **Message processor messages** page for a specific failed message on the hub deployment.</span></span> <span data-ttu-id="17a2f-156">W razie potrzeby można dodać dodatkową logikę, aby wysłać powiadomienia równolegle przy użyciu innych kanałów i kontrolować adresatów na podstawie danych zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="17a2f-156">If needed, you can add extra logic to send the notifications in parallel using different channels and control the recipients based on the event data.</span></span>

1. <span data-ttu-id="17a2f-157">W [Power Automate](https://preview.flow.microsoft.com) utwórz nowy automatyczny przepływ w chmurze dla wyzwalacza przepływu **w przypadku wystąpienia zdarzenia biznesowego — aplikacja Fin & Ops (Dynamics 365)**, po którym następują kroki **Przeanalizuj JSON** i **Wyślij wiadomość e-mail**, tak jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="17a2f-157">In [Power Automate](https://preview.flow.microsoft.com), create a new automated cloud flow for the flow trigger **When a Business Event occurs - Fin & Ops App (Dynamics 365)** followed by the **Parse JSON** and **Send an email** steps, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Power Automate automatyczny przepływ w chmurze":::

1. <span data-ttu-id="17a2f-159">W kroku **W przypadku wystąpienia zdarzenia biznesowego** można odszukać lub wprowadzić **wystąpienie** centrum, a następnie użyć kroków **Kategoria**, **Zdarzenie biznesowe** *Przetworzony komunikat procesora komunikatów*, jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="17a2f-159">In the **When a Business Event occurs** step, you can look up or enter the hub **Instance** following the **Category** and then the **Business event** *Message processor message processed*, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate Krok W przypadku wystąpienia zdarzenia biznesowego":::

1. <span data-ttu-id="17a2f-161">W kroku **Przeanalizuj JSON** wprowadź **schemat** definiujący pola rozszerzone.</span><span class="sxs-lookup"><span data-stu-id="17a2f-161">For the **Parse JSON** step, enter a **Schema** that defines the extended fields.</span></span> <span data-ttu-id="17a2f-162">Można użyć opcji *Pobierz schemat* na stronie **Katalog zdarzeń biznesowych** w module Supply Chain Management lub rozpocząć od wklejenia przykładowego tekst schematu.</span><span class="sxs-lookup"><span data-stu-id="17a2f-162">You can use the *Download schema* option on the **Business events catalog** page in Supply Chain Management or start by pasting in the example schema text.</span></span> <span data-ttu-id="17a2f-163">Ten przykładowy tekst znajduje się po następującej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="17a2f-163">This example text is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate Krok Przeanalizuj JSON":::

    ```json
    {
        "properties": {
            "BusinessEventId": {
                "type": "string"
            },
            "ControlNumber": {
                "type": "integer"
            },
            "EventId": {
                "type": "string"
            },
            "EventTime": {
                "type": "string"
            },
            "MajorVersion": {
                "type": "integer"
            },
            "MessageContent": {
                "type": "string"
            },
            "MessageDestinationCompanyId": {
                "type": "string"
            },
            "MessageDestinationOperationalSiteId": {
                "type": "string"
            },
            "MessageDestinationWarehouseId": {
                "type": "string"
            },
            "MessageDestinationWorkloadName": {
                "type": "string"
            },
            "MessageInfolog": {
                "type": "string"
            },
            "MessageProcessingResult": {
                "type": "string"
            },
            "MessageProcessingResultLabel": {
                "type": "string"
            },
            "MessageProcessorMessagePageUrl": {
                "type": "string"
            },
            "MessageQueue": {
                "type": "string"
            },
            "MessageQueueLabel": {
                "type": "string"
            },
            "MessageSourceCompanyId": {
                "type": "string"
            },
            "MessageSourceOperationalSiteId": {
                "type": "string"
            },
            "MessageSourceWarehouseId": {
                "type": "string"
            },
            "MessageSourceWorkloadName": {
                "type": "string"
            },
            "MessageState": {
                "type": "string"
            },
            "MessageStateLabel": {
                "type": "string"
            },
            "MessageType": {
                "type": "string"
            },
            "MessageTypeLabel": {
                "type": "string"
            },
            "MinorVersion": {
                "type": "integer"
            }
        },
        "type": "object"
    }
    ```

1. <span data-ttu-id="17a2f-165">W kroku **Wysyłanie wiadomości e-mail** możesz zaznaczyć poszczególne pola lub rozpocząć od wklejenia przykładowej treści wiadomości e-mail w polu **Treść**.</span><span class="sxs-lookup"><span data-stu-id="17a2f-165">In the **Send an email** step, you can select the individual fields or start by pasting the email body example into the **Body** field.</span></span> <span data-ttu-id="17a2f-166">Ten przykład znajduje się po następującej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="17a2f-166">This example is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate Krok Wysyłanie wiadomości e-mail":::

    ```plaintext
    Message queue: @{body('Parse_JSON')?['MessageQueue']}
    Message queue label: @{body('Parse_JSON')?['MessageQueueLabel']}
    Message type: @{body('Parse_JSON')?['MessageQueueType']}
    Message type label: @{body('Parse_JSON')?['MessageQueueTypeLabel']}
    Message content: @{body('Parse_JSON')?['MessageContent']}
    Message state: @{body('Parse_JSON')?['MessageState']}
    Message state label: @{body('Parse_JSON')?['MessageStateLabel']}
    Message processing result: @{body('Parse_JSON')?['MessageProcessingResult']}
    Message processing result label: @{body('Parse_JSON')?['MessageProcessingResultLabel']}
    Message infolog: @{body('Parse_JSON')?['MessageInfolog']}
    Message source company ID: @{body('Parse_JSON')?['MessageSourceCompanyId']}
    Message source workload name: @{body('Parse_JSON')?['MessageSourceWorkloadName']}
    Message source site ID: @{body('Parse_JSON')?['MessageSourceOperationalSiteId']}
    Message source warehouse ID: @{body('Parse_JSON')?['MessageSourceWarehouseId']}
    Message destination company ID: @{body('Parse_JSON')?['MessageDestinationCompanyId']}
    Message destination workload name: @{body('Parse_JSON')?['MessageDestinationWorkloadName']}
    Message destination site ID: @{body('Parse_JSON')?['MessageDestinationOperationalSiteId']}
    Message destination warehouse ID: @{body('Parse_JSON')?['MessageDestinationWarehouseId']}
    Message processor message page URL: @{body('Parse_JSON')?['MessageProcessorMessagePageUrl']}
    ```

1. <span data-ttu-id="17a2f-168">Zapisanie zdarzenia biznesowego spowoduje jego automatyczne uaktywnienie, po czym jest gotowe do użycia w ramach modułu Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="17a2f-168">When you save the business event, it will automatically be activated and ready to use as part of Supply Chain Management.</span></span>
