---
title: Zarządzanie zmianami w formułach i ich składnikach
description: Ten artykuł opisuje jak wykonać zarządzanie formułą i zarządzać zmianami w danych podstawowych produkcji procesowej.
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8105ebc7f3698a6baaa04b6548dac18a7bf81a47
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904080"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>Zarządzanie zmianami w formułach i ich składnikach

[!include [banner](../includes/banner.md)]

Jeśli w Microsoft Dynamics 365 Supply Chain Management są używane funkcje produkcji procesowej, można również używać powiązanych funkcji zarządzania formułami do zarządzania następującymi zmianami:

- **Formuła i planowanie towarów:** zarządzanie zmianami składników w formułach oraz ich produktami ubocznymi i współproduktami.
- **Produkty uboczne i współprodukty:** edycja ilości i innych informacji o produktach dodatkowych i produktach ubocznych w formule.
- **Pozycje z ilością efektywną:** zarządzanie zmianami w pozycjach z ilością efektywną.

## <a name="turn-this-feature-on-or-off"></a>Włączanie lub wyłączanie tej funkcji

Funkcje opisane w tym artykule wymagają włączania w *systemie zarówno zarządzania zmianami inżynieryjnymi*, jak i *Zarządzaj zmianami formuł i ich składników*. Aby uzyskać szczegółowe informacje dotyczące sposobu włączanie i wyłączanie tych funkcji, zobacz [omówienie zarządzania zmianami inżynieryjnymi](product-engineering-overview.md).

## <a name="feature-naming-conventions"></a>Konwencje nazewnictwa funkcji

W interfejsie użytkownika (UI) i dokumentacji Supply Chain Management funkcjonalność zarządzania zmianą jest zwykle określana jako *zarządzanie zmianami inżynieryjnymi*, a produkty zarządzalne są zwykle określane jako *engineering products*. Chociaż terminologia ta nie jest zwykle kojarzona z zarządzaniem recepturami dla produkcji procesowej, należy myśleć o zarządzaniu zmianami inżynierskimi jako po prostu o zarządzaniu zmianami, a o produktach inżynierskich jako o produktach wersjonowanych.

## <a name="work-with-formula-change-management-features"></a>Praca z funkcjami zarządzania zmianą formuły

Poniższa lista podsumowuje, w jaki sposób funkcje zarządzania zmianami inżynierskimi mają zastosowanie do zarządzania formułą. Znajdują się tam również linki do dalszych informacji. Ponieważ zarządzanie zmianą formuły wykorzystuje funkcje zarządzania zmianą inżynieryjną, należy dowiedzieć się, jak ogólnie działa zarządzanie zmianą inżynieryjną, aby móc je wykorzystać do zarządzania formułami i ich składnikami.

- **Scentralizowane zarządzanie danymi produktów** — umożliwia skonfigurowanie organizacji, która — za pośrednictwem zarządzanego procesu zwalniania — zapewnia, że dokładne i odpowiednie dane produktów są dostępne dla użytkowników w całym przedsiębiorstwie. Aby uzyskać więcej informacji, zobacz artykuł [Firm inżynierskie i reguły własności danych](engineering-org-data-ownership-rules.md).
- **Wersja produktu** – śledzenie zmian w produktach za pośrednictwem wersji produktów i kontrolowanie produktu na wszystkich etapach łańcucha dostaw. W ten sposób można śledzić zmiany formuł. Aby uzyskać więcej informacji, zobacz [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).
- **Zarządzanie cyklem życia produktu** – zarządzanie widocznością danych produktów w całej organizacji i kontrolowanie dostępności wersji produktów na każdym etapie łańcucha dostaw. Masz szczegółową kontrolę nad tym, kiedy dana wersja produktu może być używana w określonych procesach biznesowych i możesz tworzyć własne stany cyklu życia, aby dopasować je do swoich potrzeb biznesowych. Aby uzyskać więcej informacji, zobacz [Stany cyklu życia produktu i transakcje](product-lifecycle-state-transactions.md).
- **Zarządzanie zmianami formuły** — użytkownicy w całej organizacji mogą żądać zmian w formułach. Wykorzystanie zleceń zmian do oceny i dokumentowania wpływu proponowanych zmian. Dodaj przepływy pracy do zarządzania procesem zmian i wydawania nowych wersji produktu i jego formuły. Aby uzyskać więcej informacji, zobacz [Zarządzanie zmianami dotyczącymi produktów inżynieryjnych](engineering-change-management.md).
- **Kontrola gotowości** – używanie sprawdzianów systemowych i wytycznych dotyczących użytkowników (kwestionariuszy i list kontrolnych) w celu zapewnienia, że wszystkie wymagane dane produktu są w pełni wprowadzone przed jego wydaniem. Aby uzyskać więcej informacji, zobacz temat [Gotowość produktu](product-readiness.md).
- **Rozszerzone funkcje zwalniania produktów** – zwalnianie w pełni zdefiniowanych wersji produktu i jego formuły z organizacji (firmy) do innych firm. Można także zdecydować, czy przed zwolnieniem informacje o produkcie mają być przeglądane, czy edytowane. Aby uzyskać więcej informacji, zobacz [Zwalnianie struktur produktu](release-product-structure.md).

Pamiętaj, że większość artykułów połączonych z poprzednią listą zawiera przykłady oparte na BOM. Formuły działają jednak w podobny sposób. Oto kilka dodatkowych pojęć, które warto znać, gdy używa się zarządzania zmianą (lub tylko zarządzania zmianą formuły) do zarządzania formułami i zestawami BOM:

- Dla każdej [kategorii inżynieryjnej produktu](engineering-versions-product-category.md) można określić typ produkcji (BOM, formuła lub pozycja planowania). Możesz również określić, czy obsługa ilości efektywnej jest wymagana dla produktów, które korzystają z tej kategorii.
- Produkty uboczne i współprodukty nie są produktami inżynieryjnymi. Dlatego nie są one wersjonowane. Jeśli trzeba je zmienić, po prostu utwórz nowy produkt. Takie podejście ułatwia obsługę.
- Można zarządzać pozycjami końcowymi, które są BOM-ami i które mają pozycje podrzędne formuły. Funkcjonalność będzie działać dla dowolnej kombinacji BOM-ów zawierających formuły i/lub formuł zawierających BOM-y.
