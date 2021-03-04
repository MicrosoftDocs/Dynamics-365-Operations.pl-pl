---
title: Omówienie materiałów niebezpiecznych
description: Ten temat zawiera przegląd funkcji związanych z obsługą i dokumentami materiałów niebezpiecznych podczas zarządzania informacjami o produktach i zarządzania magazynem.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 34c0a19308bb5159faa9a4ab06bf65e58da0deb1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434976"
---
# <a name="hazardous-materials-overview"></a>Omówienie materiałów niebezpiecznych

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W celu zachowania zgodności z przepisami dotyczącymi wysyłki i transportu, organizacje, które dostarczają materiały, które są sklasyfikowane jako towary niebezpieczne, muszą zawierać dodatkowe dokumentacji wraz z ich wysyłką. Funkcja materiałów niebezpiecznych umożliwia klientom przechowywanie informacji związanych ze zwolnionymi pozycjami. Te informacje mogą być następnie używane w celu przygotowania dokumentacji dotyczącej wysyłki. Organizacja, która dostarcza towary niebezpieczne, musi dysponować własnymi procesami i procedurami służącymi do zarządzania procesem wysyłki. Microsoft Dynamics 365 Supply Chain Management to tylko narzędzie, które może pomóc w wygenerowaniu wymaganych dokumentów.

Na poniższym diagramie przedstawiono kroki niezbędne do skonfigurowania i użycia funkcji materiałów niebezpiecznych.

![Ustawienia i użycie funkcji materiałów niebezpiecznych](media/hazmat-overview.png "Ustawienia i użycie funkcji materiałów niebezpiecznych")

Funkcja zarządzania materiałami niebezpiecznymi jest skonfigurowana w module Zarządzanie informacjami o produktach i zawiera dokumenty, które można wydrukować za pomocą modułu Zarządzanie magazynem. Dzięki temu obszary te są tymi dwoma głównymi obszarami, które będą przeglądane, konfigurowane i zastosowane w następujących funkcjach:

- **Zarządzanie informacjami o produktach:** — umożliwia konfigurowanie kodów, które będą stosowane w odniesieniu do zwolnionego produktu.
- **Zarządzanie magazynem** — praca z dodatkowymi dokumentami wysyłki, które będą drukowane dla wysyłek.

> [!IMPORTANT]
> Funkcje dot. materiałów niebezpiecznych w Supply Chain Management zawierają użyteczny zbiór pól informacji o produktach i związanych z nimi funkcji, które mogą pomóc w rejestrowaniu i odnajdywaniu informacji związanych z produktami niebezpiecznymi. Te funkcje mogą również pomóc w projektowaniu i drukowaniu dokumentów dostawy, które zawierają niektóre z tych samych informacji o wszelkich transportowanych niebezpiecznych materiałach. Jednak system nie sprawi, że działania będą automatycznie zgodne ze wszystkimi przepisami danego kraju lub regionu. Chociaż narzędzia te mają na celu ułatwienie zgodności ze wspólnymi przepisami, same w sobie nie są wystarczające ani nie gwarantują poprawności. Twoja organizacja jest odpowiedzialna za zastosowanie wszystkich stosownych rozporządzeń i podjęcie wszelkich niezbędnych kroków w celu przestrzegania odpowiednich przepisów.

## <a name="product-information-management"></a>Zarządzanie informacjami o produktach

Zarządzanie informacjami o produktach zawiera zakres tabel ustawień, w którym można podać informacje o odwołaniach, które znajdują się w wykazach towarów niebezpiecznych dla transportu drogowego, powietrznego i morskiego.

W przypadku opracowania tych funkcji nastąpiły odwołania do następujących wspólnych reguł:

- **ADR** — przepisy dotyczące międzynarodowego przewozu drogowego towarów niebezpiecznych
- **CFR 49** — przepisy w USA dot. przewozu towarów niebezpiecznych
- **IMDG** — Międzynarodowy kodeks ładunków niebezpiecznych (IMDG)
- **IATA** — regulacje dotyczące towarów niebezpiecznych międzynarodowego zrzeszenia przewoźników powietrznych (IATA)

Każdy zbiór rozporządzeń zawiera standardowe wykazy towarów niebezpiecznych i kodów referencyjnych. Z tego też powodu program Supply Chain Management zawiera tabelę odwołań dla wspólnych kodów z tych list. Każda lista ma również kilka unikatowych kodów, które można zdefiniować.

Aby uzyskać więcej informacji na temat konfigurowania przepisów i wartości materiałów niebezpiecznych oraz sposobu przypisywania wartości do odpowiednich produktów, należy zapoznać się z następującymi tematami:

- [Ustawianie materiałów niebezpiecznych](hazmat-setup.md)
- [Materiały niebezpieczne w produktach, zamówieniach, wysyłkach i ładunkach](hazmat-items.md)

## <a name="warehouse-management"></a>Zarządzanie magazynem

Podczas przygotowywania wysyłki w module Zarządzanie magazynem można wydrukować kilka nowych raportów korzystających z informacji skonfigurowanych w module Zarządzanie informacjami o produktach. Aby uzyskać więcej informacji o dostępnych raportach i sposobach ich używania, zapoznaj się z [zapytaniami i raportami dotyczącymi materiałów niebezpiecznych](hazmat-reports.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]