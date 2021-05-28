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
# <a name="message-processor-messages"></a>Komunikaty procesora komunikatów

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Komunikaty procesora komunikatów są używane podczas uruchamiania jednostek skalowania chmury i urządzenia brzegowego w przypadku [obciążeń produkcyjnych](cloud-edge-workload-manufacturing.md) oraz [obciążeń zarządzania magazynu](cloud-edge-workload-warehousing.md).

W celu ich synchronizacji między środowiskami wdrażania centrum i jednostki skalowania wymieniana jest duża ilość danych, ale *procesor komunikatów* przetworzy tylko część z tych wymian. Komunikaty przetwarzane przez procesor komunikatów można wyświetlić, przechodząc do widoku **Administrowanie systemem > Procesor komunikatów > Komunikaty procesora komunikatów**.

## <a name="message-grid-columns-and-filters"></a>Kolumny i filtry siatki komunikatów

Pól w górnej części strony **Komunikaty procesora komunikatów** można używać do wyszukiwania określonych komunikatów. Większość z tych filtrów pasuje do nagłówków kolumn w siatce wiadomości. Dostępne są następujące filtry i nagłówki kolumn:

- **Typ komunikatu** — określa typ komunikatu.
- **Kolejka komunikatów** — określa nazwę kolejki, w której komunikat ma być przetwarzany. Dostępne są następujące kolejki:
  - *Jednostka skalowania do piasty*
  - *Jednostka skalowania wykonania magazynu do centrali*
  - *Jednostka skalowania wykonania produkcji do centrali*
- **Stan komunikatu** — określa stan komunikatu. Istnieją następujące stany:
  - *W kolejce* — komunikat jest gotowy do przetworzenia przez procesor komunikatów.
  - *Przetworzony* — komunikat został przetworzony przez procesor komunikatów.
  - *Anulowany* — komunikat został przetworzony, ale przetwarzanie nie powiodło się.
- **Zawartość komunikatu** — ten filtr umożliwia przeprowadzanie wyszukiwania pełnotekstowego w treści komunikatu. (Zawartość komunikatu nie jest wyświetlana w siatce). Filtr traktuje większość symboli specjalnych (takich jak „-”) jako spacje, a wszystkie znaki spacji — jako operatory logiczne LUB. T=jeśli na przykład wyszukiwana jest wartość `journalid` równa „USMF-123456”, system znajdzie wszystkie komunikaty zawierające „USMF” lub „123456”, co może być długa listą. W związku z tym lepiej jest wpisać tylko wartość „123456”, ponieważ spowoduje to zwrócenie bardziej precyzyjnych wyników.

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a>Przykładowy typ komunikatu: żądanie aktualizacji finansowej korekty zapasów

Na przykład **typ komunikatu** *Żądanie aktualizacji finansowej korekty zapasów* jest używany do tworzenia i księgowania arkusza zliczania w centrum, gdy pracownik używa aplikacji magazynu do [rejestrowania korekty zapasów](cloud-edge-warehouse-inventory-adjustment.md) w obciążeniach zarządzania magazynem jednostki skalowania. Ponieważ ten określony proces pochodzi z jednostki skalowania, w polu **Kolejki wiadomości** jest pokazywana wartość *Jednostka skalowania z centrum*.

Dla tego typu komunikatu obciążenie jednostki skalowania rejestruje komunikat jako część operacji korekty zapasów w aplikacji magazynowej. Dane komunikatu są następnie przenoszone do centrum w ramach tego samego procesu używanego dla [architektury Commerce Data Exchange](../../commerce/commerce-architecture.md). Komunikat zostanie zaktualizowany, aby wyświetlić **stan komunikatu** jako *oczekujący*. Następnie procesor komunikatów spróbuje przetworzyć komunikat i zaktualizuje **stan komunikatu** na *Przetworzony* lub *Anulowany*.

## <a name="view-the-message-log-message-content-and-details"></a>Wyświetlanie dziennika komunikatów, zawartości komunikatu i szczegółów

Szczegółowe informacje o komunikacie można znaleźć, zaznaczając go w siatce, a następnie otwierając karty **Dziennik** lub **Zawartość komunikatu** w siatce komunikatów, na których są wyświetlane poszczególne zdarzenia przetwarzania.

**Zawartość komunikatu** zależy od **typu komunikatu** i dlatego będzie mieć różną długość tekstu. Typowy tekst komunikatu rozpoczyna się od znaku **{** i kończy znakiem **}**, a pomiędzy nimi znajdują się nazwy pól, jak `journalId`, a następnie znak **:** i wartość, jak *USMF-123456*.

Pasek narzędzi na karcie **Dziennik** zawiera następujące przyciski:

