---
title: "Administrowanie organizacją — strona główna"
description: "Ten temat zawiera informacje o zasobach, które ułatwią korzystanie z rozwiązania Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition w organizacji."
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: eb8674a6401b11e8e33d3cba54add1fb4bca1cd3
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="organization-administration-home-page"></a>Administrowanie organizacją — strona główna

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje o zawartości, która ułatwi zaawansowanym użytkownikom i administratorom skonfigurowanie rozwiązania Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Ta zawartość ułatwi im skonfigurowanie systemu w celu płynnej i efektywnej pracy w organizacji.

Większość zawartości wymienionej tutaj dotyczy funkcji w module **Administracja organizacyjna**. Istnieje jednak kilka zadań, takich jak tworzenie i używanie szablonu rekordu, które mogą zostać wykonane w dowolnym module, aby ułatwić organizacji bardziej efektywne działanie. 

<a name="number-sequences"></a>Sekwencje identyfikatorów
----------------
Sekwencje numerów są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które muszą mieć identyfikatory. Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do *odwołania*. Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem.

-   [Omówienie sekwencji numerów](number-sequence-overview.md)
-   [Konfigurowanie sekwencji numeracji za pomocą kreatora](tasks/set-up-number-sequences-wizard.md) (przewodnik po zadaniu)
-   [Konfigurowanie indywidualnych sekwencji identyfikatorów](tasks/set-up-number-sequences-individual-basis.md) (przewodnik po zadaniu)

## <a name="organizations"></a>Organizacje
Organizacja to grupa osób, które pracują razem, aby przeprowadzić proces biznesowy lub osiągnąć cel. Hierarchie organizacyjne reprezentują relacje między organizacjami, które tworzą firmę.

Przed skonfigurowaniem organizacji i hierarchii organizacyjnych w rozwiązaniu Finance and Operations upewnij się, że masz plan dotyczący modelowania firmy. Model organizacyjny ma znaczny wpływ na implementację programu Finance and Operations i na procesy biznesowe.

-   [Organizacje i hierarchie organizacyjne](organizations-organizational-hierarchies.md)
-   [Planowanie hierarchii organizacyjnej](plan-organizational-hierarchy.md)
-   [Tworzenie hierarchii organizacyjnej](tasks/create-organization-hierarchy.md) (przewodnik po zadaniu)
-   [Tworzenie firmy](tasks/create-legal-entity.md) (przewodnik po zadaniu)
-   [Tworzenie jednostki operacyjnej](tasks/create-operating-unit.md) (przewodnik po zadaniu)

## <a name="address-books"></a>Książki adresowe
Globalna książka adresowa to scentralizowane repozytorium danych głównych, które musi być przechowywane dla wszystkich osób wewnętrznych i zewnętrznych, z którymi współpracuje firma. Dane skojarzone z rekordami stron obejmują nazwę i adres oraz informacje kontaktowe. 

Po utworzeniu w globalnej książki adresowej można utworzyć dodatkowe książki adresowe, np. oddzielne książki adresowe dla każdej firmy w organizacji lub dla każdego wiersza biznesowego. 

-   [Globalna książka adresowa](overview-global-address-book.md)
-   [Planowanie sposobu konfiguracji globalnej książki adresowej i dodatkowych książek adresowych](plan-configuration-global-address-book-additional-address-books.md)
- [Konfigurowanie globalnej książki adresowej](tasks/configure-global-address-book.md)
-   [Książki adresowe — najczęściej zadawane pytania](qa-address-books.md)


## <a name="workflow"></a>System Workflow
Przepływ pracy to system instalowany z rozwiązaniem Finance and Operations, którego można użyć do tworzenia indywidualnych przepływów pracy lub procesów biznesowych. Utworzenie przepływu pracy definiuje sposób przepływu lub przenoszenia dokumentu przez system, pokazując, kto musi wykonać zadanie, podjąć decyzję lub zatwierdzić dokument. 

-   [Omówienie przepływu pracy](overview-workflow-system.md)
-   [Elementy przepływu pracy](workflow-elements.md)
-   [Akcje przepływu pracy](workflow-actions.md)
-   [Tworzenie przepływu pracy](create-workflow.md)

## <a name="electronic-signatures"></a>Podpisy elektroniczne
Podpis elektroniczny potwierdza tożsamość osoby, która ma rozpocząć lub zatwierdzić jakiś proces obliczeniowy. W przypadku niektórych branż podpis elektroniczny jest tak samo prawnie wiążący jak podpis odręczny. Podpisy elektroniczne są wymagane przepisami w przypadku kilku branż regulowanych, takich jak przemysł farmaceutyczny, spożywczy oraz lotniczy i obronny.

W programie Finance and Operations można używać podpisów elektronicznych w przypadku procesów biznesowych o podstawowym znaczeniu. Niektóre procesy mają wbudowane możliwości podpisu elektronicznego. Można również tworzyć niestandardowe wymagania dotyczące podpisu cyfrowego dla dowolnej tabeli lub pola bazy danych.

-   [Omówienie podpisów elektronicznych](electronic-signature-overview.md)
-   [Konfigurowanie podpisów elektronicznych](tasks/set-up-electronic-signatures.md) (przewodnik po zadaniu)

## <a name="case-management"></a>Zarządzanie sprawami
Planowanie, śledzenie i analizowanie spraw powoduje, że użytkownik może tworzyć wydajne rozwiązania, które mogą być używane dla podobnych spraw. Na przykład, gdy przedstawiciele obsługi klienta lub specjaliści ds. personalnych tworzą sprawy, znajdują informacje w artykułach merytorycznych, ułatwiające pracę ze sprawami i ich efektywnego rozwiązywania. 

-   [Omówienie zarządzania sprawami](cases.md)
-   [Konfigurowanie zabezpieczeń, procesów i kategorii spraw](plan-case-management.md)

## <a name="record-templates"></a>Szablony rekordów
Szablony rekordów pomagają w szybkim tworzeniu rekordów w systemie. Można utworzyć szablon rekordu, tak aby wartości pól, które są często używane, nie musiały być jawnie wprowadzane dla każdego nowego rekordu. 

-   [Szablony rekordów](record-templates.md)
- [Tworzenie szablonu rekordu w celu ułatwienia wprowadzania danych](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (przewodnik zadania)
- [Używanie szablonu rekordu do tworzenia nowego rekordu](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (przewodnik zadania)

## <a name="general-organization-administration"></a>Ogólny administrator organizacji
-   [Zmienianie transparentu lub logo](../get-started/tasks/change-banner-or-logo.md) (przewodnik po zadaniu)
- [Konfigurowanie zarządzania dokumentami](configure-document-management.md)
- [Konfigurowanie i wysyłanie wiadomości e-mail](configure-email.md)
-   [Dane dotyczące daty/godziny i strefy czasowe](date-time-zones.md)








