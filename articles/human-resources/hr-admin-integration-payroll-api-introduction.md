---
title: Wprowadzenie do API integracji płac
description: W tym temacie opisano interfejs API integracji Listy płac Dynamics 365 Human Resources.
author: twheeloc
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3743561e3ea3c798c37d71d851eb6b197c8d1c41
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2022
ms.locfileid: "8533834"
---
# <a name="payroll-integration-api-introduction"></a>Wprowadzenie do API integracji płac


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym dokumencie opisano interfejs API integracji Listy płac Dynamics 365 Human Resources. Interfejs API umożliwia uproszczone, końcowe integracje między Human Resources i partnerami systemów listy płac. Zintegrowane doświadczenie zaczyna się w dziale Human Resources od profilu pracownika, wynagrodzenia i odliczeń oraz informacji o składkach. Kiedy zatrudniasz pracownika i wprowadzasz wymagany profil i informacje o płacach do Human Resources, system płac pobiera te informacje do wykorzystania podczas przetwarzania listy płac. Wszelkie aktualizacje wprowadzone do pracownika lub informacje o wynagrodzeniach są również pobierane do wykorzystania w późniejszych okresach wypłaty.

[![Przepływ integracji płac.](media/hr-admin-integration-payroll-api-introduction-flow.png)](media/hr-admin-integration-payroll-api-introduction-flow-2.png#lightbox)

Aby włączyć integrację, składnik Human Resources zawiera następujące składniki:

- [Funkcja oznaczania pracownika jako gotowego do zapłaty.](hr-compensation-payroll.md)
- Integracyjny interfejs API, otwierający nową funkcjonalność do integracji aplikacji.

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Ten interfejs API jest wbudowany Microsoft Dataverse (poprzednio Common Data Service). Cała interakcja RESTful z tym interfejsem API odbywa się za pośrednictwem internetowego interfejsu API Microsoft Dataverse, który korzysta z protokołu OData. Ten interfejs API jest podzestawem interfejsu API sieci Web Dataverse. Interfejs API sieci Web Dataverse definiuje cechy, takie jak uwierzytelnianie, umowy SLA, partia, kontrola współbieżności i obsługa błędów.

Aby uzyskać więcej ogólnych informacji na temat interfejsu API sieci Web Microsoft Dataverse, zobacz:

- [Co to jest usługa Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)
- [Użyj interfejsu API sieci Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Podręcznik dewelopera Microsoft Dataverse](/powerapps/developer/data-platform)

Ta dokumentacja zawiera szczegółowe informacje i wskazówki dla deweloperów dotyczące korzystania z internetowego interfejsu API Dataverse, w tym następujące tematy:

- [Uwierzytelnianie z Microsoft Dataverse za pomocą interfejsu API sieci Web](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [Wykonywanie operacji przy użyciu interfejsu API sieci Web](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [Używanie Postman z interfejsem API sieci Web](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [Użyj śledzenia zmian, aby zsynchronizować dane z systemami zewnętrznymi](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Wirtualne tabele dla Human Resources w Dataverse

Punkty końcowe dla interfejsu API integracji listy płac korzystają z możliwości platformy tabel wirtualnych Microsoft Dataverse. Domyślnie tabele wirtualne i skojarzone z nimi punkty końcowe interfejsu API nie są wdrażane w środowiskach Human Resources, co umożliwia organizacjom określenie, które punkty końcowe OData będą widoczne dla środowiska. Aby można było korzystać z interfejsu API, należy wygenerować tabele wirtualne dla jednostek Human Resources dla środowiska.

Aby uzyskać informacje dotyczące generowania tabel wirtualnych dla interfejsu API, zobacz temat [Konfigurowanie tabel wirtualnych Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Model danych

Poniższy diagram ilustruje relacje w ramach interfejsu API. Kilka typów ma klucze obce do innych, wcześniej istniejących jednostek w dziale Human Resources, które nie zostały tutaj zilustrowane. Ten dokument zawiera informacje o jednostkach, które są specyficzne dla scenariuszy integracji listy płac. Jednak istnieje wiele innych podmiotów w Dataverse Web API for Human Resources, które mogą być również istotne dla Twojej integracji. Niektóre z tych jednostek odwołują się do relacji klucza obcego lub właściwości nawigacji.

[![Model danych API integracji listy płac.](media/hr-admin-payroll-api-data-model.png)](media/hr-admin-payroll-api-data-model.png#lightbox)

## <a name="payroll-employee-and-related-entities"></a>Pracownik etatowy na liście płac i jednostki powiązane

Jednostki:

- [Pracownik etatowy listy płac](hr-admin-integration-payroll-api-payroll-employee.md)
- [Adres pracownika listy płac](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [Plan stałych wynagrodzeń listy płac](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md)
- [Plan zmiennych wynagrodzeń listy płac](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md)
- [Zadanie stanowiska listy płac](hr-admin-integration-payroll-api-payroll-position-job.md)
- [Stanowisko listy płac](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>Informacje dodatkowe

[Generowanie i przeglądanie jednostek listy płac](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[Konfigurowanie parametrów rozwiązania Human Resources](hr-setup-parameters.md)<br>
[Konfigurowanie udostępnionych parametrów rozwiązania Human Resources](hr-setup-shared-parameters.md)<br>
[Co to jest usługa Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Użyj interfejsu API sieci Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
