---
title: Magazyny
description: Lokalizacje w magazynach są używane w podstawowym module zarządzania magazynem (WMS I) do ustalania, gdzie towary będą przechowywane i skąd będą pobierane w magazynie zarządzanym w ramach WMS I.
author: yufeihuang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSLocation, WMSBlockingCause, WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd5ad086cadd2e49585614e7650bb7e30a4e7328
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888594"
---
# <a name="inventory-locations"></a>Magazyny

[!include [banner](../includes/banner.md)]

Lokalizacje w magazynach są używane w podstawowym module zarządzania magazynem (WMS I) do ustalania, gdzie towary będą przechowywane i skąd będą pobierane w magazynie zarządzanym w ramach WMS I.

Ten artykuł dotyczy funkcji w module Zarządzanie zapasami. Nie ma zastosowania do funkcji w module Zarządzanie magazynem.

Termin lokalizacja dotyczy miejsca, w którym towary są przechowywane i z którego są wyjmowane.

Dla każdej lokalizacji można także określić miejsce, w którym jest wkładany towar. Domyślnie te miejsca są identyczne. Zazwyczaj towary są wkładane i wyjmowane po tej samej stronie lokalizacji, jednak ta zasada nie zawsze obowiązuje. Na przykład towary przechowywane na ruchomych regałach są wkładane z jednego korytarza, a wyjmowane z drugiego. Głównego wprowadzenia dokonuje się przez nazwę lokalizacji, która jest zwykle określana na podstawie jej współrzędnych: magazyn, korytarz, regał, półka i pojemnik. Tę nazwę lub identyfikator można wprowadzać ręcznie lub generować na podstawie współrzędnych lokalizacji — na przykład 01-02-03-4 oznacza korytarz 1, regał 2, półkę 3 i pojemnik 4 na stronie Magazyny.
Właściwości lokalizacji

Lokalizacja ma następujące właściwości:
-   Rozmiar (wysokość, szerokość, głębokość, a przez to objętość)
-   Magazyn, korytarz, regał, półka oraz pojemnik.
-   Typ lokalizacji (lokalizacja zbiorcza, lokalizacji pobrania, dok rozładunkowy, dok załadunkowy, lokalizacja przyjęcia z produkcji, lokalizacja inspekcji lub supermarket kanban)

W systemach online w celu sprawdzenia, czy operator wybrał prawidłową lokalizację dla określonego towaru, można użyć funkcji Tekst sprawdzania. Ten tekst sprawdzania można utworzyć ręcznie lub użyć domyślnego.

## <a name="sort-codes"></a>Kody sortowania
Kody sortowania umożliwiają optymalizację obsługi wierszy pobrań, które pozwalają uzyskać szczegółowe informacje wymagane do pobierania towarów z magazynu, w tym kolejność pobierania. Kody sortowania mogą być określane na podstawie korytarza lub innych współrzędnych, można je także przypisywać ręcznie do konkretnej lokalizacji.

## <a name="blocked-locations"></a>Lokalizacje zablokowane
Sporadycznie konieczne może być wskazanie lokalizacji, która jest przez jakiś czas zablokowana, na przykład w celu dokonania napraw. Innym razem może zaistnieć potrzeba zablokowania tylko wejścia lub tylko wyjścia.

## <a name="tree-structure"></a>Struktura drzewa

Na stronie Magazyny można wyświetlić układ magazynu w postaci struktury drzewa na podstawie współrzędnych lokalizacji magazynu, w zdefiniowanym formacie wyświetlania.

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a>Obsługa magazynów za pomocą formularza magazynu

Można skopiować lokalizacje z jednego magazynu do innego i tworzyć lokalizacje za pomocą kreatora. Przed uruchomieniem kreatora należy upewnić się, że masz zdefiniowane domyślne nazwy lokalizacji na stronie Magazyn.



## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie nowego układu magazynu](tasks/create-new-warehouse-layout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]