- **Dziennik** — wyświetlane są wyniki przetwarzania. Jest to szczególnie pomocne w celu zrozumienia przyczyn niepowodzenia przetwarzania komunikatów o **wyniku przetwarzania** *Niepowodzenie*.
- **Pakiet** — wiele operacji przetwarzania wiadomości może być uruchomionych w ramach tego samego procesu wsadowego. Ten przycisk należy nacisnąć, aby wyświetlić te szczegółowe dane. Na przykład można sprawdzić, czy istnieją zależności wymagające od systemu przetwarzania określonych komunikatów w określonej kolejności.

## <a name="message-processor-batch-job"></a>Zadanie wsadowe procesora komunikatów

Podczas uruchamiania chmury i urządzenia brzegowego zadanie wsadowe *Procesor komunikatów* zostanie automatycznie utworzone w celu wykonania, więc nie ma potrzeby ręcznego planowania tego zadania.

W razie potrzeby można uzyskać dostęp do zadania wsadowego, klikając pozycję **Administrowanie systemem > Procesor komunikatów > Procesor komunikatów**.

## <a name="manually-process-or-cancel-a-message"></a>Ręczne przetwarzanie lub anulowanie komunikatu

W razie potrzeby można ręcznie przetworzyć lub anulować komunikat, w zależności od jego bieżącego stanu. W tym celu zaznacz komunikat w siatce, a następnie wybierz opcję **Przetwórz** lub **Anuluj** w okienku akcji

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Konfigurowanie zdarzeń biznesowych w celu dostarczania alertów o nieudanym przetwarzaniu

Oprócz filtrowania według wartości **stanu komunikatu** *Anulowany* w celu wyszukiwania informacji o nieudanych komunikatach, można skonfigurować [zdarzenia biznesowe](../../fin-ops-core/dev-itpro/business-events/home-page.md) w centrum, aby otrzymywać alerty o nieudanym przetwarzaniu. W tym celu aktywuj zdarzenie biznesowe o nazwie *Przetworzenie komunikatu procesora komunikatów* na stronie **Katalog zdarzeń biznesowych** (**Administrowanie systemem > Ustawienia > Zdarzenia biznesowe > Katalog zdarzeń biznesowych**).

W trakcie procesu aktywacji należy określić, czy zdarzenie jest specyficzne dla jednej czy wszystkich firm, i podać **nazwę punktu końcowego**, którą należy najpierw zdefiniować.

>[!NOTE]
> Jeśli w polu **w przypadku wystąpienia zdarzenia biznesowego** jest wybrane ustawienie *Microsoft Power Automate* (a nie na przykład *HTTPS*), **nazwa punktu końcowego** zostanie automatycznie utworzona w module Supply Chain Management na podstawie ustawień *Microsoft Power Automate*.

### <a name="microsoft-power-automate-example"></a>Przykład: Microsoft Power Automate

W tym przykładzie używasz pola **w przypadku wystąpienia zdarzenia biznesowego** z ustawieniem *Microsoft Power Automate*, aby wysyłać wiadomości e-mail zawierające komunikaty InfoLog i hiperłącza do strony **Komunikaty procesora komunikatów** określonego nieprzetworzonego komunikatu we wdrożeniu centrum. W razie potrzeby można dodać dodatkową logikę, aby wysłać powiadomienia równolegle przy użyciu innych kanałów i kontrolować adresatów na podstawie danych zdarzenia.

1. W [Power Automate](https://preview.flow.microsoft.com) utwórz nowy automatyczny przepływ w chmurze dla wyzwalacza przepływu **w przypadku wystąpienia zdarzenia biznesowego — aplikacja Fin & Ops (Dynamics 365)**, po którym następują kroki **Przeanalizuj JSON** i **Wyślij wiadomość e-mail**, tak jak pokazano na poniższej ilustracji.

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Power Automate automatyczny przepływ w chmurze":::

1. W kroku **W przypadku wystąpienia zdarzenia biznesowego** można odszukać lub wprowadzić **wystąpienie** centrum, a następnie użyć kroków **Kategoria**, **Zdarzenie biznesowe** *Przetworzony komunikat procesora komunikatów*, jak pokazano na poniższej ilustracji.

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate Krok W przypadku wystąpienia zdarzenia biznesowego":::

1. W kroku **Przeanalizuj JSON** wprowadź **schemat** definiujący pola rozszerzone. Można użyć opcji *Pobierz schemat* na stronie **Katalog zdarzeń biznesowych** w module Supply Chain Management lub rozpocząć od wklejenia przykładowego tekst schematu. Ten przykładowy tekst znajduje się po następującej ilustracji.

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

1. W kroku **Wysyłanie wiadomości e-mail** możesz zaznaczyć poszczególne pola lub rozpocząć od wklejenia przykładowej treści wiadomości e-mail w polu **Treść**. Ten przykład znajduje się po następującej ilustracji.

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

1. Zapisanie zdarzenia biznesowego spowoduje jego automatyczne uaktywnienie, po czym jest gotowe do użycia w ramach modułu Supply Chain Management.
